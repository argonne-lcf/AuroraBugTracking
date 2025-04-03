# :bug: Aurora Bug Tracking System

This repository serves as a public, centralized bug tracking system for ALCF Aurora at Argonne National Laboratory. It provides a structured way to document, track, and manage issues related to the system.

> [!IMPORTANT]
> The main bug tracking table is available in [`bugs.md`](bugs.md). This comprehensive reference summarizes all currently-known and recently-closed bugs on Aurora.

## Other files

- [`POC.md`](POC.md) - Directory of Aurora subject matter experts, especially related to bug reporting.
- [`TODO.md`](TODO.md) - Potential changes to this repository setup

## Table Format

The two Markdown tables are automatically generated from GitHub issues and contain the following columns:

- **Internal ID**: GitHub issue number with link
- **Description**: Issue title
- **Vendor ID**: Links to related tickets in other bug-tracking systems (vendor JIRA, other GitHub repo, etc.)
- **Reproducer Path**: Location of code to reproduce the bug (e.g. on `/lus/flare/` or a URL)
- **PoC**: Point of Contact
- **Status**: Current status of the bug (final status for closed issues)
- **Priority**: 🚨 if marked as priority
- **ETA**: Expected resolution date
- **Date Opened**: When the issue was created
- **Last Updated/Closed Date**: When the issue was last modified (changed title or edited text body for open issues) or closed (for closed issues). Note, a new/deleted/edited comment on an open Issue will also modify its "Last Updated" date, but deleting a comment will never rollback the date.
<!--- KGF: cannot find documentation of gh CLI's updatedAt JSON field precise details. Also consider adding GH Issue labels, author, assignedTo fields to the tables? -->

This content is parsed from our current [Bug Report Form template](https://github.com/argonne-lcf/AuroraBugTracking/issues/new?template=1-BugReportForm.yaml); changes to that template require changing the GitHub Action parser logic.

> [!WARNING]
> Issues opened via the [Blank issue](https://github.com/argonne-lcf/AuroraBugTracking/issues/new) template will likely break this auto-parsing process

## Auto-Generation Process

The bug tracking table is automatically synchronized using GitHub Actions. The synchronization runs automatically whenever an Issue is opened and/or edited, and every night at 9am UTC. You can also trigger it manually:
- Through the GitHub Actions Web UI
- Via command line: `gh workflow run "Sync issues to table"`

To monitor a summary of the last 20 submitted workflow runs from the command line:
```bash
GH_FORCE_TTY=100% watch -c gh run list # --workflow=sync-issues-to-table.yml
```
This assumes that your `watch` installation and terminal support the rich-formatted, color-enabled output from `gh` (e.g. `procps-ng watch` on Linux, not BSD `watch` on macOS).

To watch a more detailed breakdown (only while it is executing) of most recently-launched workflow run:
```bash
gh run watch -i 1 $(gh run list --workflow=sync-issues-to-table.yml --json databaseId --jq '.[0].databaseId')
```
<!-- gh run view --job=$(gh run view $(gh run list --workflow=sync-issues-to-table.yml --json databaseId --jq '.[0].databaseId') --json jobs --jq '.jobs[0].databaseId')  -->
To view a summary of the most recently-launched workflow run in your browser:
```bash
gh run view $(gh run list --workflow=sync-issues-to-table.yml --json databaseId --jq '.[0].databaseId') -w
```

## License

This project is maintained by Argonne National Laboratory. Contact repository maintainers for usage guidelines.
