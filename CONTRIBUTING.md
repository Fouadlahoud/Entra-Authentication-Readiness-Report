# Contributing

Thank you for considering a contribution.

## Before you start

- Open an issue for substantial behavior changes before implementing them.
- Never include real tenant identifiers, user information, sign-in records, authentication details, credentials, or report output in an issue, test, commit, or pull request.
- Use only fictional identities and reserved domains such as `example.com` in tests and documentation.

## Development workflow

1. Fork the repository and create a focused branch.
2. Make a small, documented change.
3. Run the offline smoke test:

   ```powershell
   .\tests\Invoke-SmokeTest.ps1
   ```

4. If PSScriptAnalyzer is available, run:

   ```powershell
   Invoke-ScriptAnalyzer -Path .\Get-EntraAuthenticationReadinessReport.ps1 -Recurse -Severity Warning,Error
   ```

5. Update the README and changelog when behavior or output changes.
6. Open a pull request that explains the problem, approach, validation, and any security or privacy impact.

## PowerShell style

- Support Windows PowerShell 5.1 unless a major version explicitly changes that requirement.
- Use approved PowerShell verbs and descriptive parameter names.
- Keep `Set-StrictMode -Version Latest` and terminating error behavior intact.
- Surface actionable errors instead of silently ignoring failures.
- Preserve offline testability for reporting-pipeline changes.

## Pull request checklist

- [ ] The change is focused and does not include generated reports.
- [ ] Sample data is entirely fictional.
- [ ] The smoke test passes.
- [ ] PSScriptAnalyzer has no new warning or error findings.
- [ ] Documentation reflects any user-visible change.
