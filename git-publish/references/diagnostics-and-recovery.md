# Diagnostics and recovery: expanded cookbook

## Read-only reconnaissance (safe first)

- `git ls-remote <URL>` before fetch/push when host state is unknown — a read; writes no refs.
- After fetch: `git log --oneline --decorate origin/main`, `git ls-tree -r --name-only origin/main`, `git show --stat origin/main`, and diff as needed (`git diff main origin/main`; know two-dot vs three-dot). Substitute the branch you push.
- Network triage order: local git config → env vars → OS/WinHTTP proxy → fetch tool's own settings that ignore env → `curl -x` probe → DNS/TLS specifics. Cert-verification fixes belong in the trust store; never `-k` silently, never for real secrets.
- SSH: split reachability from auth (`ssh -T -o BatchMode=yes -o ConnectTimeout=12 git@github.com`); a missing key is a config step — generate locally in `~/.ssh` (user space) and add the PUBLIC key on the host (user action).

## Refusal and divergence playbook

- Non-fast-forward: fetch → diff → merge (both lines preserved) or rebase (linear) → resolve → commit → push. Unrelated histories: same, plus `--allow-unrelated-histories`, stated plainly. Substitute the branch you push throughout.
- Undo map: `git merge --abort` (pre-commit); amend (unpushed commits only); after a merge, `ORIG_HEAD` is the review point; reflog recovers local accidents (local only, never shared).
- Force-push policy: last resort; explicit request; consequence stated (remote history rewritten, others must reconcile). Branch protections and permission failures are answered by the owner, never bypassed.
- Land states: 401/403 → credentials/permissions, ask; empty remote → normal first push; 404 → URL/name/visibility (confirm with the owner, don't infer); branch-name mismatch vs host default → push the named branch and set upstream, or ask.

## Credentials and non-interactive sessions

- No credentials in argv (shell history, process listings), files, or chat; prefer credential stores (`credential.helper`/GCM here), env vars, SSH keys. If a secret was exposed anywhere, rotate it.
- No-tty sessions: batch modes, stored credentials, `GIT_TERMINAL_PROMPT=0` to fail cleanly; interactive SSO/browser flows may simply not run there — use the user's terminal session instead of working around prompts with literals.
- A `.gitignore` entry does not un-commit a file: check the staged diff, not just ignore rules.

## Windows and PowerShell notes (verified on this machine 2026-11-11)

- PowerShell 5.1: no `&&`/`||` chaining, no `VAR=val cmd` prefix, no coreutils (`head` etc.) by default — use native syntax, `$env:VAR`, native pipes; check `$PSVersionTable.PSVersion`.
- Proxy schemes: `socks5h://` was rejected by the .NET stack git rides on here — use `http://` proxies or per-command `-c` overrides; never silently edit the user's global git config.
- Machine/port/network facts (proxy listener, reachability) are environment-dependent and change with reconfiguration — the `local-proxy` skill owns those; re-verify rather than assume.
