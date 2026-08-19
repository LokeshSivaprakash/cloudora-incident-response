# Investigation Findings

## Finding 1 — CEO account compromise
`daniel.reeve@cloudora.io` successfully authenticated at 03:12:05 UTC on 10 August from `102.89.44.17` in Lagos after failed attempts. The session used Windows 10 / Chrome 125 and was followed by Outlook Web and Azure Portal access. Daniel later authenticated normally from London at 08:41 UTC.

**Assessment:** confirmed unauthorized access / valid-account use.

## Finding 2 — Password spraying
Three Lagos IP addresses generated 114 failed sign-ins across 26 distinct accounts over three nights. The low number of attempts per account across many accounts is consistent with password spraying.

**MITRE ATT&CK:** T1110.003 — Brute Force: Password Spraying.

## Finding 3 — MFA persistence
At 03:18:44 UTC, an authenticator app named **Pixel 6** was registered on the CEO account from attacker infrastructure.

**MITRE ATT&CK:** T1098.005 — Account Manipulation: Device Registration.

## Finding 4 — BEC staging
At 03:31:09 UTC, the attacker created the **RSS Subscriptions** inbox rule on the CEO mailbox. Messages from `finance@cloudora.io` or containing `invoice` were moved to RSS Feeds and marked read.

**MITRE ATT&CK:** T1564.008 — Hide Artifacts: Email Hiding Rules.

## Finding 5 — Second compromised account
`priya.nair@cloudora.io` was successfully accessed from `102.89.45.101` at 03:47:18 UTC after spray activity. SharePoint Online access followed at 03:52:40 UTC.

**Assessment:** confirmed second compromised account.

## Finding 6 — False positive / legitimate travel
`omar.farah@cloudora.io` showed successful Dubai activity consistent with legitimate travel: daytime sign-ins, established iOS 17 / Mobile Safari device fingerprint, and no failed attempts immediately before the successful sessions. Omar was a spray target but was not confirmed compromised in the available logs.
