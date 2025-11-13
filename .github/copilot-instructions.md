
# Repository AI Helper (copilot) — Multivendor_Ecommerce

**Purpose:** Provide concise, actionable guidance so an AI coding assistant can be immediately productive in this repository.

**Big Picture:**
- **What:** A Multivendor e-commerce website (see `README.md`). It appears to host web scripts across multiple technologies; expect web frontend + backend components for products, categories, sellers, checkout and multilingual support.
- **Where to look first:** `README.md` (project overview) and top-level files/folders that appear when opening the repository. If new folders appear (e.g., `backend/`, `frontend/`, `docker/`, `requirements.txt`, `pyproject.toml`), treat those as primary system boundaries.

**Immediate goals for an AI assistant:**
- Inspect top-level manifests (`requirements.txt`, `pyproject.toml`, `package.json`, `Dockerfile`) to determine runtime and test commands.
- Prefer changes that are small, well-tested, and documented: add or update a README, add tests next to modified modules, and keep config changes minimal.

**Project-specific conventions (discoverable):**
- **Multitechnology expectation:** Because the README says "web scripts in various technologies", expect mixed-language directories. Before changing code, detect the language by file extensions under each folder.
- **Feature areas:** Files or packages related to `products`, `categories`, `sellers`, `checkout`, and `i18n` are high-impact — prefer conservative edits and add tests.

**Developer workflows & useful commands (Windows PowerShell):**
- **Check remotes:** `git remote -v` to see push/pull targets.
- **Set origin to SSH (recommended to avoid HTTPS auth errors):**
	- `git remote set-url origin git@github.com:binikiya/Multivendor_Ecommerce.git`
	- Create an SSH key (if needed): `ssh-keygen -t ed25519 -C "you@example.com"`
	- Copy public key: `Get-Content $env:USERPROFILE\.ssh\id_ed25519.pub | Set-Clipboard` and add to GitHub -> Settings -> SSH keys.
	- Test: `ssh -T git@github.com`
- **If using HTTPS, use a Personal Access Token (PAT):** create a PAT with `repo` scopes and use it as your password when prompted.
- **Clear stale credentials (Windows):** remove GitHub entries from Windows Credential Manager or run `cmdkey /list` to inspect stored credentials and delete relevant ones.

**When you see git 403 / "Permission denied to <owner>":**
- This means your local authentication (account `bosskiya`) lacks privileges on `binikiya/Multivendor_Ecommerce`.
- Short checklist to resolve:
	1. Confirm remote: `git remote get-url origin`.
	2. If you should push to a fork, make sure `origin` points to your fork (e.g., `git@github.com:bosskiya/Multivendor_Ecommerce.git`).
	3. If you intend to push to `binikiya/Multivendor_Ecommerce`, get collaborator access from the repo owner or push to your fork and open a PR.
	4. Switch to SSH or update stored credentials (see steps above).

**How to propose changes (safe default):**
- Make a feature branch, keep commits small, include a short descriptive message, and push to a fork if you don't have direct push rights.
	- Example flow:
		- `git checkout -b fix/correct-thing`
		- `git add <files>`; `git commit -m "Short: what changed"`
		- `git push --set-upstream origin fix/correct-thing`

**If you add code:**
- Add or update tests (if the project has a test runner). Detect `pytest`, `unittest`, `npm test`, or Docker-based tasks in repo manifests.
- Document the change in `README.md` or add a short `CHANGES.md` entry.

**Files to reference when making decisions:**
- `README.md` — project overview and feature list.
- Any top-level `requirements.txt`, `pyproject.toml`, `package.json`, `Dockerfile`, or CI config (e.g., `.github/workflows`) — these indicate build/test/runtime.

If anything above is unclear or you want me to tailor the instructions to detected frameworks (Django, Flask, Express, etc.), tell me to scan the repo for language-specific files and I'll update this file accordingly.

---
Please review and tell me which parts to expand (e.g., add sample test commands, CI notes, or language-specific setup). Also let me know whether you want me to commit this change and attempt to push it — I can help resolve the `403` by walking through the SSH or PAT steps interactively.

