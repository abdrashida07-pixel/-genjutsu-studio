# Genjutsu Studio

A self-hosted Genjutsu-style video AI studio built from scratch. It is not a copy of Higgsfield's proprietary frontend code.

## Features

- Motion Transfer
- Object Swap
- Upload one source video
- Upload up to 8 reference images
- Prompt
- 480p / 720p / 1080p selector
- Direct browser-to-Higgsfield signed uploads
- Server-side API key protection
- Generation queue + polling
- Result video player + download link
- Responsive dark UI

## Requirements

- Node.js 20+
- A Higgsfield API key with access to the selected Genjutsu models

## Start

```bash
npm install
cp .env.example .env
# Put your Higgsfield API key into .env
npm start
```

Open http://localhost:3000

## Important

The AI generation itself is not free: Higgsfield charges according to its current API pricing and your account. This project does not bypass credits or authentication.

The app currently uses:

- Motion Transfer: `higgsfiled/genjutsu/motion-transfer/v1.0`
- Object Swap: `higgsfiled/genjutsu/object-swap/v1.0`

If Higgsfield changes a model ID, update the constants in `server.js`.

## Production notes

For production, add:
- authentication/user accounts
- rate limiting
- persistent job storage
- file size/type validation
- S3/R2 storage if you need your own media archive
- HTTPS
- CSRF protection if you add cookie auth
- billing/credits if you plan to expose this publicly
