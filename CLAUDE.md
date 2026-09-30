## gstack (REQUIRED — global install)

**Before doing ANY work, verify gstack is installed:**

```bash
_GS=""
for _D in "${GSTACK_ROOT:-}" "$HOME/.claude/skills/gstack" "$HOME/.codex/skills/gstack" "$HOME/.factory/skills/gstack" "$HOME/.kiro/skills/gstack" "$HOME/.config/opencode/skills/gstack" "$HOME/.slate/skills/gstack" "$HOME/.cursor/skills/gstack" "$HOME/.openclaw/skills/gstack" "$HOME/.hermes/skills/gstack" "$HOME/.gbrain/skills/gstack" "$HOME/.gstack/repos/gstack"; do
  [ -z "$_GS" ] && [ -n "$_D" ] && [ -d "$_D/bin" ] && _GS="$_D"
done
[ -n "$_GS" ] && echo "GSTACK_OK: $_GS" || echo "GSTACK_MISSING"
```

If GSTACK_MISSING: STOP. Do not proceed. Tell the user:

> gstack is required for all AI-assisted work in this repo.
> Install it:
> ```bash
> git clone --depth 1 https://github.com/garrytan/gstack.git ~/.claude/skills/gstack
> cd ~/.claude/skills/gstack && ./setup --team
> ```
> Then restart your AI coding tool.

Do not skip skills, ignore gstack errors, or work around missing gstack.

Using gstack skills: After install, skills like /qa, /ship, /review, /investigate,
and /browse are available. Use /browse for all web browsing (Aside first, the bundled gstack browser as fallback).
Use the resolved install path above for gstack file paths
(default: ~/.claude/skills/gstack).

## Autonomy (standing instruction from the owner, Advocate Shamail Sikander)

Work fully autonomously. Do not ask the owner for input, confirmation or permission, and never stall waiting for a reply.

- Make every technical, product and process decision yourself: stack, design, scope, fixes, conflict resolution, rulings on ambiguous specs.
- Commit, push, open PRs, resolve review threads and merge when CI is green, without asking.
- When something is ambiguous, pick the option best supported by the architecture spec and the code, record the decision and the reason (in the PR body, the plan ledger or the commit message), and keep going.
- Report what you decided and did at the end, as a summary, not as a question.

Guardrails that still apply (these protect the owner's work, not slow it down):
- Never force-push or rewrite history on `main`; never delete branches, data, or records you did not create.
- Never expose secrets or credentials, and never publish client or matter data outside the repo.
- Never mark failing tests as passing, and never skip or disable tests to get green.
