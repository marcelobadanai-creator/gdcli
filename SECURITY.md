
# Security Policy

**Last updated:** August 1, 2026

## Supported Versions

Security fixes are generally provided only for the latest released version of `gdcli`.

Users are encouraged to keep their installation up to date.

| Version | Supported |
|---------|-----------|
| Latest Release | ✅ Yes |
| Older Releases | ❌ No |
| Development Builds | ⚠ Best Effort |

---

## Reporting a Vulnerability

If you discover a security vulnerability, please **do not disclose it publicly before it has been addressed**.

Instead, report it privately to the project maintainer through one of the following channels:

- GitHub Security Advisories (preferred, if enabled)
- GitHub Private Vulnerability Reporting
- Email (if provided by the project)

Please include as much information as possible:

- Description of the vulnerability
- Steps to reproduce
- Affected version(s)
- Operating system
- Proof-of-concept, if available
- Suggested mitigation (optional)

---

## Response Process

When a valid vulnerability report is received, the maintainer will make reasonable efforts to:

1. Acknowledge receipt of the report.
2. Investigate the issue.
3. Develop and test a fix.
4. Publish a patched release when appropriate.
5. Credit the reporter, if they wish to be acknowledged.

Response times may vary depending on the severity and the maintainer's availability.

---

## Security Scope

`gdcli` is a local command-line application.

Security issues may include, but are not limited to:

- Authentication vulnerabilities
- OAuth token exposure
- Local credential disclosure
- Remote code execution
- Privilege escalation
- Path traversal
- Arbitrary file overwrite
- Unsafe temporary file handling
- Command injection
- Memory corruption
- Denial of service

General bugs, usability issues, or feature requests should be reported through the project's regular GitHub Issues page.

---

## OAuth Security

`gdcli` uses Google OAuth 2.0 for authentication.

Authentication credentials are intended to remain on the user's local machine and are never intentionally transmitted to infrastructure controlled by the project maintainer.

Users should:

- Keep their operating system secure.
- Protect local configuration files.
- Revoke Google OAuth access if credentials are suspected to be compromised.
- Avoid sharing authentication files.

---

## Responsible Disclosure

Please allow a reasonable amount of time for a fix before publicly disclosing a vulnerability.

Coordinated disclosure helps protect all users of the project.

---

## Dependencies

This project relies on third-party libraries and services.

Security issues originating from third-party dependencies may need to be addressed upstream before they can be resolved in `gdcli`.

Users are encouraged to regularly update both `gdcli` and its dependencies.

---

## Security Best Practices

For the safest experience, users should:

- Download releases only from the official project repository.
- Verify release signatures or checksums if provided.
- Keep OAuth credentials private.
- Review commands before executing operations that modify or delete files.
- Maintain backups of important data.
- Use the latest stable version of the software.

---

## Contact

Security-related questions or reports should be directed to the project maintainer using the private reporting methods described above.
