# :bug: Aurora Bug Tracking System

This repository serves as a public, centralized bug tracking system for ALCF Aurora at Argonne National Laboratory. It provides a structured way to document, track, and manage issues related to the system.

- [`bugs.md`](bugs.md) - Main bug tracking document containing a comprehensive table summarizing all current (and recently closed?) reported issues on Aurora

## Other files

- [`bugs_auto.md`](bugs_auto.md) - Summary table of bugs, automatically generated from all Issues (open and closed) in this repository. All updates, lengthy details, discussions, and related artifacts (e.g. screenshots) for a given bug should be included at its linked Issue, the first column in the table.
- [`bugs_manual.md`](bugs_manual.md) - Manually maintained table of other bug reports (with no corresponding Issue). When discussing one of these bugs and/or including more information, add the content in a `##` section below the table. Any changes to this file should be made via Pull Requests. Ideally, these reports would eventually be replaced by Issues and removed from this file. 
- [`POC.md`](POC.md) - Directory of Aurora subject matter experts, especially related to bug reporting.

## Bug Report Table Format

Each bug report in the any of the Markdown tables should include the following information; 
- Internal ID
- Description
- Vendor ID (if applicable)
- Reproducer Path (on `/lus/flare/`)
- PoC (Point of Contact)
- Status (Open, Closed, Workaround Available (WA), etc.)
- Priority (🚨 High, ⚠️ Medium, ℹ️ Low)
- ETA (for a bugfix or workaround)

For auto-generated rows, this content is parsed from our current [Bug Report Form template](https://github.com/argonne-lcf/AuroraBugTracking-test/issues/new?template=BugReportForm.yaml). Note, an Issue's title is not parsed at all when generating the table in [`bugs_auto.md`](bugs_auto.md). 

Rows in [`bugs_manual.md`](bugs_manual.md) are assigned Internal IDs prefixed with an `A`, e.g. `A1`, `A2`, ... When manually adding a bug report, self-assign the next available ID.

## Auto-Generation Process

The bug tracking tables are automatically synchronized using GitHub Actions. 

<!-- The process works as follows:

1. A GitHub Action parses all open and closed Issues in the repository
2. Generates a formatted table from the Issues
3. Merges this with the manually-curated table in [`bugs_manual.md`](bugs_manual.md)
4. Updates [`bugs.md`](bugs.md) with the combined results
--> 

The synchronization runs automatically every night at 9am UTC. You can also trigger it manually:
- Through the GitHub Actions Web UI
- Via command line: `gh run list --workflow=sync-issues-to-table.yml`

## License

This project is maintained by Argonne National Laboratory. Contact repository maintainers for usage guidelines.
