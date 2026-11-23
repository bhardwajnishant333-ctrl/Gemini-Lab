# Gemini Lab

Independent Gemini API application for Cloudflare Workers.

**Public repository:** Do not commit API keys or access tokens. This repository contains no credentials. PIVYON and other applications remain unchanged.

## Cloudflare deployment

1. Connect this repository to a **new** Cloudflare Worker.
2. Set the entrypoint to `src/index.js`.
3. Configure `GEMINI_API_KEY` and `APP_ACCESS_TOKEN` as encrypted Worker secrets.
4. Restrict access with Cloudflare Access and add rate limiting before public use.
5. Test Gemini API availability and free-tier quota with one request. Do not enable paid billing.

The Gemini API key previously pasted into chat should be rotated, even if it is a free-tier key.

## Endpoints

- `GET /` serves a simple chat UI.
- `POST /api/generate` expects JSON `{"prompt":"Hello"}` and `Authorization: Bearer <APP_ACCESS_TOKEN>`.

The API fails closed if required secrets are missing.
