---
name: git-publish
description: |
  Publish a local git repository to its remote: repository init, commit identity,
  remote wiring, proxy-aware connectivity checks, push with refusal handling
  (fetch first, non-fast-forward, unrelated histories via merge/rebase), and
  post-push parity verification. Triggers on: "push this repo", "publish to
  GitHub/GitLab", "git push rejected", "remote contains work you do not have",
  "unrelated histories", "set up git and push", "推送这个仓库". Use when a
  folder, plugin, or project is ready for its first push, or after local and
  remote history diverged.
license: MIT
compatibility: |
  Verified on this machine 2026-11-11: Git 2.45.1, Windows PowerShell 5.1 (no
  &&/|| chaining, no VAR=val command prefix, no coreutils like `head` on PATH),
  and a machine-specific local proxy. Proxy/host/port facts are environment
  dependent — re-verify; see the `local-proxy` skill.
metadata:
  version: "1.0"
  note: Personal workflow skill; built from a real publish flow (2026-11-11).
---

# Git publish flow: local repo to remote

Scope: first push and divergence repair for a local repository. Not account registration, not credential entry (user-only, never via chat/commands), not proof that app/GUI-level behavior works.

## Ground rules (before any command)

- Push, tag, release, and registry publish are externally visible: confirm scope with the user first, state the command and why, keep an auditable trail.
- Config steps are local and reversible (`init`, `config`, `remote add`); ref-mutating steps are not — sequence accordingly; read probes (`ls-remote`) are safe anytime.
- Never put credentials in commands, files, or chat; prefer stores/env/keys (see references for non-interactive and storage notes).

## 1. Preflight the payload

- Verify byte-parity when shipping copies of local files (hash before and after copy).
- Keep out runtime/user data and secrets: session state, logs, caches, DBs, local config. Review what will be committed (status + staged diff, and history before the first publish when unsure).
- Ship ecosystem metadata: package manifest/exports, license with a real copyright line (no placeholders), README, `.gitignore` (deps, dist, logs, OS junk).
- Separate evidence types: byte-parity/imports/registration checks are not GUI- or app-level acceptance — label them as they are.

## 2. Build local history (cheap to change now)

- `git init -b main` (older Git: `-b` may be unsupported — fall back and set the branch per host default).
- Identity at repo scope while scope is undecided: set local `user.name` and `user.email` (`git config --local …`) to real values. Going global is a user decision; check surprises (`git config --list --show-origin` shows system and global layers too).
- Review status and staged diff → commit with a meaningful message → confirm `git log --oneline` and a clean tree. Unpushed commits are the cheap, amendable phase.

## 3. Wire the remote; check the route (config ≠ network)

- `git remote add origin URL`; verify with `git remote -v`. Wiring contacts nothing.
- Don't declare "network is broken" before checking layers: env proxies (`HTTP(S)_PROXY` etc.), git config (`http.proxy`, global or local), OS/WinHTTP proxy, and fetch tools whose own settings ignore env.
- Proxy schemes can trip git/dotnet stacks — `socks5h://` is rejected by some builds ("ServicePointManager does not support socks5h"). Prefer a command-scoped override (`-c http.proxy=http://127.0.0.1:2080 -c https.proxy=…`) over silently rewriting the user's global config; health-probe with `curl.exe -x`; proxy facts are machine-specific — follow the `local-proxy` skill and re-verify.
- Read probes with auth-aware expectations: 200/301/404 vs 401/403 semantics; 404 ≠ proof of privacy — confirm visibility with the owner.
- SSH reachability vs auth split: `ssh -T -o BatchMode=yes git@github.com` → permission-denied(publickey) means reachable with no usable key; read the actual error before diagnosing.
- Sessions without a tty cannot answer prompts: prefer credential stores/batch modes; `GIT_TERMINAL_PROMPT=0` to fail cleanly instead of hanging.

## 4. Push; triage refusals

- First push and any divergence: `git fetch origin`, then inspect (`git ls-remote`, then `git log` / `git ls-tree -r` / `git show` for the remote branch, e.g. `origin/main`) — see what exists before integrating.
- Non-fast-forward / "fetch first": integrate deliberately — `git merge origin/main` (default: both lines preserved; substitute the branch you push) or rebase (linear); record which and why. Unrelated histories: `git merge --allow-unrelated-histories` (explicit; note it in the message when it looks odd).
- Resolve conflicts by content (real data over placeholder) → `git add` → commit. Undo map: `git merge --abort` pre-commit; `git reset --hard ORIG_HEAD` post-commit only with a clear head and the tree understood.
- Never reflex-force. `push --force` rewrites remote history others may have pulled: only with explicit request/justification, consequence stated. Protection/permission failures are answered by the owner, never bypassed.
- No secrets anywhere in the transaction — objects, messages, refs. Scan history before first publish when unsure.

## 5. Verify and close

- `git ls-remote origin`; `git rev-list --left-right --count HEAD...origin/main` (expect 0/0; substitute the pushed branch); `git ls-tree -r --name-only origin/main`; `git status -sb` (tracking, e.g. `## main...origin/main`).
- Report observed output as-is; list what stayed unverified and how to close it.

## 6. Scratch and hygiene

- Temp/test scripts in the OS temp area, removed after use; no stray files or processes; call out leftovers that exist.

Full cookbook and edge cases: [references/diagnostics-and-recovery.md](references/diagnostics-and-recovery.md).
