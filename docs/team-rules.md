# Team rules for main (S-5)

Stage 0 - S-5 Branch rules (free plan) and pull-request template. File in repo: `docs/team-rules.md`.

GitHub Free keeps the repository private but cannot lock `main`. So `main` stays safe in three free
ways: every PC refuses a direct push to `main`, CI runs on every pull request, and the team merges only
green pull requests. No paid plan or paid tool is used anywhere.

## Rules

1. **Never push to `main`.** Push a branch and open a pull request.
2. **Squash merge only.**
3. **Merge only when CI is green.** A pull request with a red check is not merged.
4. **Delete the branch after the merge.**
5. **Ask a review** when the pull request touches contracts, database migrations or security code
   (the folders below). Tick the box in the pull-request template and ask one teammate.

## Folders that need a review

From the file layout (Build Guide §1: "ask a review for contracts, migrations, security"):

| Kind | Folders |
|---|---|
| Contracts | `platform/scada-common/`, `platform/scada-proto/`, `platform/scada-schemas/`, `acquisition/scada-driver-api/`, `server/scada-eventbus/` |
| Migrations | the Flyway folder of every module (`src/main/resources/db/migration/`) |
| Security | `server/scada-security/` |

## One-time setup

- **Each developer, once per clone:** `git config core.hooksPath dev/git-hooks`
- **Repository owner, once (GitHub: Settings > General > Pull Requests, both are free):**
  allow only "Squash merging", and switch on "Automatically delete head branches".
