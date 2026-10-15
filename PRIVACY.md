# Halcira Privacy Policy

_Last updated: October 15, 2026_

Halcira is a privacy-first email app that respects your time. It runs on your own computer, and we built it so your mail stays yours: there is no Halcira server, no account with us, no analytics and no ads. This policy explains exactly what the app stores, where it stores it, and every outside service it talks to.

## The short version

- Your email, passwords, keys and settings are stored only on your computer, encrypted with your passcode.
- We (the people who make Halcira) never receive your email, your contacts or anything about how you use the app.
- Halcira talks directly to your email providers, and only to the other services listed below, most of which you can turn off.
- If you turn on Lisa's Claude features, the emails she works on are sent to Anthropic using your own API key.
- We don't sell, rent or share data, because we never have it.

## What Halcira stores on your computer

Everything below lives in Halcira's data folder on your PC (under your Windows user profile). Sensitive data is kept in an encrypted vault (AES-256-GCM, with a key derived from your passcode using scrypt). Without your passcode it can't be read, including by us.

- Sign-in details for your mail accounts: Google and Microsoft sign-in tokens, and passwords for IMAP accounts such as Proton Mail Bridge.
- Your Anthropic API key, if you add one.
- Copies of message headers and summaries, used to make your inbox load quickly.
- Lisa's data: her notes about what you asked her to remember, chat history, follow-ups, reminders, the codes, packages, bills and events she found, label rules, unsubscribe history, scheduled emails, and her activity log.
- Your settings and your OpenPGP keys.

Sender pictures are cached as plain image files so they don't need to be downloaded again. If you choose "Unlock automatically on this PC", your passcode is protected with Windows' own per-user encryption (DPAPI) so Halcira can open without asking. Turn that off in Settings to type it every time.

Deleting an account in Halcira removes its data from the vault. Uninstalling Halcira and deleting its data folder removes everything.

## Services Halcira connects to

Halcira connects directly from your computer to these services. Each one receives your IP address and whatever is described here, and each has its own privacy policy.

- Your email providers (Google Gmail, Microsoft Outlook, Proton Mail Bridge running on your PC, or another IMAP/SMTP server you add): to sign in, download, send, label, move and delete mail on your behalf.
- Anthropic (Claude), only if you add an API key: the content of emails Lisa works on (sender, subject, body text) and your chats with her, so she can sort, summarize, draft replies, suggest labels, find bills and events, and answer you. Requests use your own key under your agreement with Anthropic.
- Gravatar and DuckDuckGo, only while "Show sender pictures" is on: Gravatar receives a one-way hash of a sender's address; DuckDuckGo receives a company sender's domain name (for example, "example.com") to fetch its icon. For company senders, Halcira may also look up the company's published BIMI logo through DNS and the logo or app icon on the company's own website (it requests the website itself, never anything inside the email).
- keys.openpgp.org, only when you send an encrypted email: the recipient's address, to find their public key.
- Senders' unsubscribe addresses, only when you or Lisa unsubscribe: a request to the link or address the sender published in the email.
- Senders' image servers, when an email's images load: automatically in Default privacy mode, or only when you choose Load images in Strict mode. Like any web image, this can let a sender see your IP address and that the email was opened. Known tracking pixels are blocked either way.
- GitHub, to check for and download Halcira updates. GitHub receives your IP address and the app version.

Halcira does not include analytics, crash reporting, advertising or tracking code of any kind.

## Google user data

When you connect a Google account, Halcira asks for permission to read, send, label and organize your Gmail so it can work as your email app. Halcira's use and transfer of information received from Google APIs adheres to the Google API Services User Data Policy, including the Limited Use requirements.

- Gmail data is used only to provide the email features you see in Halcira.
- It is transferred to a third party only to provide those features at your direction (Anthropic, when you turn on Lisa's Claude features), to comply with law, or as part of a merger or acquisition with your notice.
- It is never used for advertising, never sold, and never used to train AI models, by us or by anyone we send it to on your behalf.
- No person reads your Gmail data, except with your explicit permission for a specific message (for example, if you send it to us while reporting a bug), when needed for security or to comply with law.

You can remove Halcira's access at any time from your Google Account's security settings (Third-party apps with account access), or by removing the account in Halcira.

## Lisa and AI

Lisa's organizing, codes, tracking numbers and duplicate detection run on your computer. Her other features use Claude through your Anthropic API key, and only while you have a key added and the feature switched on. Anthropic's commercial terms say API inputs aren't used to train their models by default; check Anthropic's current policies for details.

Lisa treats the content of emails as information, not instructions. Actions such as sending, deleting or forwarding mail happen only within the settings you chose or when you ask her in chat. Lisa can make mistakes; review what she does in her activity list.

## Your choices

- Choose Default or Strict privacy mode in Settings, or turn sender pictures, remote images, notifications and each of Lisa's features on or off one by one.
- Remove your Anthropic key to stop all AI processing.
- Remove any mail account, which also deletes its saved data.
- Export or delete your data by using your email provider directly; Halcira keeps only copies.

## Children

Halcira isn't directed to children under 13, and we don't knowingly collect anyone's personal information, of any age.

## Security

Halcira encrypts its vault, runs its local server only on your computer's loopback address, blocks requests from other websites, and sandboxes email content. No software is perfectly secure; keep Windows updated and choose a strong passcode. To report a security problem, see the Security page.

## Changes and contact

If this policy changes, the new version ships with an app update and the date at the top changes. Material changes will be called out in the update notes.

Questions: open an issue at https://github.com/EstelaRepositories/halcira/issues.
