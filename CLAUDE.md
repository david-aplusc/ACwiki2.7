# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This repository is a single-file, password-protected internal wiki for A+C Animation Studios. The entire wiki is a self-contained static HTML page (`README.md`) that uses [StatiCrypt](https://robinmoisson.github.io/staticrypt/) to encrypt the wiki content client-side.

## Architecture

`README.md` is the deployable HTML file (the `.md` extension is intentional for GitHub Pages or similar hosting). It contains:

- **StatiCrypt decryption engine** — inline JavaScript implementing AES-CBC decryption using the Web Crypto API, with a 3-round PBKDF2 key derivation (SHA-1 × 1000 → SHA-256 × 14000 → SHA-256 × 585000) and HMAC-SHA-256 signature verification.
- **Encrypted payload** — the entire wiki HTML is stored as `staticryptEncryptedMsgUniqueVariableName`, a hex-encoded AES-CBC ciphertext + HMAC.
- **Login UI** — a Fredoka-font "claymorphism" styled password form that decrypts and replaces the page on correct password entry. Supports "Remember me" via `localStorage`.

There is no build system, no dependencies, and no source files — the encrypted page is the artifact. To update the wiki, decrypt the current page, edit the plaintext HTML, and re-encrypt using the StatiCrypt CLI with the same salt (`e58622878c5b4107a5c053c29b821537`).

## Re-encrypting

```bash
# Install StatiCrypt CLI
npm install -g staticrypt

# Re-encrypt after editing plaintext wiki.html
staticrypt wiki.html --password <studio-password> --salt e58622878c5b4107a5c053c29b821537 -o README.md
```
