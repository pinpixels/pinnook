# Security policy

## Supported versions

Only the latest published version of Pinnook receives security fixes.

## Reporting a vulnerability

Please **do not open a public issue** for security problems.

1. Use GitHub's **private vulnerability reporting**: *Security → Report a vulnerability* on the repository page, or
2. email **pinpixels@gmail.com** with the subject "Pinnook security".

Include: affected version, steps to reproduce, impact, and (if you have one) a suggested fix. You do not need to include real user data — please don't.

**What to expect:** an acknowledgement within 3 working days, a fix or mitigation plan within 14 days for confirmed issues, and credit in the release notes if you wish. Please give us reasonable time to ship a fix before public disclosure.

## Scope

In scope: the extension code in `src/`, the build and licence tools in `tools/`, the documentation site, and the encrypted-backup format.

Particularly interesting: script execution from note content or imported files, CSP bypass, token or passphrase exposure, weaknesses in the backup envelope, ways to make the free build send data off-device, licence-signature bypass beyond "anyone can rebuild the open-source code".

Out of scope: attacks requiring a compromised browser profile or OS account, social engineering, and vulnerabilities in Chrome, Google Drive or Dropbox themselves (report those to the vendors).

## Design notes for researchers

See [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md) (security model section). The test suite includes an XSS corpus (`test/markdown.test.mjs`) and tamper/downgrade tests for the backup format (`test/crypto-license-sync.test.mjs`).
