# Halcira Security

_Last updated: October 15, 2026_

How Halcira protects your mail, and how to tell us about a problem.

## How Halcira is built

- Your accounts, keys and Lisa's data are stored in a vault encrypted with AES-256-GCM, using a key derived from your passcode with scrypt.
- Halcira's local server listens only on your computer's loopback address and rejects requests from other websites and hostnames.
- Email content is sanitized and shown in a sandbox without scripts. Remote images and known trackers are blocked by default.
- Links in email open in your normal browser, never inside Halcira.
- Lisa treats email content as information, never as instructions.
- Updates are downloaded from the official release repository and checked against their published SHA-512 hashes before installing.

## Reporting a vulnerability

Please report security problems privately using GitHub's "Report a vulnerability" button on the Security tab of https://github.com/EstelaRepositories/halcira, not in a public issue. If that button isn't there, open an issue that only says you have a security report (no details) and we'll set up a private way to talk. Include the Halcira version, what you found and steps to reproduce. We'll acknowledge reports as soon as we can and credit you in the release notes if you'd like.

Please don't access other people's mail or data, and give us reasonable time to fix a problem before sharing it publicly.
