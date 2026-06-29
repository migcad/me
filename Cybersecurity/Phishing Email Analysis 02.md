


# Forensic Analysis of Email Headers and Message Source

## Executive Summary

**Assessment:** **Very High Confidence Phishing Email (≈99% confidence)**

After examining both the SMTP routing headers and the HTML message source, I conclude that this email is almost certainly a phishing campaign designed to steal credentials by impersonating an electronic signature notification.

The attacker has taken considerable effort to make the email appear trustworthy:

* The email was sent from infrastructure that is authorized to send mail on behalf of `jci.com`.
* SPF passed.
* DMARC passed.
* Microsoft's spam filters assigned a low spam confidence level.
* The email visually resembles a legitimate electronic signature notification.

However, the single most important piece of evidence is the destination of the "Review & Sign Now" button.

Instead of directing the user to Clixsign or another legitimate electronic signature service, the email directs the recipient to:

```
https://emea01safelinks-protection-documents-esign.pro
```

This is **not** a Microsoft SafeLinks domain.

It is **not** a Johnson Controls domain.

It is **not** a Clixsign domain.

Instead, it is a deceptive lookalike domain intentionally engineered to resemble Microsoft's SafeLinks infrastructure.

This is the decisive indicator that the email is malicious.

---

# High-Level Timeline

The email followed this approximate path:

```
Attacker or compromised system
        │
        ▼
Internal JCI Exchange server
        │
        ▼
IONOS outbound SMTP gateway
        │
        ▼
Microsoft Exchange Online Protection
        │
        ▼
Hotmail mailbox
        │
        ▼
Inbox
```

The routing itself appears legitimate.

The payload is what is malicious.

---

# Detailed SMTP Routing Analysis

SMTP routing is read from the bottom upward.

Each "Received:" header represents one server handing the message to the next server.

---

## Segment 1 — Message Creation

```
From:
Miguelcadena via Clixsign
<john.mccormick@jci.com>
```

This is where the message originated.

Immediately noticeable are several inconsistencies.

The display name is

```
Miguelcadena via Clixsign
```

while the actual sender mailbox is

```
john.mccormick@jci.com
```

Normally these would match.

Examples of legitimate formatting would be:

```
John McCormick via Clixsign
```

or

```
Clixsign
```

Using the recipient's own name as part of the display name is unusual and strongly suggests manipulation of the template.

---

## Segment 2 — Internal Exchange Server

```
Received:
from 1cbdb02c.biz (10.72.140.250)

by

winhex19beeu31.wineu.mail
```

Notice the IP address:

```
10.72.140.250
```

This is a private RFC1918 address.

Private addresses cannot exist on the public Internet.

Therefore this server is inside an organization's private network.

The hostname

```
winhex19beeu31.wineu.mail
```

suggests an internal Microsoft Exchange server located in Europe.

This indicates the email was generated inside an internal mail environment.

This does **not** prove legitimacy.

If an attacker compromises an employee account or an internal application, they can generate email from inside the corporate network.

---

## Segment 3 — Internal Mail Relay

```
Received:

from

winhex19beeu31.wineu.mail

by

mri.eue.server.lan
```

Again:

```
10.x.x.x
```

private addresses.

This is another internal relay.

The mail is moving between internal Exchange infrastructure before being sent externally.

---

## Segment 4 — Outbound Gateway

```
Received:

from

mout.kundenserver.de

212.227.126.133
```

This is the first public Internet server.

The IP

```
212.227.126.133
```

belongs to IONOS.

This server is acting as the outbound SMTP gateway.

This explains why SPF passes.

---

## Segment 5 — Microsoft Exchange Online Protection

```
DM2PEPF00003FC9
```

This is Microsoft's Exchange Online Protection (EOP).

Here Microsoft performs:

* SPF validation

* malware scanning

* spam analysis

* DMARC verification

* reputation analysis

Microsoft concluded:

```
SPF PASS
```

