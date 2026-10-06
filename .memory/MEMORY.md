# Memory: pullfrog

- Comments cite `wiki/*.md`, `AGENTS.md`, server files such as `utils/codexSecretRotation.ts`, and paths prefixed `action/` that do not exist here, because this repository is the `action/` directory of the private Pullfrog monorepo: read `action/<path>` as `<path>`, read https://docs.pullfrog.com/codex-auth instead of `wiki/codex-auth.md`, and treat server behavior such as `PUT /api/runtime/secret` as unverifiable from this checkout [source: https://github.com/anaclumos/pullfrog/pull/1]
- `internal/index.ts` (package export `./internal`) re-exports utilities such as `parseCodexAuthBody`, `decodeJwtExpMs`, and `verifyCredential` to the Pullfrog web app, which is not in this repository, so `pnpm typecheck` passes on a signature change that breaks that app: grep `internal/index.ts` before changing a utility's signature and keep re-exported signatures additive [source: https://github.com/anaclumos/pullfrog/pull/1]

## Index
- [[codex_auth]]
- [[testing]]
