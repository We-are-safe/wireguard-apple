# Safe WireGuard fork agent instructions

## Current engineering workflow

Oscar develops Safe with agents. Work directly on `main` in this repository’s
canonical checkout. Do not create task branches, pull requests or Git worktrees.
The [current Safe policy](https://github.com/We-are-safe/Safe/blob/main/AGENTS.md)
supersedes historical workflow instructions. Follow these rules when this
repository is checked out on its own:

- Track each change in an owning GitHub issue with outcome and acceptance.
  Inspect status, remotes, existing staging and unrelated edits before writing.
- Oscar assigns work and coordinates the chats. Chats can work concurrently in
  this repository. Keep edits scoped to their issue and preserve unrelated
  edits and staging. Use ordinary Git commands or the optional issue helper
  in the parent workspace.
- Validate the changed outcome locally and obtain independent agent review for
  meaningful code. For application UI changes, follow Safe’s
  [local visual review](https://github.com/We-are-safe/Safe/blob/main/dev/screen-library/LOCAL-REVIEW.md):
  exact before/after commits, synthetic data, matching states/viewports and a
  private issue comparison link. Oscar owns human design acceptance.
- Commit and push completed authorized work before unrelated questions or a turn
  handoff. Stage only the paths for this change.
  Commit as `Codex <codex@openai.com>` with local command overrides. Use `Refs #N`.
- Close only after acceptance and verified publication, with the newest remote
  main commit linked in full, the checked SHA/result and delivery status on the
  issue. A blocked task stays open with the changed paths, completed checks
  and next action. Oscar decides which chat continues the work.
- Keep credentials, customer data, generated evidence and runtime state out of
  Git. Parent development gitlinks may select clean verified pushed child main;
  preserve nested dependency pins. Tags, stable releases and deployments need
  explicit authorization. Main and gitlinks never prove production availability.
