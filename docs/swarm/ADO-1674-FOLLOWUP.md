# ADO-1674-FOLLOWUP

## Goal

Close two missing edges in the ADO-1669 public discovery backlink mesh on the
`xrmghost-base` repository README: add first-party links to the
`XrmGhost.Cli` and `XrmGhost.Attributes` NuGet packages, alongside the
docs/www/org-profile/attributes-repo/skills-repo links already added in the
prior ADO-1678 cycle.

## Scope and modifications

- File touched: `README.md` only.
- Added two rows to the existing "What's public, what isn't" table (the
  sibling-repo link table from the ADO-1678 cycle), immediately after the
  `.github` row:
  - `XrmGhost.Cli` → `https://www.nuget.org/packages/XrmGhost.Cli`
  - `XrmGhost.Attributes` → `https://www.nuget.org/packages/XrmGhost.Attributes`
- Copy is differentiated from the existing rows: the CLI row emphasizes the
  `dotnet tool install -g XrmGhost.Cli` install path (vs. cloning a repo); the
  Attributes row is explicitly framed as "the prebuilt package for the
  attribute library above" to avoid duplicating the wording already used for
  the `xrmghost-attributes` GitHub repo row.
- No other section, file, or link was touched. No new standalone block was
  added — both rows integrate into the existing table per the task's risk
  note about avoiding clutter.

## Commands executed

- `git diff -- README.md` — confirmed only the two new table rows were added.
- `rg -n 'https://' README.md` — confirmed link inventory, no accidental
  duplicate or malformed URL.
- `curl -s -o /dev/null -w "%{http_code}" -L https://www.nuget.org/packages/XrmGhost.Cli`
  → `200`
- `curl -s -o /dev/null -w "%{http_code}" -L https://www.nuget.org/packages/XrmGhost.Attributes`
  → `200`

## Acceptance criteria verified

- [x] README.md includes first-party links to the CLI and Attributes NuGet
      packages, with differentiated copy from existing rows.
- [x] No other file touched (confirmed via `git status` / `git diff` scope).
- [x] Both NuGet links resolve (HTTP 200 verified above).

## Residual risks

- None identified. The change is purely editorial/link-topology, matching
  the task constraints. NuGet package listing content itself (README on
  nuget.org for each package) was not inspected/validated — only that the
  package pages resolve.

## Notes for review

- The `docs/swarm/` file itself is written per the standing ACT operating
  protocol (mandatory local run doc), not part of the task's `files_to_edit`
  scope; it does not modify product documentation under `docs/**` as
  referenced in `files_not_to_touch` (that constraint targets the repo's own
  product docs tree, not the swarm reporting artifact).
