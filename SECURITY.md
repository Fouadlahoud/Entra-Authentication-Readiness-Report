# Security policy

## Supported versions

Security updates are applied to the latest code on the `main` branch.

## Reporting a vulnerability

Do not open a public issue for a suspected vulnerability or include tenant data, credentials, access tokens, user records, or report output in a report.

Use [GitHub private vulnerability reporting](https://github.com/fredlahoud/Entra-Authentication-Readiness-Report/security/advisories/new) and include:

- A concise description of the issue and its impact.
- The affected version or commit.
- Reproduction steps using fictional data.
- Any suggested mitigation.

Reports will be acknowledged as soon as practical. Please allow time to investigate and prepare a fix before public disclosure.

## Operational security

This tool uses delegated Microsoft Graph access and exports identity and authentication-usage data. Operators are responsible for applying least privilege, protecting generated files, reviewing data before sharing it, and following organizational retention requirements.
