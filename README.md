# Shared CI workflows

This public repository holds shared reusable CI workflows for freeappstore-online app repositories.

App repositories call `.github/workflows/app-ci.yml` to build their apps and run the store’s platform compliance checks.

## Bumping the compliance CLI pin

`app-ci.yml` pins `@freeappstore/cli` through the `compliance_cli_version`
input default. Before bumping it, run the old and the new CLI (`pnpm install
--frozen-lockfile && pnpm build && npx -y @freeappstore/cli@<v> check`) against
every app that calls this workflow and confirm no app changes result; do not
bump over a regression. See #2 for how that was done for 0.4.10 → 0.4.77.
