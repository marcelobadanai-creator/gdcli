
# Google OAuth Setup

This guide explains how to configure Google Drive API access for gdcli.

## 1. Create a Google Cloud Project

Open Google Cloud Console:

https://console.cloud.google.com/

Create a new project.

Example:

gdcli-user

---

## 2. Enable Google Drive API

Go to:

APIs & Services → Library

Enable:

Google Drive API

---

## 3. Configure OAuth Consent Screen

Go to:

APIs & Services → OAuth consent screen

Choose:

External

Fill:

- Application name
- User support email
- Developer contact email

---

## 4. Create OAuth Credentials

Go to:

APIs & Services → Credentials

Create:

OAuth Client ID

Application type:

Desktop app

---

## 5. Configure gdcli.json

Copy the generated credentials:

```json
{
  "google": {
    "project_id": "...",
    "client_id": "...",
    "client_secret": "..."
  }
}
