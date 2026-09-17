# Agent guidance for snort3

This repository has a companion knowledge wiki, **snort3-wiki**
(https://github.com/satchm0h/snort3-wiki), kept in a separate repository and
checked out as a sibling directory, `../snort3-wiki`, by default. The wiki synthesizes `doc/`, `README.md`, `ChangeLog.md`, and
`src/**/dev_notes.txt` into cross-linked pages and stores per-project working
state. Use it on every task; do not rediscover from raw docs what it already
holds.

## Required workflow

1. **Read the wiki first.** Open `../snort3-wiki/index.md` and the wiki's
   `AGENTS.md`. Follow links to the `overview/`, `guides/`, `modules/`,
   `concepts/`, and `sources/` pages relevant to the task before touching code.
2. **Create or update a project page.** For any non-trivial task, create
   `../snort3-wiki/projects/<slug>.md` (status, goal, plan, decisions, findings,
   open questions, pages used) and keep it current as work proceeds. Resume from
   it when returning to a task.
3. **Build and test per the wiki.** `guides/build-and-test.md` records the
   working configure/build/`make check` recipe, required environment
   (e.g. `HWLOC_SYNTHETIC` on some VMs), and known limitations
   (benchmark target, NUMA Catch test). Prefer it over guessing.
4. **File what you learn.** New facts about Snort internals, build quirks,
   module behavior, or doc staleness go back into the wiki: extend the relevant
   `modules/`, `concepts/`, or `guides/` page, add a `questions/` page for open
   items, add the page to `index.md`, and append to `log.md`. Commit the wiki
   alongside the snort3 change.
5. **Cite sources.** Wiki claims must point to repo-relative paths in this
   repository (e.g. `doc/user/binder.txt`, `src/stream/tcp/dev_notes.txt`).
   Raw docs here are the authoritative, immutable sources; the wiki condenses
   them and must never be copied into this tree.

## Repository conventions (summary; see the wiki for detail)

- Coding style: `doc/devel/style.txt` (wiki: `guides/coding-style.md`).
  Four-space indent, <120 columns, no exceptions/RTTI, `FIXIT-*` tags,
  zero warnings, unit tests for new code.
- Plugin/module model: `doc/devel/extending.txt`
  (wiki: `guides/extending-plugins.md`).
- Commit messages: `<topic>: <summary>`.
- Versioning: `doc/devel/versions.txt` (wiki: `overview/versioning.md`).

If the wiki checkout is missing, clone it next to this repository before
starting work rather than proceeding without it.