```
DMARC PASS
```

```
Spam Confidence Level = 1
```

The email therefore looked technically legitimate.

---

## Segment 6 — Exchange Mailbox Servers

After Microsoft accepted the message, it traversed Microsoft's internal mailbox infrastructure.

```
DM2PEPF00003FC9
        │
        ▼
DS7P222CA0006
        │
        ▼
PU4P216MB1957
        │
        ▼
SE2P216MB3393
```

These are Microsoft's own mailbox servers.

Each hop is entirely normal.

---

## Segment 7 — Delivery to Inbox

Finally:

```
Delivered using HTTPS
```

to the Hotmail mailbox.

No additional relays occurred after Microsoft's mailbox servers.

---

# Authentication Analysis

## SPF

```
spf=pass
```

Meaning:

The sending server

```
212.227.126.133
```

was authorized to send mail for

```
jci.com
```

SPF only answers one question:

> "Was this server allowed to send email for this domain?"

It does **not** answer:

> "Is this email trustworthy?"

Possible explanations include:

* legitimate sender

* compromised sender account

* compromised application

* compromised mail gateway

* malicious employee

Therefore SPF passing should never be interpreted as proof of legitimacy.

---

## DKIM

```
dkim=none
```

This is noteworthy.

Most large enterprises cryptographically sign outbound mail.

Electronic signature workflows are particularly likely to use DKIM.

The absence of DKIM lowers confidence in the message.

It does not prove phishing.

However it is another warning sign.

---

## DMARC

```
dmarc=pass
```

DMARC passed because SPF aligned with the visible From address.

DMARC does **not** inspect:

* hyperlinks

* attachments

* HTML

* login pages

* phishing content

Many phishing emails pass DMARC.

---

## Composite Authentication

```
compauth=pass
```

Microsoft's composite authentication engine also accepted the sender.

Again, this only reflects authentication.

It is not a determination that the content is safe.

---

# Analysis of the HTML Email

The HTML source contains numerous indicators.

---

## 1. Fake Electronic Signature Notification

The email claims:

```
Your Electronic Signature Is Requested
```

This is a very common phishing lure.

Recipients are conditioned to expect:

* DocuSign

* Adobe Sign

* HelloSign

* Dropbox Sign

* Clixsign

Most users click first and think later because they assume somebody is waiting for their signature.

---

## 2. Generic Subject

```
Signature requested on

Eft-WLTR-383927
```

No indication of:

* customer

* project

* contract

* purchase order

* invoice

* department

Attackers deliberately use vague identifiers because they create curiosity while avoiding factual mistakes.

---

## 3. Missing Business Context

The email says:

```
Please click the link below
```

But never explains:

* who sent it

* why

* what the document concerns

* why the recipient should expect it

Legitimate signing requests nearly always include context.

---

## 4. Poor Footer

```
Questions?

Please contact

James Law, LLC
```

No:

* email address

* phone number

* explanation

This footer appears copied from another template.

---

## 5. Typographical Errors

The footer contains:

```
delviery
```

instead of

```
delivery
```

Large electronic signature providers generally do not release production email templates containing obvious spelling mistakes.

---

# The Most Important Evidence

The HTML button is:

```html
<a href="https://emea01safelinks-protection-documents-esign.pro">
Review & Sign Now
```

Everything else in the email is secondary.

This URL determines the classification.

---

# Why This URL Is Malicious

Microsoft SafeLinks URLs always resemble:

```
https://nam01.safelinks.protection.outlook.com/
```

or

```
https://eur03.safelinks.protection.outlook.com/
```

Notice the real Microsoft domain:

```
protection.outlook.com
```

Instead, this email uses:

```
emea01safelinks-protection-documents-esign.pro
```

This is an entirely different domain.

The attacker intentionally concatenated familiar Microsoft terminology:

```
emea01
```

```
safelinks
```

```
protection
```

```
documents
```

```
esign
```

