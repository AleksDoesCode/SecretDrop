# SecretDrop — Encrypted File Sharing for Developers

**Share sensitive files without trusting the server.**

SecretDrop encrypts everything in your browser before it ever reaches a server. Send API keys, credentials, configs, and documents through password-protected links or end-to-end encrypted direct transfers.

**[Get Started at secretdrop.dev](https://secretdrop.dev)**

---

## How It Works

### Password-Protected Links
1. Upload files and set a password
2. Files are encrypted client-side with AES-256-GCM
3. Share the link — recipients decrypt in-browser
4. No account required for recipients

### E2E Direct Transfer (Premium)
1. Select recipients by email
2. Files are encrypted with each recipient's public key (ECIES)
3. Only intended recipients can decrypt — no passwords, no shared secrets
4. Sender identity verified via digital signatures

---

## Why SecretDrop

- **Zero-Knowledge Architecture** — The server never sees your plaintext data, filenames, or passwords
- **Client-Side Encryption** — AES-256-GCM with PBKDF2 key derivation (600,000 iterations)
- **No Recipient Account Needed** — Password-protected links work for anyone
- **Multi-File Bundles** — Send multiple files in a single encrypted bundle
- **Expiration Policies** — Bundles auto-expire based on your settings
- **Access Analytics** — Track views, downloads, and access attempts
- **Built on Web Standards** — WebCrypto API, no third-party crypto libraries

---

## Security Model

| What the server stores | What the server cannot access |
|---|---|
| Encrypted file blobs | Plaintext file contents |
| Encrypted filenames | Original filenames |
| Verification hash + salt | Your password |
| Metadata (title, timestamps) | The encryption key |

Private keys for Direct Transfer are encrypted with your password before storage. They never leave your browser unencrypted.

---

## Tech Stack

- React 19, Vite, Tailwind CSS
- NestJS, Supabase (Postgres, Auth, Storage)
- WebCrypto API for all cryptographic operations
- Astro for the marketing site

---

## Pricing

| | Free | Premium |
|---|---|---|
| Password-protected bundles | 1 active | Unlimited |
| Bundle expiry | 7 days | Custom |
| E2E Direct Transfer | — | Included |
| Access analytics | Basic | Detailed |
| Multi-recipient transfers | — | Included |

---

## Links

- **Website:** [secretdrop.dev](https://secretdrop.dev)
- **Security Model:** [secretdrop.dev/security](https://secretdrop.dev/security)
- **FAQ:** [secretdrop.dev/faq](https://secretdrop.dev/faq)

---

Built for developers who take security seriously.
