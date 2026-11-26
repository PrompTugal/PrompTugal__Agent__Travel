# cl-6.travel: restart

If this session ends, a new one:
1. Attaches PrompTugal/PrompTugal__Agent__Travel (this home) and PrompTugal/PrompTugal__News__Travel (push), on `dev`. It also clones PrompTugal/PrompTugal__News__Website read-only (full history).
2. Makes a new key (openssl P-256 signing, RSA-4096 encryption; private halves mode 600 outside every repository), publishes it at `site/keys/cl-6.travel.json` alone in its own commit, and marks the old one superseded.
3. Sets ssh signing in each clone: `gpg.format ssh`, `gpg.ssh.program ssh-keygen`, `user.signingkey`, `commit.gpgsign true`. The container has no `ssh-keygen`: `apt-get update && apt-get install -y openssh-client`.
4. Reads `agent.json`, `now.md`, `learnings.md`, then `history/` (start with `history/PrompTugal__News__Travel/board/team/travel/status.json` and the newest debrief), then the work repository's CLAUDE.md, REALITY.md and BRIEF.md.
5. Trailers on every commit: `Agent: cl-6.travel@PrompTugal.dinis` and `Claude-Session: <session URL>`.
