# Stage 0 - S-5 Branch rules (free plan) and pull-request template

Files (the paths are the same as in the repository):

| File | What it is |
|---|---|
| `dev/git-hooks/pre-push` | Git hook: refuses a push to `main` |
| `.github/pull_request_template.md` | Pull-request template |
| `docs/team-rules.md` | Team rules and the folders that need a review |

## Set up (each developer, once)

    git config core.hooksPath dev/git-hooks

On Linux and macOS the hook must be executable: `git update-index --chmod=+x dev/git-hooks/pre-push`
(the file needs LF line endings; S-1's `.editorconfig` sets that).

## Check (done check)

    git push origin main
    -> Push to main refused: push a branch and open a pull request.

A push of any other branch is not affected. The second done check (a pull request with a red check is
not merged) needs the CI workflow from S-1.

## Notes

- A hook cannot stop `git push --no-verify`; this is the free-plan trade-off the card accepts.
- The card does not list "the critical folders"; I took them from the file layout (Build Guide §1) -
  please confirm the list in `docs/team-rules.md`, especially the Flyway path.
