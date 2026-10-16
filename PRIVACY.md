# Halcira Privacy Policy

_Last updated: October 16, 2026_

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

Halcira for Android keeps its link key in Android's protected storage, plus a copy of your recent message list so it opens instantly. It's excluded from Google backups and device transfers, and unlinking the phone erases it.

Halcira for Android also gets your Gmail sign-in from your PC when you link it, so Gmail keeps working on the phone when the PC is off (turn this off on the phone under Settings → Without your PC). If you use Halcira for Android with no PC at all, you sign in to Google on the phone, and your Google sign-in keys stay on the phone. Either way, the sign-in is encrypted with a key kept in the phone's hardware-backed keystore. The phone checks Gmail in the background for new-mail notifications, which show who it's from and the subject only when your phone is unlocked. Proton Mail still needs your PC, because Proton only allows other apps through Proton Mail Bridge.

Lisa runs on the phone too, with the same rules as on your PC. When the phone is linked to your PC, the PC shares Lisa's memory with it (her settings, the replies and questions waiting for you, what she's done, the codes, bills and follow-ups she found, your label and sender choices, your chat with her, and your Claude key), over the same end-to-end encrypted link. When your PC is off, Lisa on the phone works from that copy, and when the PC is back the two copies are merged. On the phone it's all kept encrypted with a key in the phone's hardware-backed keystore. Lisa on the phone only works on mail while Lisa on your PC hasn't been active for a few minutes (the PC leaves a hidden label in your Gmail as a sign it's running), so the same email never gets two replies.

Halcira Cloud (on by default; Settings → Phone on your PC) keeps Halcira for Android in sync even when your PC is off. Your PC uploads an encrypted copy of Lisa's memory, your settings, your Claude key, the Google app keys and your Gmail sign-ins. It's encrypted on your PC (AES-256) with a random key that is itself locked with a key made from your Halcira passcode (scrypt), and your passcode never leaves your devices. The copy is stored in a database Halcira's maker runs on Supabase (US). That database sees only the encrypted copy, a one-way hash of each of your email addresses, and a hash of a passcode proof it uses to refuse wrong guesses (after 8 wrong ones, the address is locked for a while). On the phone you sign in with one of your email addresses and your passcode, and the keys are kept in the phone's hardware-backed keystore. Changes on either device are merged into the copy. Other Halcira apps you sign in to with the same email and passcode share the same encrypted copy, so Lisa is one assistant across them; each app adds its own notes for Lisa (for example a reminder or a sign-in code), and they travel inside that same encrypted copy. Turning Halcira Cloud off on your PC deletes the copy from the database. Proton Mail never goes through it.

On the phone, Lisa can keep working with Halcira closed (Settings → Lisa in the background). She runs inside the app on your phone as an Android background service, which Android shows as an ongoing “Lisa is keeping an eye on your mail” notification. About once a minute she checks your inbox for new mail and sign-in codes, and she tells you about important mail, drafts waiting for you, reminders and her morning catch-up. When your PC is on, she gets this from your PC over the encrypted link instead. Nothing extra leaves your phone: she talks only to your PC, to Gmail, and to Claude when you've connected it, just as when the app is open. A sign-in code is copied to your clipboard only when you tap Copy or turn on “Copy new codes automatically”, and the Quick Settings tile keeps only your latest code, for 15 minutes.

On the phone, your encryption (OpenPGP) key, if you make or import one, is kept in the app's private storage and locked by your passphrase. Opening an attachment saves a temporary copy in the app's private cache so another app can show it; saving one puts it in your Downloads folder. App lock uses Android's own fingerprint, face or screen-lock check; Halcira never sees your fingerprint.

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
- Supabase, for Halcira Cloud while it's on: the encrypted copy described above, hashes of your email addresses, and your IP address.
- Your own PC, if you use Halcira for Android: the phone talks only to Halcira on your PC, over your Wi-Fi or Tailscale, and every request is end-to-end encrypted with a key the phone got by scanning a code on your PC's screen. Mail, Lisa and settings reach the phone this way; nothing goes through a Halcira server. The phone also talks to Google's Gmail servers directly for Gmail, the same way the PC app does.

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
