# to-do / design questions and decisions 

- [x] update hardcoded URLs (to https://github.com/argonne-lcf/AuroraBugTracking-test) in README if this stuff gets merged upstream
- [ ] Do we remove Closed Issues from the tables? (e.g. `gh issue list --state=open`)
- [ ] Could filter auto-parsed issues via their labels (e.g. `gh issue list --label=track-bug`) and/or assignee, etc.
- [ ] cleanup `gh` json parser; consider replacing as much as possible with `gh --template` flag with Go templates: https://cli.github.com/manual/gh_help_formatting
  - and/or use `--jq` flag directly?
- [ ] FYI, no ability to Delete Issues based on argonne-lcf GitHub Org settings, even though members have Admin permissions
- [ ] stop the cron job trigger for the GH action, if we trust the Issue open/edit trigger
- [ ] Disable Blank Issues entirely? That would make the GH Action much more robust
- [ ] auto-include `bugs.md` table as a Snippet in a https://github.com/argonne-lcf/user-guides page for a prettier rendering of the table for viewers, e.g. at the bottom of https://docs.alcf.anl.gov/aurora/known-issues/
  - Would be able to make it sortable (priority, ID, "last updated date") via JavaScript: https://squidfunk.github.io/mkdocs-material/reference/data-tables/#sortable-tables
  - Still would likely need to update its inclusion in the user-guides semi-manually via `git submodule update`
  - Need to add column wrap/sizing changes:
<img width="1107" alt="image" src="https://github.com/user-attachments/assets/9d8ab2ff-212b-4d21-b961-910d453c5e3d" />
 
- [ ] add some minimal PR template or warning to only edit `bugs_manual.md`
- [ ] add "last updated" date column to tables, sort by date?
- [ ] stuff all `bugs_*.md`, `POC.md` in some subdir, remove links from README.md, so that `bugs.md` gets the main focus for viewers? 
- [ ] and/or change the GH Action to write the combined table directly to the `README.md` instead of `bugs.md`? So people landing on the repo see the table right away, front and center
- [ ] automatically update `.body` ---> `.md` table parser `extract_field()` in [Action YAML](../.github/workflows/sync-issues-to-table.yml) from [Bug Report Form template](https://github.com/argonne-lcf/AuroraBugTracking/issues/new?template=BugReportForm.yaml) whenever the template changes
  - [ ] Understand and/or test what happens if we add/remove table columns (AKA Issue fields) from the Issue template and Table in the future
- [ ] Test robustness of the Issue body parsing of fields (newlines, screenshots/files in Description, ...) , especially for future edits of Issues, when the editor is completely unconstrained by the YAML template format
- [ ] Need Issue Label(s) like `about-bug-tracker` or `do-not-file` and/or `ignore` etc. for people to report issues or suggestions with this repository itself (or "draft" Issues etc. that dont conform to the template), and make the parser ignore them during processing Issues