The resulting hostname is designed so that users glance at it and think:

> "This is Microsoft's SafeLinks protection."

It is not.

This is a classic example of a lookalike domain engineered for social engineering.

---

# Why Microsoft Still Delivered It

Many people assume:

> SPF passed.

> DMARC passed.

> Spam score was low.

Therefore it must be legitimate.

That is incorrect.

Microsoft's spam engine primarily evaluates:

* sender reputation

* authentication

* malware

* historical abuse

If an attacker compromises:

* a legitimate mailbox

* a trusted application

* an enterprise email workflow

then the email can successfully pass authentication while containing a malicious hyperlink.

This is exactly why modern phishing campaigns frequently originate from compromised business accounts rather than spoofed addresses.

---

# Possible Attack Scenario

The most likely sequence is:

1. The attacker compromises a legitimate Johnson Controls mailbox or an internal application capable of sending email.

2. The attacker generates a convincing electronic signature notification.

3. The email is sent through authorized infrastructure.

4. SPF and DMARC pass.

5. Microsoft sees a technically authentic email.

6. The recipient clicks the "Review & Sign Now" button.

7. The fake electronic signature website requests authentication.

8. The victim enters Microsoft 365 credentials.

9. The attacker captures those credentials.

10. The attacker gains access to the victim's account.

This style of attack is commonly used in Business Email Compromise (BEC) campaigns because authenticated messages are much less likely to be blocked than messages sent from spoofed domains.

---

# Overall Evidence Summary

| Indicator            | Assessment                        | Interpretation                                                                                                                                 |
| -------------------- | --------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| SPF                  | Pass                              | Sending server was authorized to send for `jci.com`; does not prove the message is benign.                                                     |
| DKIM                 | None                              | Unusual for a large enterprise; weakens confidence in legitimacy.                                                                              |
| DMARC                | Pass                              | Alignment succeeded because SPF aligned; does not evaluate message content.                                                                    |
| Microsoft Spam Score | Low (SCL=1)                       | Reputation looked acceptable; phishing can still bypass filters.                                                                               |
| Sender Display Name  | Suspicious                        | Display name ("Miguelcadena via Clixsign") does not match the sender mailbox (`john.mccormick@jci.com`).                                       |
| Subject              | Generic                           | Lacks document context, organization, or business purpose.                                                                                     |
| HTML Quality         | Poor                              | Template inconsistencies and spelling errors reduce credibility.                                                                               |
| Footer               | Inconsistent                      | "James Law, LLC" is unexplained and does not fit the rest of the message.                                                                      |
| Button Destination   | **Critical Red Flag**             | Links to `emea01safelinks-protection-documents-esign.pro`, a deceptive lookalike domain unrelated to Microsoft, Clixsign, or Johnson Controls. |
| Overall Assessment   | **Very High Confidence Phishing** | The deceptive hyperlink outweighs the positive authentication signals.                                                                         |

# Final Verdict

This email is almost certainly a phishing attack.

The SMTP routing itself is technically valid and indicates that the message was transmitted through infrastructure authorized to send on behalf of `jci.com`, which explains why SPF and DMARC both passed and why Microsoft's filtering systems assigned a low spam score.

However, email authentication validates only the sending infrastructure and domain alignment—it does **not** validate the intent or safety of the message.

The decisive evidence is the embedded hyperlink. The "Review & Sign Now" button directs the recipient to `emea01safelinks-protection-documents-esign.pro`, a domain deliberately crafted to imitate Microsoft's SafeLinks naming convention while being unrelated to Microsoft or the claimed electronic signature service. This, combined with the inconsistent sender identity, generic content, template anomalies, and lack of contextual business information, provides overwhelming evidence that the message is designed to trick recipients into visiting a fraudulent website, most likely to harvest credentials.

Accordingly, this email should be treated as malicious, reported as phishing, and neither its links nor any credentials requested by the linked site should be trusted.
