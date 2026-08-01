# Privacy Policy

**Last updated:** August 1, 2026

## Overview

Google Drive CLI (`gdcli`) is an open-source command-line application that allows users to interact with their own Google Drive account.

This application does not operate its own servers and does not collect, store, sell, or share personal information beyond what is necessary to communicate with the Google Drive API on behalf of the user.

---

## Information We Access

When you authenticate with your Google Account, `gdcli` may access information required to perform the operations you explicitly request, including:

- Google Drive files and folders.
- File metadata (such as names, sizes, MIME types, and modification dates).
- Folder structure.
- OAuth authentication tokens.

The application only accesses data within the permissions granted by you during the Google OAuth authorization process.

---

## Authentication

`gdcli` uses Google's OAuth 2.0 authentication system.

Authentication credentials (such as access tokens and refresh tokens) are stored locally on your computer to allow future authenticated sessions.

These credentials are never transmitted to any server controlled by the developer.

---

## Data Storage

All application data is stored locally on the user's device.

Depending on the configured features, this may include:

- OAuth credentials.
- Application configuration.
- Offline cache or mirrored files.
- Temporary files created during uploads or downloads.

The exact storage location depends on your configuration.

---

## Data Sharing

`gdcli` does not sell, rent, or share your personal information with third parties.

The only external service contacted by the application is the Google Drive API for the purpose of executing the commands requested by the user.

Your use of Google services is also governed by Google's own Privacy Policy.

---

## Offline Features

Some commands optionally create local copies of files or temporary data for offline operation, upload buffering, or resumable transfers.

These files remain under the user's control and are stored only on the local machine.

---

## Open Source

The source code of `gdcli` is publicly available.

Users are encouraged to inspect the source code to verify how information is handled.

---

## Third-Party Services

This application uses:

- Google Drive API
- Google OAuth 2.0

Their respective privacy policies apply when interacting with Google's services.

---

## Security

Reasonable efforts are made to protect locally stored authentication credentials and application data.

However, the security of files stored on your computer ultimately depends on the security of your operating system and local environment.

---

## Your Control

You remain in full control of your data.

At any time you may:

- Remove locally stored credentials.
- Revoke the application's access through your Google Account.
- Delete local configuration files.
- Uninstall the application.

---

## Changes to This Policy

This Privacy Policy may be updated from time to time.

Material changes will be reflected by updating the "Last updated" date at the top of this document.

---

## Contact

If you have questions regarding this Privacy Policy, please contact the project maintainer through the project's GitHub repository or the contact information provided with the project.
