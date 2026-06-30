# Prompt
Analyse the following email trace and message source.

- Determine if this email is a phishing attack.
- Break down the trail of email routing into segments so I can understand where the email originated and how it got relayed all the way to my Inbox.

Avoid using semantic compression in your response.\
Display your entire response in a single reusable Markdown-style writing block which I can directly save as a .md file.

```none
Received: from PU4P216MB1957.KORP216.PROD.OUTLOOK.COM (2603:1096:301:108::11)by SE2P216MB3393.KORP216.PROD.OUTLOOK.COM with HTTPS; Mon, 29 Jun 202618:56:38 +0000Received: from DS7P222CA0006.NAMP222.PROD.OUTLOOK.COM (2603:10b6:8:2e::23) byPU4P216MB1957.KORP216.PROD.OUTLOOK.COM (2603:1096:301:108::11) with MicrosoftSMTP Server (version=TLS1_2, cipher=TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384) id15.21.159.19; Mon, 29 Jun 2026 18:56:36 +0000Received: from DM2PEPF00003FC9.namprd04.prod.outlook.com(2603:10b6:8:2e:cafe::6a) by DS7P222CA0006.outlook.office365.com(2603:10b6:8:2e::23) with Microsoft SMTP Server (version=TLS1_3,cipher=TLS_AES_256_GCM_SHA384) id 15.21.159.19 via Frontend Transport; Mon,29 Jun 2026 18:56:35 +0000Authentication-Results: spf=pass (sender IP is 212.227.126.133)smtp.mailfrom=jci.com; dkim=none (message not signed)header.d=none;dmarc=pass action=none header.from=jci.com;compauth=passreason=100Received-SPF: Pass (protection.outlook.com: domain of jci.com designates212.227.126.133 as permitted sender) receiver=protection.outlook.com;client-ip=212.227.126.133; helo=mout.kundenserver.de; pr=EReceived: from mout.kundenserver.de (212.227.126.133) byDM2PEPF00003FC9.mail.protection.outlook.com (10.167.23.27) with MicrosoftSMTP Server (version=TLS1_3, cipher=TLS_AES_256_GCM_SHA384) id 15.21.181.6via Frontend Transport; Mon, 29 Jun 2026 18:56:34 +0000X-IncomingTopHeaderMarker: OriginalChecksum:318D99F7CCE9F6836C461E7CB6FD3469D93911F9994C287EE3350557403E1E87;UpperCasedChecksum:770D5B8626B9466282E1006FE2C4A7FA3E91C738C584A0B3CB700B20AEE03E72;SizeAsReceived:2846;Count:14Received: from winhex19beeu31.wineu.mail ([10.72.140.28]) bymri.eue.server.lan (mrieue002 [10.74.32.56]) with ESMTPS (Nemesis) id1Mi4BN-1xHzYu1Ht3-00Zm6Q for miguelcadena@hotmail.com; Mon, 29 Jun 202620:56:33 +0200Received: from 1cbdb02c.biz (10.72.140.250) by winhex19beeu31.wineu.mail(10.72.140.28) with Microsoft SMTP Server (version=TLS1_2,cipher=TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384) id 15.2.2562.43; Mon, 29 Jun2026 20:56:32 +0200Content-Type: multipart/mixed;boundary="===============3326699882436199059=="From: Miguelcadena via Clixsign john.mccormick@jci.comTo: miguelcadena@hotmail.comSubject: Signature requested on Eft-WLTR-383927Date: Mon, 29 Jun 2026 18:56:31 +0000Message-ID: 178275939131.6924.4781492314516302447@jci.comX-Accept-Language: en-us, enReturn-Path: john.mccormick@jci.comX-ClientProxiedBy: winhex19beeu34.wineu.mail (10.72.140.159) Towinhex19beeu31.wineu.mail (10.72.140.28)X-Spam-Flag: NOUI-OutboundReport: notjunk:1;M01:P0+w=;jRXXjR4xuUOU1Z9G+w2PNBtODiceCi1e47QTTxAfBOi5/3B5qluDuTopfkzOHrzormlzab+65X+JL+U39HOW3eq0dX63P8TKhpvQR+gXSI0QaMtKjfVL6dR5vVg4GyQw2Zqp9LC7tjDVlyGTxu8rI4c1G1/ePpZ/7n2IaTuMuWPtfq4Z+ybwoJoo/CgDexOj7DiM1rl9+sKYIz9Mk/426ldEuIGAN+Q08T+iOVF537diE8+MVz9FVpAlwYckwZ86DL4TqVOPGVyaAVAMq+nGlIGBVR4dZhKCMcxIR1LoNtwSXjkwqZ1vOs+wlwrKlEPsp2s+MLUk9nqpQsnto1glCPjflvjz8m0z3tvDCPbej84glfS1CUwZoTIbeY2FK1Ys7vJnZ/gktmEjuiLLW0pLkexp7B7ck5rFErRXVIgnoSoT5XdG8JkwBmOBwFQjuqjGOD2bPbyGCIsl6q3ZsEnQfBrjQkMFdw2L727M16cjSpooC95qwd43GqGpsLfRtkuua0jpt0ZnP0CWU+/sBpUcKgmTn+iBmPS/kOcrsLHNC7KmB9454srg5LdwxW/qypwB6mseeKMKsgcVxXwz6sPVYViFUpohlYgRnUh0SZiJ/sCl5nccgUU9qRqFb0UDro3iG6dBh68hZhc+LAG5E6dBahZAxscMpe6/MuMJ3fxI8BTyEPa4ecQjU2qhgHseGpIAtouTopMfKeYRnRYKhkHKEVyYgpm3wKq3RqcoTIiCJ6tklC+1FZ0HeoADenDuEUmzML2LaTrYQnpM6an0WZ25bf/D7XbcFAGNhF1ZyeYZglKWQzCZRNzu9kjDzbU8ww5GxitKHIt19Td0890Fs81fBovslarCCrXv9VRCjmr0rS2RLpWLXyfJfJ4cfBSFJBN72t/MBZb+KMbzoh8Qso57Mbl4sPTVgpaLyP/bhgyx1SXiQWSIlyOXGRP5k92ij6E+tmEem8k6sYmxAwAzAsL5DeQ2qF7qEf3MCE2tOFDEcBbixMKmbIK2u2vk9IV69LCwrpA84599gS6bgVo0Xj5YnEC2cNl4J16Ooxsr27dgETN8/m+OJcttsXSYSzTwLWmLMjADKI5l6LxMeTRDrP1M7ZQRW2dzU+LkZ6y9iBRcYZ8p44DPyGKZ2Fd10ZUBEb2uLxsSyN2s6VdAzZRK0LKKM+eV15+P+YDyYc9R/tHtedm/B3UbK+oVzkldLHAT9lW+GuglNwSkqBy4dRec8RIyhbR5dSeRY1DFvzrJIUvMJ5Kw5TJ506TM7K0LNyl1U1GXbPMW2uuYq51QPiAJl+VtdCAh039WuBkGBUFRLKvc+Qz0ISvQIGpbLfLN2fuYBy1SImjKbUyNmTtVqCBlicoNGFVT5RLSBrSEzVlmG5PnsbdJOARU2uLqP+/4W9CSzXqJvcHZWRfOSMUKqZqzEni7oUb1/8XgSQu6NCGwcPz9J0Ly+IcnRfTJuDsFByrOqok+AAnHu/thCaBL8kfx8SYvvJWdDitAb1m/HKOkNeYHVajixvqp612+pxhTyfuU/C92FcMSc+50Da94lEJRSllOliagtu8g/DiVTU1sdolpyWxl5JeTdP6yXViL8kzpa28qHioFedRk/iluxuv6LEALO6aMrJ+RXJ76lPHlqhtf61/nhmMUX7MObtVBTYsWecGirnstu4mADhxL2HbKPlBKVvulfT5eP2wNVV8V9xi+AMz8wnvY8f9rizw/euLuQhqAX-IncomingHeaderCount: 14X-MS-Exchange-Organization-ExpirationStartTime: 29 Jun 2026 18:56:34.9072(UTC)X-MS-Exchange-Organization-ExpirationStartTimeReason: OriginalSubmitX-MS-Exchange-Organization-ExpirationInterval: 1:00:00:00.0000000X-MS-Exchange-Organization-ExpirationIntervalReason: OriginalSubmitX-MS-Exchange-Organization-Network-Message-Id: 5187b39b-3968-46a4-4d23-08ded610243eX-EOPAttributedMessage: 0X-EOPTenantAttributedMessage: 84df9e7f-e9f6-40af-b435-aaaaaaaaaaaa:0X-MS-Exchange-Organization-MessageDirectionality: IncomingX-MS-PublicTrafficType: EmailX-MS-TrafficTypeDiagnostic: DM2PEPF00003FC9:EE_|PU4P216MB1957:EE_|SE2P216MB3393:EE_X-MS-Exchange-Organization-AuthSource: DM2PEPF00003FC9.namprd04.prod.outlook.comX-MS-Exchange-Organization-AuthAs: AnonymousX-MS-UserLastLogonTime: 6/29/2026 6:53:22 PMX-MS-Office365-Filtering-Correlation-Id: 5187b39b-3968-46a4-4d23-08ded610243eX-MS-Exchange-EOPDirect: trueX-Sender-IP: 212.227.126.133X-SID-PRA: JOHN.MCCORMICK@JCI.COMX-SID-Result: PASSX-MS-Exchange-Organization-SCL: 1X-Microsoft-Antispam: BCL:0;ARA:1444111002|7120799021|5139299004|970799063|9400799043|10300799038|1680799066|4089299007|1131999019|60050799012|9000799056|70100799019|30041999003|18021999003|6022199012|1602099012|4302099013|3412199025|8011999015|1370799030|1360799030|1380799030|440099028|26104999009;X-MS-Exchange-CrossTenant-OriginalArrivalTime: 29 Jun 2026 18:56:34.3776(UTC)X-MS-Exchange-CrossTenant-Network-Message-Id: 5187b39b-3968-46a4-4d23-08ded610243eX-MS-Exchange-CrossTenant-Id: 84df9e7f-e9f6-40af-b435-aaaaaaaaaaaaX-MS-Exchange-CrossTenant-AuthSource: DM2PEPF00003FC9.namprd04.prod.outlook.comX-MS-Exchange-CrossTenant-AuthAs: AnonymousX-MS-Exchange-CrossTenant-FromEntityHeader: InternetX-MS-Exchange-CrossTenant-RMS-PersistedConsumerOrg: 00000000-0000-0000-0000-000000000000X-MS-Exchange-Transport-CrossTenantHeadersStamped: PU4P216MB1957X-MS-Exchange-Transport-EndToEndLatency: 00:00:03.7181407X-MS-Exchange-Processed-By-BccFoldering: 15.21.0159.018X-Microsoft-Antispam-Mailbox-Delivery:ucf:0;jmr:0;ex:0;auth:1;dest;ENG:(5062000311)(920221119095)(90000117)(920221120095)(90005022)(91005020)(91035115)(9050020)(9100341)(944500132)(2008001181)(2008121020)(4810010)(4910033)(9575002)(10195002)(9320005)(120001);X-Message-Delivery: Vj0xLjE7dXM9MDtsPTA7YT0wO0Q9MTtHRD0xO1NDTD0zX-Microsoft-Antispam-Message-Info:=?utf-8?B?NTIzdUViVStCS2pkTUtMN1krbDRpUWNDR3l5SHdLZGhzK1dWZXJGTTJtMTdH?==?utf-8?B?aTJRWXR1Q25XWmRmWXFEU2xuYXlNcjhhMHdFeDNUV09lemZUblU2YzR0dHNI?==?utf-8?B?bnhUckY0ZWdvdUVZM0VaTmwvdjREa2p1OUYvaG1XNjZzbFZhMlh2a3EwUCtm?==?utf-8?B?TlJTYmIvVjZld0ZCQ1ZBeFJIZnRnTFp6UWRaS3lPN05maXQ4SDRHem1wcjU2?==?utf-8?B?anB2dGFSMWV3c2MvemhmTm4zUVltWXRzUVJxSEM3eFNXMVpPUEZoUmZzZnVX?==?utf-8?B?RXVpa3VnTFdGdnJVTS9aSWRXUElhV29JOXB2ZTl4eko4ejhmRmJ6YlY4T1h5?==?utf-8?B?Mk1CK1BqQmk5SDZxci9PaVVsRVI1QitZc3VVdW9JbENCU2hsVGduMThFUjhM?==?utf-8?B?cFpqVmUzcm1STzFOZUh0eUM3NytGdC84THQ5R0wyamxNS3kxSS9ZSzB1dG5C?==?utf-8?B?ZUFodTlRN2pGay9VRDB2T1JwdDVTQWM2K1JScXJQaHMzNk43bUR3UTBrMmlO?==?utf-8?B?NFZLV0VBZitYVXRoTkRvZ04wb09SS0k2M0lIcUJVOWNHTWsxMFU4dkt0Ukpm?==?utf-8?B?K3B5cFJmSlVDZkJPTVJEamE4a2ZFRjFteUQzVXNlS1VOTlczTys2K3ovOW1B?==?utf-8?B?MFhseENRYlJiODQzUW1NaXNneDRTWTF1cWZhemRHb2Iwc2VkUkc1aEhzQ3RI?==?utf-8?B?ZFBkMTNjLzJlYkNmQ1l5OEFMaStZTkJBb1pDN2R4WWVDdFdJcTlqZ1p3TGV4?==?utf-8?B?TGNVWUF0ZkVBaldESnhldVFkVDZabEZ2ZlMyZGJMRFh3eDhlVUJXOE5JL0o5?==?utf-8?B?REdkaE45UG51VExCTDN4bjdKdDhzSXB0QXNYQWIzQlh1SmtiTVRCK1FQYUt5?==?utf-8?B?OXpmTngrMElUYkw3Mkc3dkV1enhKYmhPUXEvcm1PdEtQQ21NcW5nL0p5WTZZ?==?utf-8?B?UExOZ2c0b0RicERMSWZLckRFK2xMSnVKMWwwL1N1Qm10VkhNY3FFb0o1VERu?==?utf-8?B?ZFF3MzFOL3Z5Ui9FZFVzSkZmSHdvYXp5Sno1aHh2NkllbmkwSlgybUFISWZ4?==?utf-8?B?aE9iMGVPa0NwcWZmL2VHck1XTG9XaGpuaC9XWWx6TUhlS1V0cUhqMXQ4dDJv?==?utf-8?B?UHk2RmNWS3RpOGthYVk2aWdVOHVML29SYkVvSTd3MHFhaEFva3RTR3BKOTA2?==?utf-8?B?UTVRcmE4RUN4Wk42ZEtiekVwSUQrMlAwU1ZZeVhKMTd6S1RtVzB3RU9aYmZn?==?utf-8?B?amcrTHg4YzBwYnJpd2hJS3NaR0ZuQURRWjFaUEVXc3gyRWR6WWlxcSsrZnZr?==?utf-8?B?YmJQaDhNOC9TdTFpVnlFZWh4Nml5K3kvbzdENGt2U2hVT0ZTSWtrNXlZWk5a?==?utf-8?B?aURYM1F5WjVFYnJ1RXpLUTNxdjNTdW1Pd0RFMnhoVHIwQ2p0cE5Fbkc1bHFH?==?utf-8?B?YmttWW5Zb3ZLQ0RqT1dqVFRGUFRUY2NqaWF1ZFFWTmthTkhtU3ZuTVYxTWZS?==?utf-8?B?Vzc3S0VNUjFEZ1gwU2p5Ti8vcVNFOXhxK2U3UzY5cHRqZzFtSjVyVFhxWEI5?==?utf-8?B?eSt4Q3ZJQkQ5VjMrR2NTSnFaZi9ZWTdSTFp6aW4zWlRSVmc0TElmcnd4MjIv?==?utf-8?B?MisxV1dxR3pxT2pZSzFWa0U4Y3poUTZpdTY1NnBnVVNPNE8xMlFMNlVYUmtQ?==?utf-8?B?eER3T3k5ZVFvdFpvYmFFRjN6NjBjMEFVMzhJWWZIM3I0Z0UzcnU4d0NQSHJl?==?utf-8?B?MnQ0ZlJQd2VzcHgwME8yTzBKUG5RU0MzK3VhcVNXb0Q2TzhtSndEUFNxSkUz?==?utf-8?B?eUNoQ000c3htYTBWajlnK1hGN2kwSTVybjl3Mm85OFp5N2ZvejMwdjlFZHYz?==?utf-8?B?ZFp2YWpRYXA0ME5MM2RiVjhlYkM3M21kcFpaWEhTZzlNNFltUWhHMFIySldk?==?utf-8?B?UXRHQ3g0cUEvRitPajk3dE9OY29nYTNON2FsSmg5UWpaNGhnVDQ1UTNzT3Bv?==?utf-8?B?YnFtbW8ySE9XVFhTamsxdzJYS2xUVHd0VDF5VEVKaHhIK3JBRE5iOFlhUC9D?==?utf-8?B?bVFkLzVoS1dFSUxYQm1zS0NXT1ZwaXczazFYZkl4WUgrZlJxQlVxWWtrdVFU?==?utf-8?B?bk9tamgxczJWU0RzeFU3dkVtMkFNcktyTHR4a25UR0NjS0NzbjV2bm95VWFt?==?utf-8?B?REh4L1lBUlJiaXRvajd5dXlaSXJCdWVuZXlDT3JjQmdPWlBsamlNaVcvbmln?==?utf-8?B?YWNhTC9lVmVBNEFQTUpYNDVxZzREejNPWFN2cGVNUHFmSSsrR1EwcHpNUy8v?==?utf-8?B?Y2E2UVdkeWZUL0hnZThsYnRWMGNZL09hZlB0V2QzZENoMDlSV1llOEFidXNm?==?utf-8?B?R1pkSEZYeks3RUovNXhxaHlzcU1RUVFIYkY4c3A4bDc1d2NMTlhFZFdYdldk?==?utf-8?B?VWFlUlo2SWpBbFdiNG9rTFF3Yk02Z000TzdyQzdxNmZ0SklkWHNzSDhMT0pH?==?utf-8?B?VmdUSzl6WWt4bXFNcjRpRGtIWHozbS9BWm1lWDNoZUNiNFhmaXYzZS9kVFpW?==?utf-8?B?WElnbDJ1UzFINUE0QVlBZi9WWXBnai80NmRqMlVRYzkrbGl4VzdCY0tsU1Vz?==?utf-8?B?OXZSNWVqT1ZhN2ZkMHNxTi9xYmhuNWlKUTZBWUp1Nm1FNk1YVkJZbXNJa2ht?==?utf-8?B?SFgxQ0dsV0hYajJ1cFZzTVNSbXdueFNmYlpleCtFQ2VtQ1FHcDQzZC9sd2ts?==?utf-8?B?L0tybHU1M012VTN4dTQyQ2lYWjRVZUhJMUVEcHhtSUhxMkRKOFpXb0xvaGJB?==?utf-8?B?PT0=?=MIME-Version: 1.0
```

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
