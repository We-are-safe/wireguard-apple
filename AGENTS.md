# Safe WireGuard fork agent instructions

## Current engineering workflow

Oscar develops Safe with agents. Work directly on `main` in this repository’s
canonical checkout. Do not create task branches, pull requests or Git worktrees.
The [current Safe policy](https://github.com/We-are-safe/Safe/blob/main/AGENTS.md)
supersedes historical branch/worktree instructions; the essentials apply here
also when this repository is checked out without the parent workspace:

- Track each change in an owning GitHub issue with outcome and acceptance.
  Inspect status, remotes, existing staging and unrelated edits before writing.
- Use the parent workspace’s `bin/safe-workflow begin` with this repo, issue,
  owner chat, owned paths and relevant check commands when available. One owner
  holds the writer lease; its delegates coordinate disjoint paths. Serialize
  staging, commits and pushes. Preserve unknown or unfinished work.
- Validate the changed outcome locally and obtain independent agent review for
  meaningful code. For application UI changes, follow Safe’s
  [local visual review](https://github.com/We-are-safe/Safe/blob/main/dev/screen-library/LOCAL-REVIEW.md):
  exact before/after commits, synthetic data, matching states/viewports and a
  private issue comparison link. Oscar owns human design acceptance.
- Commit and push completed authorized work before unrelated questions or a turn
  handoff. Stage explicit owned paths; never sweep unknown edits into a commit.
  Commit as `Codex <codex@openai.com>` with local command overrides. Use `Refs #N`.
- Close only after acceptance and verified publication, with the newest remote
  main commit linked in full, the checked SHA/result and delivery status on the
  issue. Use `safe-workflow checkpoint` and `complete` when available; otherwise
  perform that same sequence explicitly. A blocked task stays open with a next
  action; `handoff` releases its lease without claiming completion.
- Keep credentials, customer data, generated evidence and runtime state out of
  Git. Parent development gitlinks may select clean verified pushed child main;
  preserve nested dependency pins. Tags, stable releases and deployments need
  explicit authorization. Main and gitlinks never prove production availability.
