# Prompt
Analyse the following email trace and message source.

- Determine if this email is a phishing attack.
- Break down the trail of email routing into segments so I can understand where the email originated and how it got relayed all the way to my Inbox.

Avoid using semantic compression in your response.\
Display your entire response in a single reusable Markdown-style writing block which I can directly save as a .md file.

```none
Received: from PU4P216MB1957.KORP216.PROD.OUTLOOK.COM (2603:1096:301:108::11)
 by SE2P216MB3393.KORP216.PROD.OUTLOOK.COM with HTTPS; Mon, 29 Jun 2026
 18:56:38 +0000
Received: from DS7P222CA0006.NAMP222.PROD.OUTLOOK.COM (2603:10b6:8:2e::23) by
 PU4P216MB1957.KORP216.PROD.OUTLOOK.COM (2603:1096:301:108::11) with Microsoft
 SMTP Server (version=TLS1_2, cipher=TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384) id
 15.21.159.19; Mon, 29 Jun 2026 18:56:36 +0000
Received: from DM2PEPF00003FC9.namprd04.prod.outlook.com
 (2603:10b6:8:2e:cafe::6a) by DS7P222CA0006.outlook.office365.com
 (2603:10b6:8:2e::23) with Microsoft SMTP Server (version=TLS1_3,
 cipher=TLS_AES_256_GCM_SHA384) id 15.21.159.19 via Frontend Transport; Mon,
 29 Jun 2026 18:56:35 +0000
Authentication-Results: spf=pass (sender IP is 212.227.126.133)
 smtp.mailfrom=jci.com; dkim=none (message not signed)
 header.d=none;dmarc=pass action=none header.from=jci.com;compauth=pass
 reason=100
Received-SPF: Pass (protection.outlook.com: domain of jci.com designates
 212.227.126.133 as permitted sender) receiver=protection.outlook.com;
 client-ip=212.227.126.133; helo=mout.kundenserver.de; pr=E
Received: from mout.kundenserver.de (212.227.126.133) by
 DM2PEPF00003FC9.mail.protection.outlook.com (10.167.23.27) with Microsoft
 SMTP Server (version=TLS1_3, cipher=TLS_AES_256_GCM_SHA384) id 15.21.181.6
 via Frontend Transport; Mon, 29 Jun 2026 18:56:34 +0000
X-IncomingTopHeaderMarker: OriginalChecksum:318D99F7CCE9F6836C461E7CB6FD3469D93911F9994C287EE3350557403E1E87;UpperCasedChecksum:770D5B8626B9466282E1006FE2C4A7FA3E91C738C584A0B3CB700B20AEE03E72;SizeAsReceived:2846;Count:14
Received: from winhex19beeu31.wineu.mail ([10.72.140.28]) by
 mri.eue.server.lan (mrieue002 [10.74.32.56]) with ESMTPS (Nemesis) id
 1Mi4BN-1xHzYu1Ht3-00Zm6Q for <miguelcadena@hotmail.com>; Mon, 29 Jun 2026
 20:56:33 +0200
Received: from 1cbdb02c.biz (10.72.140.250) by winhex19beeu31.wineu.mail
 (10.72.140.28) with Microsoft SMTP Server (version=TLS1_2,
 cipher=TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384) id 15.2.2562.43; Mon, 29 Jun
 2026 20:56:32 +0200
Content-Type: multipart/mixed;
	boundary="===============3326699882436199059=="
From: Miguelcadena via Clixsign <john.mccormick@jci.com>
To: <miguelcadena@hotmail.com>
Subject: Signature requested on Eft-WLTR-383927
Date: Mon, 29 Jun 2026 18:56:31 +0000
Message-ID: <178275939131.6924.4781492314516302447@jci.com>
X-Accept-Language: en-us, en
Return-Path: john.mccormick@jci.com
X-ClientProxiedBy: winhex19beeu34.wineu.mail (10.72.140.159) To
 winhex19beeu31.wineu.mail (10.72.140.28)
X-Spam-Flag: NO
UI-OutboundReport: notjunk:1;M01:P0:OpHycVEhW+w=;jRXXjR4xuUOU1Z9G+w2PNBtODic
 eCi1e47QTTxAfBOi5/3B5qluDuTopfkzOHrzormlzab+65X+JL+U39HOW3eq0dX63P8TKhpvQ
 R+gXSI0QaMtKjfVL6dR5vVg4GyQw2Zqp9LC7tjDVlyGTxu8rI4c1G1/ePpZ/7n2IaTuMuWPtf
 q4Z+ybwoJoo/CgDexOj7DiM1rl9+sKYIz9Mk/426ldEuIGAN+Q08T+iOVF537diE8+MVz9FVp
 AlwYckwZ86DL4TqVOPGVyaAVAMq+nGlIGBVR4dZhKCMcxIR1LoNtwSXjkwqZ1vOs+wlwrKlEP
 sp2s+MLUk9nqpQsnto1glCPjflvjz8m0z3tvDCPbej84glfS1CUwZoTIbeY2FK1Ys7vJnZ/gk
 tmEjuiLLW0pLkexp7B7ck5rFErRXVIgnoSoT5XdG8JkwBmOBwFQjuqjGOD2bPbyGCIsl6q3Zs
 EnQfBrjQkMFdw2L727M16cjSpooC95qwd43GqGpsLfRtkuua0jpt0ZnP0CWU+/sBpUcKgmTn+
 iBmPS/kOcrsLHNC7KmB9454srg5LdwxW/qypwB6mseeKMKsgcVxXwz6sPVYViFUpohlYgRnUh
 0SZiJ/sCl5nccgUU9qRqFb0UDro3iG6dBh68hZhc+LAG5E6dBahZAxscMpe6/MuMJ3fxI8BTy
 EPa4ecQjU2qhgHseGpIAtouTopMfKeYRnRYKhkHKEVyYgpm3wKq3RqcoTIiCJ6tklC+1FZ0He
 oADenDuEUmzML2LaTrYQnpM6an0WZ25bf/D7XbcFAGNhF1ZyeYZglKWQzCZRNzu9kjDzbU8ww
 5GxitKHIt19Td0890Fs81fBovslarCCrXv9VRCjmr0rS2RLpWLXyfJfJ4cfBSFJBN72t/MBZb
 +KMbzoh8Qso57Mbl4sPTVgpaLyP/bhgyx1SXiQWSIlyOXGRP5k92ij6E+tmEem8k6sYmxAwAz
 AsL5DeQ2qF7qEf3MCE2tOFDEcBbixMKmbIK2u2vk9IV69LCwrpA84599gS6bgVo0Xj5YnEC2c
 Nl4J16Ooxsr27dgETN8/m+OJcttsXSYSzTwLWmLMjADKI5l6LxMeTRDrP1M7ZQRW2dzU+LkZ6
 y9iBRcYZ8p44DPyGKZ2Fd10ZUBEb2uLxsSyN2s6VdAzZRK0LKKM+eV15+P+YDyYc9R/tHtedm
 /B3UbK+oVzkldLHAT9lW+GuglNwSkqBy4dRec8RIyhbR5dSeRY1DFvzrJIUvMJ5Kw5TJ506TM
 7K0LNyl1U1GXbPMW2uuYq51QPiAJl+VtdCAh039WuBkGBUFRLKvc+Qz0ISvQIGpbLfLN2fuYB
 y1SImjKbUyNmTtVqCBlicoNGFVT5RLSBrSEzVlmG5PnsbdJOARU2uLqP+/4W9CSzXqJvcHZWR
 fOSMUKqZqzEni7oUb1/8XgSQu6NCGwcPz9J0Ly+IcnRfTJuDsFByrOqok+AAnHu/thCaBL8kf
 x8SYvvJWdDitAb1m/HKOkNeYHVajixvqp612+pxhTyfuU/C92FcMSc+50Da94lEJRSllOliag
 tu8g/DiVTU1sdolpyWxl5JeTdP6yXViL8kzpa28qHioFedRk/iluxuv6LEALO6aMrJ+RXJ76l
 PHlqhtf61/nhmMUX7MObtVBTYsWecGirnstu4mADhxL2HbKPlBKVvulfT5eP2wNVV8V9xi+AM
 z8wnvY8f9rizw/euLuQhqA
X-IncomingHeaderCount: 14
X-MS-Exchange-Organization-ExpirationStartTime: 29 Jun 2026 18:56:34.9072
 (UTC)
X-MS-Exchange-Organization-ExpirationStartTimeReason: OriginalSubmit
X-MS-Exchange-Organization-ExpirationInterval: 1:00:00:00.0000000
X-MS-Exchange-Organization-ExpirationIntervalReason: OriginalSubmit
X-MS-Exchange-Organization-Network-Message-Id: 5187b39b-3968-46a4-4d23-08ded610243e
X-EOPAttributedMessage: 0
X-EOPTenantAttributedMessage: 84df9e7f-e9f6-40af-b435-aaaaaaaaaaaa:0
X-MS-Exchange-Organization-MessageDirectionality: Incoming
X-MS-PublicTrafficType: Email
X-MS-TrafficTypeDiagnostic: DM2PEPF00003FC9:EE_|PU4P216MB1957:EE_|SE2P216MB3393:EE_
X-MS-Exchange-Organization-AuthSource: DM2PEPF00003FC9.namprd04.prod.outlook.com
X-MS-Exchange-Organization-AuthAs: Anonymous
X-MS-UserLastLogonTime: 6/29/2026 6:53:22 PM
X-MS-Office365-Filtering-Correlation-Id: 5187b39b-3968-46a4-4d23-08ded610243e
X-MS-Exchange-EOPDirect: true
X-Sender-IP: 212.227.126.133
X-SID-PRA: JOHN.MCCORMICK@JCI.COM
X-SID-Result: PASS
X-MS-Exchange-Organization-SCL: 1
X-Microsoft-Antispam: BCL:0;ARA:1444111002|7120799021|5139299004|970799063|9400799043|10300799038|1680799066|4089299007|1131999019|60050799012|9000799056|70100799019|30041999003|18021999003|6022199012|1602099012|4302099013|3412199025|8011999015|1370799030|1360799030|1380799030|440099028|26104999009;
X-MS-Exchange-CrossTenant-OriginalArrivalTime: 29 Jun 2026 18:56:34.3776
 (UTC)
X-MS-Exchange-CrossTenant-Network-Message-Id: 5187b39b-3968-46a4-4d23-08ded610243e
X-MS-Exchange-CrossTenant-Id: 84df9e7f-e9f6-40af-b435-aaaaaaaaaaaa
X-MS-Exchange-CrossTenant-AuthSource: DM2PEPF00003FC9.namprd04.prod.outlook.com
X-MS-Exchange-CrossTenant-AuthAs: Anonymous
X-MS-Exchange-CrossTenant-FromEntityHeader: Internet
X-MS-Exchange-CrossTenant-RMS-PersistedConsumerOrg: 00000000-0000-0000-0000-000000000000
X-MS-Exchange-Transport-CrossTenantHeadersStamped: PU4P216MB1957
X-MS-Exchange-Transport-EndToEndLatency: 00:00:03.7181407
X-MS-Exchange-Processed-By-BccFoldering: 15.21.0159.018
X-Microsoft-Antispam-Mailbox-Delivery:
	ucf:0;jmr:0;ex:0;auth:1;dest:I;ENG:(5062000311)(920221119095)(90000117)(920221120095)(90005022)(91005020)(91035115)(9050020)(9100341)(944500132)(2008001181)(2008121020)(4810010)(4910033)(9575002)(10195002)(9320005)(120001);
X-Message-Delivery: Vj0xLjE7dXM9MDtsPTA7YT0wO0Q9MTtHRD0xO1NDTD0z
X-Microsoft-Antispam-Message-Info:
	=?utf-8?B?NTIzdUViVStCS2pkTUtMN1krbDRpUWNDR3l5SHdLZGhzK1dWZXJGTTJtMTdH?=
 =?utf-8?B?aTJRWXR1Q25XWmRmWXFEU2xuYXlNcjhhMHdFeDNUV09lemZUblU2YzR0dHNI?=
 =?utf-8?B?bnhUckY0ZWdvdUVZM0VaTmwvdjREa2p1OUYvaG1XNjZzbFZhMlh2a3EwUCtm?=
 =?utf-8?B?TlJTYmIvVjZld0ZCQ1ZBeFJIZnRnTFp6UWRaS3lPN05maXQ4SDRHem1wcjU2?=
 =?utf-8?B?anB2dGFSMWV3c2MvemhmTm4zUVltWXRzUVJxSEM3eFNXMVpPUEZoUmZzZnVX?=
 =?utf-8?B?RXVpa3VnTFdGdnJVTS9aSWRXUElhV29JOXB2ZTl4eko4ejhmRmJ6YlY4T1h5?=
 =?utf-8?B?Mk1CK1BqQmk5SDZxci9PaVVsRVI1QitZc3VVdW9JbENCU2hsVGduMThFUjhM?=
 =?utf-8?B?cFpqVmUzcm1STzFOZUh0eUM3NytGdC84THQ5R0wyamxNS3kxSS9ZSzB1dG5C?=
 =?utf-8?B?ZUFodTlRN2pGay9VRDB2T1JwdDVTQWM2K1JScXJQaHMzNk43bUR3UTBrMmlO?=
 =?utf-8?B?NFZLV0VBZitYVXRoTkRvZ04wb09SS0k2M0lIcUJVOWNHTWsxMFU4dkt0Ukpm?=
 =?utf-8?B?K3B5cFJmSlVDZkJPTVJEamE4a2ZFRjFteUQzVXNlS1VOTlczTys2K3ovOW1B?=
 =?utf-8?B?MFhseENRYlJiODQzUW1NaXNneDRTWTF1cWZhemRHb2Iwc2VkUkc1aEhzQ3RI?=
 =?utf-8?B?ZFBkMTNjLzJlYkNmQ1l5OEFMaStZTkJBb1pDN2R4WWVDdFdJcTlqZ1p3TGV4?=
 =?utf-8?B?TGNVWUF0ZkVBaldESnhldVFkVDZabEZ2ZlMyZGJMRFh3eDhlVUJXOE5JL0o5?=
 =?utf-8?B?REdkaE45UG51VExCTDN4bjdKdDhzSXB0QXNYQWIzQlh1SmtiTVRCK1FQYUt5?=
 =?utf-8?B?OXpmTngrMElUYkw3Mkc3dkV1enhKYmhPUXEvcm1PdEtQQ21NcW5nL0p5WTZZ?=
 =?utf-8?B?UExOZ2c0b0RicERMSWZLckRFK2xMSnVKMWwwL1N1Qm10VkhNY3FFb0o1VERu?=
 =?utf-8?B?ZFF3MzFOL3Z5Ui9FZFVzSkZmSHdvYXp5Sno1aHh2NkllbmkwSlgybUFISWZ4?=
 =?utf-8?B?aE9iMGVPa0NwcWZmL2VHck1XTG9XaGpuaC9XWWx6TUhlS1V0cUhqMXQ4dDJv?=
 =?utf-8?B?UHk2RmNWS3RpOGthYVk2aWdVOHVML29SYkVvSTd3MHFhaEFva3RTR3BKOTA2?=
 =?utf-8?B?UTVRcmE4RUN4Wk42ZEtiekVwSUQrMlAwU1ZZeVhKMTd6S1RtVzB3RU9aYmZn?=
 =?utf-8?B?amcrTHg4YzBwYnJpd2hJS3NaR0ZuQURRWjFaUEVXc3gyRWR6WWlxcSsrZnZr?=
 =?utf-8?B?YmJQaDhNOC9TdTFpVnlFZWh4Nml5K3kvbzdENGt2U2hVT0ZTSWtrNXlZWk5a?=
 =?utf-8?B?aURYM1F5WjVFYnJ1RXpLUTNxdjNTdW1Pd0RFMnhoVHIwQ2p0cE5Fbkc1bHFH?=
 =?utf-8?B?YmttWW5Zb3ZLQ0RqT1dqVFRGUFRUY2NqaWF1ZFFWTmthTkhtU3ZuTVYxTWZS?=
 =?utf-8?B?Vzc3S0VNUjFEZ1gwU2p5Ti8vcVNFOXhxK2U3UzY5cHRqZzFtSjVyVFhxWEI5?=
 =?utf-8?B?eSt4Q3ZJQkQ5VjMrR2NTSnFaZi9ZWTdSTFp6aW4zWlRSVmc0TElmcnd4MjIv?=
 =?utf-8?B?MisxV1dxR3pxT2pZSzFWa0U4Y3poUTZpdTY1NnBnVVNPNE8xMlFMNlVYUmtQ?=
 =?utf-8?B?eER3T3k5ZVFvdFpvYmFFRjN6NjBjMEFVMzhJWWZIM3I0Z0UzcnU4d0NQSHJl?=
 =?utf-8?B?MnQ0ZlJQd2VzcHgwME8yTzBKUG5RU0MzK3VhcVNXb0Q2TzhtSndEUFNxSkUz?=
 =?utf-8?B?eUNoQ000c3htYTBWajlnK1hGN2kwSTVybjl3Mm85OFp5N2ZvejMwdjlFZHYz?=
 =?utf-8?B?ZFp2YWpRYXA0ME5MM2RiVjhlYkM3M21kcFpaWEhTZzlNNFltUWhHMFIySldk?=
 =?utf-8?B?UXRHQ3g0cUEvRitPajk3dE9OY29nYTNON2FsSmg5UWpaNGhnVDQ1UTNzT3Bv?=
 =?utf-8?B?YnFtbW8ySE9XVFhTamsxdzJYS2xUVHd0VDF5VEVKaHhIK3JBRE5iOFlhUC9D?=
 =?utf-8?B?bVFkLzVoS1dFSUxYQm1zS0NXT1ZwaXczazFYZkl4WUgrZlJxQlVxWWtrdVFU?=
 =?utf-8?B?bk9tamgxczJWU0RzeFU3dkVtMkFNcktyTHR4a25UR0NjS0NzbjV2bm95VWFt?=
 =?utf-8?B?REh4L1lBUlJiaXRvajd5dXlaSXJCdWVuZXlDT3JjQmdPWlBsamlNaVcvbmln?=
 =?utf-8?B?YWNhTC9lVmVBNEFQTUpYNDVxZzREejNPWFN2cGVNUHFmSSsrR1EwcHpNUy8v?=
 =?utf-8?B?Y2E2UVdkeWZUL0hnZThsYnRWMGNZL09hZlB0V2QzZENoMDlSV1llOEFidXNm?=
 =?utf-8?B?R1pkSEZYeks3RUovNXhxaHlzcU1RUVFIYkY4c3A4bDc1d2NMTlhFZFdYdldk?=
 =?utf-8?B?VWFlUlo2SWpBbFdiNG9rTFF3Yk02Z000TzdyQzdxNmZ0SklkWHNzSDhMT0pH?=
 =?utf-8?B?VmdUSzl6WWt4bXFNcjRpRGtIWHozbS9BWm1lWDNoZUNiNFhmaXYzZS9kVFpW?=
 =?utf-8?B?WElnbDJ1UzFINUE0QVlBZi9WWXBnai80NmRqMlVRYzkrbGl4VzdCY0tsU1Vz?=
 =?utf-8?B?OXZSNWVqT1ZhN2ZkMHNxTi9xYmhuNWlKUTZBWUp1Nm1FNk1YVkJZbXNJa2ht?=
 =?utf-8?B?SFgxQ0dsV0hYajJ1cFZzTVNSbXdueFNmYlpleCtFQ2VtQ1FHcDQzZC9sd2ts?=
 =?utf-8?B?L0tybHU1M012VTN4dTQyQ2lYWjRVZUhJMUVEcHhtSUhxMkRKOFpXb0xvaGJB?=
 =?utf-8?B?PT0=?=
MIME-Version: 1.0

--===============3326699882436199059==
Content-Type: multipart/alternative;
	boundary="===============7808026097302001640=="

--===============7808026097302001640==
Content-Type: text/plain; charset="utf-8"
Content-Transfer-Encoding: quoted-printable















NOTIFICATION=20=2029/Jun/2026
































Your=20Electronic=20Signature=20Is=20Requested


You=20are=20signer=201=20of=203=20on=20this=20document



Please=20click=20the=20link=20below=20to=20complete=20the=20document.=20If=
=20you=20have=20any=20questions=20please=20consult=20your=20representative.





REVIEW
=20&amp;=20SIGN=20NOW




















Do=20Not=20Share

This=20email=20contains=20a=20secure=20link=20to=20Clixsign.=20Please=20do=
=20not=20share=20this=20email,=20link,=20or=20access=20code=20with=20others.













Questions?

If=20you=20have=20any=20questions=20or=20comments=20about=20this=20document=
=20or=20Clixsign,=20please=20contact&nbsp;James=20Law,=20LLC


















Clixsign=20is=20an=20Electronic=20Signature=20Service.=20The=20information=
=20contained=20in=20this=20transmission=20is=20confidential
=20and=20is=20intended=20only=20for=20the=20use=20of=20the=20individual=20o=
r=20entity=20named=20above.=20If=20the=20reader=20of=20this=20message=20is=
=20not=20the=20intended=20recipient,=20please=20discard=20and=20delete=20th=
is=20message.














































This=20message=20is=20intended=20for=20delviery=20to=20miguelcadena@hotmail=
.com






























--===============7808026097302001640==
Content-Type: text/html
Content-Transfer-Encoding: quoted-printable

<html>
<head>
<meta=20http-equiv=3D"Content-Type"=20content=3D"text/html;=20charset=3Dutf=
-8">
</head>
<body=20style=3D"overflow-wrap:=20break-word;=20-webkit-nbsp-mode:=20space;=
=20line-break:=20after-white-space;">

<div=20style=3D"margin:=200px=20auto;=20max-width:=20600px;=20background:=
=20rgb(255,=20255,=20255);">
<table=20role=3D"presentation"=20cellpadding=3D"0"=20cellspacing=3D"0"=20al=
ign=3D"center"=20border=3D"0"=20style=3D"border-collapse:=20collapse;=20fon=
t-size:=200px;=20width:=20600px;=20background:=20rgb(255,=20255,=20255);">
<tbody>
<tr>
<td=20style=3D"border-collapse:=20collapse;=20text-align:=20center;=20verti=
cal-align:=20top;=20border-bottom-width:=201px;=20border-bottom-style:=20so=
lid;=20border-bottom-color:=20rgb(234,=20234,=20234);=20direction:=20ltr;=
=20font-size:=200px;=20padding:=200px;">
<div=20style=3D"cursor:=20auto;=20color:=20rgb(102,=20102,=20102);=20font-f=
amily:=20Arial,=20sans-serif;=20font-size:=2012px;=20font-weight:=20400;=20=
line-height:=2022px;=20text-align:=20left;">
<div=20style=3D"padding:=2015px=2025px=2040px;"><a=20class=3D"logo"=20href=
=3D"http://www.clixsign.com/"=20style=3D"color:=20rgb(247,=20231,=2097);=20=
text-decoration:=20none;=20float:=20left;=20margin-bottom:=2010px;"><img=20=
src=3D"https://ci3.googleusercontent.com/meips/ADKq_NYcexePFnU_PXVu6te1K3nR=
UblrLpjgkw2Wpjocqhfb8MezswciV-RPoW5FF9nuvqUIbLP_a4wEwngbhS3AlBTqt6ghCJCFTO4=
ZGuzDcSI9kt0YciUa-F6rbW7skonfdgO6YOg=3Ds0-d-e1-ft#https://dpp-publicassets.=
s3.amazonaws.com/graphics/logos/clixsign/clixsign.png"=20width=3D"100px"=20=
style=3D"border:=200px;=20height:=20auto;=20line-height:=2012px;=20outline:=
=200px;=20text-decoration:=20none;"></a>
<p=20style=3D"display:=20block;=20margin:=205px=200px=2013px;=20float:=20ri=
ght;=20color:=20rgb(153,=20153,=20153);=20text-transform:=20uppercase;=20fo=
nt-size:=2011px;">
NOTIFICATION=20=2029/Jun/2026</p>
</div>
</div>
</td>
</tr>
</tbody>
</table>
</div>
<div=20style=3D"margin:=200px=20auto;=20max-width:=20600px;=20background:=
=20rgb(255,=20255,=20255);">
<table=20role=3D"presentation"=20cellpadding=3D"0"=20cellspacing=3D"0"=20al=
ign=3D"center"=20border=3D"0"=20style=3D"border-collapse:=20collapse;=20fon=
t-size:=200px;=20width:=20600px;=20background:=20rgb(255,=20255,=20255);">
<tbody>
<tr>
<td=20style=3D"border-collapse:=20collapse;=20text-align:=20center;=20verti=
cal-align:=20top;=20direction:=20ltr;=20font-size:=200px;=20padding:=200px;=
">
<table=20role=3D"presentation"=20cellpadding=3D"0"=20cellspacing=3D"0"=20al=
ign=3D"center"=20border=3D"0"=20style=3D"border-collapse:=20collapse;=20bor=
der-spacing:=200px;">
<tbody>
<tr>
<td=20style=3D"border-collapse:=20collapse;=20width:=20600px;"><img=20alt=
=3D""=20height=3D"auto"=20src=3D"https://ci3.googleusercontent.com/meips/AD=
Kq_NapcKskvzTdfKWEY2-iQzJJwHfdEGQsnGFdPZeyOVXhQWfKeACB8d9B_bgA12sc7ApaYvd6K=
2FDCT_qR9cde2yyKTagLD6iSUQ3tyI-IiPRLZcPfczWbeKtkTCWbvkcOOb0=3Ds0-d-e1-ft#ht=
tps://dpp-publicassets.s3.amazonaws.com/graphics/photos/cx/cx-header-2.jpg"=
=20width=3D"600"=20style=3D"border:=20medium;=20height:=20auto;=20line-heig=
ht:=2013px;=20outline:=200px;=20text-decoration:=20none;=20border-radius:=
=200px;=20display:=20block;=20font-size:=2013px;=20width:=20600px;"></td>
</tr>
</tbody>
</table>
</td>
</tr>
</tbody>
</table>
</div>
<div=20style=3D"margin:=200px=20auto;=20max-width:=20600px;=20background:=
=20rgb(255,=20255,=20255);">
<table=20role=3D"presentation"=20cellpadding=3D"0"=20cellspacing=3D"0"=20al=
ign=3D"center"=20border=3D"0"=20style=3D"border-collapse:=20collapse;=20fon=
t-size:=200px;=20width:=20600px;=20background:=20rgb(255,=20255,=20255);">
<tbody>
<tr>
<td=20style=3D"border-collapse:=20collapse;=20text-align:=20center;=20verti=
cal-align:=20top;=20direction:=20ltr;=20font-size:=200px;=20padding:=2050px=
=200px=20100px;">
<div=20style=3D"cursor:=20auto;=20color:=20rgb(102,=20102,=20102);=20font-f=
amily:=20Arial,=20sans-serif;=20font-size:=2012px;=20font-weight:=20400;=20=
line-height:=2022px;=20text-align:=20left;">
<h1=20class=3D"email-title"=20style=3D"font-family:=20Verdana,=20Arial,=20s=
ans-serif;=20font-size:=2021px;=20color:=20rgb(46,=2054,=2077);=20font-weig=
ht:=20200;=20text-align:=20center;=20line-height:=2028px;=20letter-spacing:=
=20-1.25px;">
<strong></strong><br>
Your=20Electronic=20Signature=20Is=20Requested<br>
</h1>
<h5=20style=3D"text-align:=20center;=20font-size:=201em;=20color:=20rgb(153=
,=20153,=20153);=20padding:=200px;=20display:=20block;=20margin:=200px;=20f=
ont-weight:=20300;">
You=20are=20signer=201=20of=203=20on=20this=20document</h5>
</div>
<div=20style=3D"cursor:=20auto;=20color:=20rgb(102,=20102,=20102);=20font-f=
amily:=20Arial,=20sans-serif;=20font-size:=2012px;=20font-weight:=20400;=20=
line-height:=2022px;=20text-align:=20left;">
<div=20style=3D"width:=20390px;=20margin:=2020px=20auto=2035px;=20text-alig=
n:=20center;=20line-height:=2021px;=20font-size:=2014px;=20border-top-width=
:=201px;=20border-top-style:=20solid;=20border-top-color:=20rgb(234,=20234,=
=20234);=20border-bottom-width:=201px;=20border-bottom-style:=20solid;=20bo=
rder-bottom-color:=20rgb(234,=20234,=20234);=20padding:=202em;">
Please=20click=20the=20link=20below=20to=20complete=20the=20document.=20If=
=20you=20have=20any=20questions=20please=20consult=20your=20representative.=
</div>
</div>
<table=20role=3D"presentation"=20cellpadding=3D"0"=20cellspacing=3D"0"=20al=
ign=3D"center"=20border=3D"0"=20style=3D"border-collapse:=20separate;">
<tbody>
<tr>
<td=20align=3D"center"=20valign=3D"middle"=20bgcolor=3D"#3fbfd0"=20style=3D=
"border-collapse:=20collapse;=20border:=20medium;=20border-radius:=204px;=
=20color:=20rgb(255,=20255,=20255);=20cursor:=20auto;=20padding:=2010px=202=
5px;">
<a=20href=3D"https://emea01safelinks-protection-documents-esign.pro"=20targ=
et=3D"_blank"=20style=3D"text-decoration:=20none;=20background:=20rgb(63,=
=20191,=20208);=20color:=20rgb(255,=20255,=20255);=20font-family:=20Ubuntu,=
=20Helvetica,=20Arial,=20sans-serif;=20font-size:=2021px;=20font-weight:=20=
600;=20line-height:=2025.200001px;=20text-transform:=20uppercase;=20margin:=
=200px;">REVIEW
=20&amp;=20SIGN=20NOW</a></td>
</tr>
</tbody>
</table>
</td>
</tr>
</tbody>
</table>
</div>
<div=20style=3D"margin:=200px=20auto;=20max-width:=20600px;=20background:=
=20rgb(250,=20250,=20250);">
<table=20role=3D"presentation"=20cellpadding=3D"0"=20cellspacing=3D"0"=20al=
ign=3D"center"=20border=3D"0"=20style=3D"border-collapse:=20collapse;=20fon=
t-size:=200px;=20width:=20600px;=20background:=20rgb(250,=20250,=20250);">
<tbody>
<tr>
<td=20style=3D"border-collapse:=20collapse;=20text-align:=20center;=20verti=
cal-align:=20top;=20border-width:=201px=201px=200px;=20border-style:=20soli=
d=20solid=20none;=20border-color:=20rgb(204,=20204,=20204)=20rgb(204,=20204=
,=20204)=20currentcolor;=20border-image:=20none;=20direction:=20ltr;=20font=
-size:=200px;=20padding:=2020px=200px;">
<div=20class=3D"mj-column-per-50=20outlook-group-fix"=20style=3D"width:=202=
99px;=20vertical-align:=20top;=20display:=20inline-block;=20direction:=20lt=
r;=20font-size:=2013px;=20text-align:=20left;">
<table=20role=3D"presentation"=20cellpadding=3D"0"=20cellspacing=3D"0"=20wi=
dth=3D"100%"=20border=3D"0"=20style=3D"border-collapse:=20collapse;">
<tbody>
<tr>
<td=20align=3D"left"=20style=3D"border-collapse:=20collapse;=20overflow-wra=
p:=20break-word;=20font-size:=200px;=20padding:=2010px=2025px;">
<div=20style=3D"cursor:=20auto;=20color:=20rgb(102,=20102,=20102);=20font-f=
amily:=20Arial,=20sans-serif;=20font-size:=2012px;=20font-weight:=20400;=20=
line-height:=2022px;=20text-align:=20left;">
<h3=20style=3D"color:=20rgb(51,=2051,=2051);=20font-size:=2021px;=20font-fa=
mily:=20Arial,=20sans-serif;=20font-weight:=20400;=20margin-bottom:=200px;">
Do=20Not=20Share</h3>
<p=20style=3D"display:=20block;=20margin:=200.5em=200px=2013px;=20color:=20=
rgb(102,=20102,=20102);=20line-height:=201.33;">
This=20email=20contains=20a=20secure=20link=20to=20Clixsign.=20Please=20do=
=20not=20share=20this=20email,=20link,=20or=20access=20code=20with=20others=
.</p>
</div>
</td>
</tr>
</tbody>
</table>
</div>
<div=20class=3D"mj-column-per-50=20outlook-group-fix"=20style=3D"width:=202=
99px;=20vertical-align:=20top;=20display:=20inline-block;=20direction:=20lt=
r;=20font-size:=2013px;=20text-align:=20left;">
<table=20role=3D"presentation"=20cellpadding=3D"0"=20cellspacing=3D"0"=20wi=
dth=3D"100%"=20border=3D"0"=20style=3D"border-collapse:=20collapse;">
<tbody>
<tr>
<td=20align=3D"left"=20style=3D"border-collapse:=20collapse;=20overflow-wra=
p:=20break-word;=20font-size:=200px;=20padding:=2010px=2025px;">
<div=20style=3D"cursor:=20auto;=20color:=20rgb(102,=20102,=20102);=20font-f=
amily:=20Arial,=20sans-serif;=20font-size:=2012px;=20font-weight:=20400;=20=
line-height:=2022px;=20text-align:=20left;">
<h3=20style=3D"color:=20rgb(51,=2051,=2051);=20font-size:=2021px;=20font-fa=
mily:=20Arial,=20sans-serif;=20font-weight:=20400;=20margin-bottom:=200px;">
Questions?</h3>
<p=20style=3D"display:=20block;=20margin:=200.5em=200px=2013px;=20color:=20=
rgb(102,=20102,=20102);=20line-height:=201.33;">
If=20you=20have=20any=20questions=20or=20comments=20about=20this=20document=
=20or=20Clixsign,=20please=20contact<span=20class=3D"Apple-converted-space"=
>&nbsp;</span><a=20href=3D""=20style=3D"text-decoration:=20none;=20color:=
=20rgb(63,=20191,=20208);">James=20Law,=20LLC</a></p>
</div>
</td>
</tr>
</tbody>
</table>
</div>
</td>
</tr>
</tbody>
</table>
</div>
<div=20style=3D"margin:=200px=20auto;=20max-width:=20600px;=20background:=
=20rgb(250,=20250,=20250);">
<table=20role=3D"presentation"=20cellpadding=3D"0"=20cellspacing=3D"0"=20al=
ign=3D"center"=20border=3D"0"=20style=3D"border-collapse:=20collapse;=20fon=
t-size:=200px;=20width:=20600px;=20background:=20rgb(250,=20250,=20250);">
<tbody>
<tr>
<td=20style=3D"border-collapse:=20collapse;=20text-align:=20center;=20verti=
cal-align:=20top;=20border:=201px=20solid=20rgb(204,=20204,=20204);=20direc=
tion:=20ltr;=20font-size:=200px;=20padding:=2020px=200px;">
<div=20style=3D"cursor:=20auto;=20color:=20rgb(102,=20102,=20102);=20font-f=
amily:=20Arial,=20sans-serif;=20font-size:=2012px;=20font-weight:=20400;=20=
line-height:=2022px;=20text-align:=20left;">
<div=20style=3D"display:=20block;=20margin:=200px=2025px;=20text-align:=20j=
ustify;=20line-height:=201.25;=20font-size:=2011px;=20color:=20rgb(153,=201=
53,=20153);">
Clixsign=20is=20an=20Electronic=20Signature=20Service.=20The=20information=
=20contained=20in=20this=20transmission=20is=20confidential
=20and=20is=20intended=20only=20for=20the=20use=20of=20the=20individual=20o=
r=20entity=20named=20above.=20If=20the=20reader=20of=20this=20message=20is=
=20not=20the=20intended=20recipient,=20please=20discard=20and=20delete=20th=
is=20message.</div>
</div>
</td>
</tr>
</tbody>
</table>
</div>
<div=20style=3D"margin:=200px=20auto;=20max-width:=20600px;=20background:=
=20rgb(48,=2062,=2072);">
<table=20role=3D"presentation"=20cellpadding=3D"0"=20cellspacing=3D"0"=20al=
ign=3D"center"=20border=3D"0"=20style=3D"border-collapse:=20collapse;=20fon=
t-size:=200px;=20width:=20600px;=20background:=20rgb(48,=2062,=2072);">
<tbody>
<tr>
<td=20style=3D"border-collapse:=20collapse;=20text-align:=20center;=20verti=
cal-align:=20top;=20direction:=20ltr;=20font-size:=200px;=20padding:=2015px=
=200px=200px;">
<div=20class=3D"mj-column-per-25=20outlook-group-fix"=20style=3D"width:=201=
50px;=20vertical-align:=20top;=20display:=20inline-block;=20direction:=20lt=
r;=20font-size:=2013px;=20text-align:=20left;">
<table=20role=3D"presentation"=20cellpadding=3D"0"=20cellspacing=3D"0"=20wi=
dth=3D"100%"=20border=3D"0"=20style=3D"border-collapse:=20collapse;">
<tbody>
<tr>
<td=20align=3D"left"=20style=3D"border-collapse:=20collapse;=20overflow-wra=
p:=20break-word;=20font-size:=200px;=20padding:=2010px=2025px;">
<div=20style=3D"cursor:=20auto;=20color:=20rgb(102,=20102,=20102);=20font-f=
amily:=20Arial,=20sans-serif;=20font-size:=2012px;=20font-weight:=20400;=20=
line-height:=2022px;=20text-align:=20left;">
<img=20class=3D"footer-logo"=20src=3D"https://ci3.googleusercontent.com/mei=
ps/ADKq_NYEgzNpwQ4kK_p7zfYNKxN6ghN7eibIFnjfXm8nbkSqjHNhyyOusz4Q1N5rZzkf29Gh=
_V2FJYRMvIsRLYT7z_yobxhl1AnsqVmE8i2MJxrDnAr5-BjNDC0gqjFYAGle3Coq-y9_NmlBhIo=
=3Ds0-d-e1-ft#https://dpp-publicassets.s3.amazonaws.com/graphics/logos/clix=
sign/clixsign-white.png"=20width=3D"100"=20style=3D"border:=200px;=20height=
:=20auto;=20line-height:=2012px;=20outline:=200px;=20text-decoration:=20non=
e;"></div>
</td>
</tr>
</tbody>
</table>
</div>
<div=20class=3D"mj-column-per-75=20outlook-group-fix"=20style=3D"width:=204=
50px;=20vertical-align:=20top;=20display:=20inline-block;=20direction:=20lt=
r;=20font-size:=2013px;=20text-align:=20left;">
<table=20role=3D"presentation"=20cellpadding=3D"0"=20cellspacing=3D"0"=20wi=
dth=3D"100%"=20border=3D"0"=20style=3D"border-collapse:=20collapse;">
<tbody>
</tbody>
</table>
</div>
</td>
</tr>
</tbody>
</table>
</div>
<div=20style=3D"margin:=200px=20auto;=20max-width:=20600px;=20background:=
=20rgb(48,=2062,=2072);">
<table=20role=3D"presentation"=20cellpadding=3D"0"=20cellspacing=3D"0"=20al=
ign=3D"center"=20border=3D"0"=20style=3D"border-collapse:=20collapse;=20fon=
t-size:=200px;=20width:=20600px;=20background:=20rgb(48,=2062,=2072);">
<tbody>
<tr>
<td=20style=3D"border-collapse:=20collapse;=20text-align:=20center;=20verti=
cal-align:=20top;=20direction:=20ltr;=20font-size:=200px;=20padding:=2015px=
=200px=200px;">
<div=20class=3D"mj-column-per-90=20outlook-group-fix"=20style=3D"width:=205=
40px;=20vertical-align:=20top;=20display:=20inline-block;=20direction:=20lt=
r;=20font-size:=2013px;=20text-align:=20left;">
<table=20role=3D"presentation"=20cellpadding=3D"0"=20cellspacing=3D"0"=20wi=
dth=3D"100%"=20border=3D"0"=20style=3D"border-collapse:=20collapse;=20borde=
r-bottom-width:=201px;=20border-bottom-style:=20solid;=20border-bottom-colo=
r:=20rgb(64,=2080,=2091);=20border-top-width:=201px;=20border-top-style:=20=
solid;=20border-top-color:=20rgb(64,=2080,=2091);">
<tbody>
<tr>
<td=20align=3D"left"=20style=3D"border-collapse:=20collapse;=20overflow-wra=
p:=20break-word;=20font-size:=200px;=20padding:=2010px=200px;">
<div=20style=3D"cursor:=20auto;=20color:=20rgb(255,=20255,=20255);=20font-f=
amily:=20Arial,=20sans-serif;=20font-size:=2012px;=20font-weight:=20400;=20=
line-height:=2022px;=20text-align:=20left;">
<div=20id=3D"footer-email-container">
<p=20style=3D"display:=20block;=20margin:=2013px=200px;">This=20message=20i=
s=20intended=20for=20delviery=20to=20miguelcadena@hotmail.com</p>
</div>
</div>
</td>
</tr>
</tbody>
</table>
</div>
</td>
</tr>
</tbody>
</table>
</div>
<div=20style=3D"margin:=200px=20auto;=20max-width:=20600px;=20background:=
=20rgb(48,=2062,=2072);">
<table=20role=3D"presentation"=20cellpadding=3D"0"=20cellspacing=3D"0"=20al=
ign=3D"center"=20border=3D"0"=20style=3D"border-collapse:=20collapse;=20fon=
t-size:=200px;=20width:=20600px;=20background:=20rgb(48,=2062,=2072);">
<tbody>
<tr>
<td=20style=3D"border-collapse:=20collapse;=20text-align:=20center;=20verti=
cal-align:=20top;=20direction:=20ltr;=20font-size:=200px;=20padding:=2020px=
=200px=2050px;">
</td>
</tr>
</tbody>
</table>
</div>
</div>
<img=20src=3D""=20alt=3D""=20width=3D"1"=20height=3D"1"=20border=3D"0"=20st=
yle=3D"border-style:=20none;=20border-color:=20currentcolor;=20border-image=
:=20none;=20line-height:=2012px;=20outline:=200px;=20text-decoration:=20non=
e;=20caret-color:=20rgb(0,=200,=200);=20font-family:=20Helvetica;=20font-si=
ze:=2012px;=20font-style:=20normal;=20font-variant-caps:=20normal;=20font-w=
eight:=20400;=20letter-spacing:=20normal;=20text-align:=20start;=20text-ind=
ent:=200px;=20text-transform:=20none;=20white-space:=20normal;=20word-spaci=
ng:=200px;=20-webkit-text-stroke-width:=200px;=20background-color:=20rgb(23=
4,=20234,=20234);=20border-width:=200px=20!important;=20height:=201px=20!im=
portant;=20width:=201px=20!important;=20margin:=200px=20!important;=20paddi=
ng:=200px=20!important;"><span=20style=3D"caret-color:=20rgb(0,=200,=200);=
=20font-family:=20Helvetica;=20font-size:=2012px;=20font-style:=20normal;=
=20font-variant-caps:=20normal;=20font-weight:=20400;=20letter-spacing:=20n=
ormal;=20text-align:=20start;=20text-indent:=200px;=20text-transform:=20non=
e;=20white-space:=20normal;=20word-spacing:=200px;=20-webkit-text-stroke-wi=
dth:=200px;=20background-color:=20rgb(234,=20234,=20234);=20text-decoration=
:=20none;=20float:=20none;=20display:=20inline=20!important;"></span></div>
</blockquote>
</div>
<br>
</body>
</html>

--===============7808026097302001640==--

--===============3326699882436199059==--
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
