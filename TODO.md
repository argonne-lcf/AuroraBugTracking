# to-do / design questions and decisions 

- [x] update hardcoded URLs (to https://github.com/argonne-lcf/AuroraBugTracking-test) in README if this stuff gets merged upstream
- [x] Do we remove Closed Issues from the tables? (e.g. `gh issue list --state=open`)
- [x] Could filter auto-parsed issues via their labels (e.g. `gh issue list --label=track-bug`) and/or assignee, etc.
- [x] FYI, no ability to Delete Issues based on argonne-lcf GitHub Org settings, even though members have Admin permissions
- [ ] cleanup `gh` json parser; consider replacing as much as possible with `gh --template` flag with Go templates: https://cli.github.com/manual/gh_help_formatting
  - and/or use `--jq` flag directly?
- [ ] stop the cron job trigger for the GH action? now that we are using the Issue Open/Edit trigger
- [-] Disable Blank Issues entirely? That would make the GH Action much more robust
- [x] auto-include `bugs.md` table as a Snippet in a https://github.com/argonne-lcf/user-guides page for a prettier rendering of the table for viewers, e.g. at the bottom of https://docs.alcf.anl.gov/aurora/known-issues/
  - [x] Would be able to make it sortable (priority, ID, "last updated date") via JavaScript: https://squidfunk.github.io/mkdocs-material/reference/data-tables/#sortable-tables
  - [ ] Still would likely need to update its inclusion in the user-guides semi-manually via `git submodule update`. Add a new GitHub Action on the `user-guides` repo to do this via cron?
  - [ ] Create a separate set of tables here (e.g. in `bugs_export.md`?) that omit certain columns that are irrelevant to the copy included in `user-guides` (POC, reproducer path, priority, ...)
  - [ ] **OR**, extend this parser to get every Issue body field (and metadata) and dump it into a `.csv`, which then gets used by https://github.com/timvink/mkdocs-table-reader-plugin to create a filtered table in `user-guides`
  - [ ] Need to add column wrap/sizing changes:
<img width="1107" alt="image" src="https://github.com/user-attachments/assets/9d8ab2ff-212b-4d21-b961-910d453c5e3d" />
 
- [ ] add some minimal PR template
- [ ] **add "last updated" date column to tables, sort by date?**
- [ ] stuff all `bugs*.md`, `POC.md` in some subdir, remove links from README.md, so that `bugs.md` gets the main focus for viewers? 
- [ ] and/or change the GH Action to write the combined table directly to the `README.md` instead of `bugs.md`? So people landing on the repo see the table right away, front and center
- [ ] automatically update `.body` ---> `.md` table parser `extract_field()` in [Action YAML](../.github/workflows/sync-issues-to-table.yml) from [Bug Report Form template](https://github.com/argonne-lcf/AuroraBugTracking/issues/new?template=BugReportForm.yaml) whenever the template changes
  - [ ] Understand and/or test what happens if we add/remove table columns (AKA Issue fields) from the Issue template and Table in the future
- [ ] Test robustness of the Issue body parsing of fields (newlines, screenshots/files in Description, ...) , especially for future edits of Issues, when the editor is completely unconstrained by the YAML template format
- [x] Need Issue Label(s) like `about-bug-tracker` or `do-not-file` and/or `ignore` etc. for people to report issues or suggestions with this repository itself (or "draft" Issues etc. that dont conform to the template), and make the parser ignore them during processing Issues
- [ ] Optimize Status dropdown choices (currently 8x) in Issue template
- [ ] decide how/if to communicate this repository to broader ALCF user community (Users Slack, emails to Catalysts/INCITE/ALCC/..., weekly facility update email, user-guides integration, ...)
  - [ ] how should ALCF staff vs. users handle reporting Aurora issues here vs. and/or support@alcf.anl.gov'
  > current matter of discussion. Maybe there should always be a support ticket if something comes from a user. Any bug that is likely a problem caused by system SW/HW problems such as oneAPI or MPICH bugs should go into AuroraBugsTracking, though, if we expect to work on it with Intel/HPE. A support ticket number can be entered as one of the “Vendor” bug IDs. Currently viewing AuroraBugsTracking as mostly for internal ALCF reference (Catalysts or other ALCF teams working with relevant applications), but more sophisticated or hands-on users may want to use it, too--- hence why we are making the repo public and visible+advertised on `users-guide`
  - [ ] Update the following descriptions of this `AuroraBugTracking` to make the instructions clear, once we decide: `README.md`, https://github.com/argonne-lcf/user-guides/blob/8cab9d95111d14826069d01328a7fc6ab2d799ce/docs/aurora/known-issues.md?plain=1#L205
  - [ ] Hide/delete this `TODO.md` file once adoption picks up. Delete/move content most of the technical formatting/workflow content in `README.md`. Move the table to README?
  - [ ] Delete `POC.md` if not maintaining it
  
