# Testing

- `vitest.setup.ts` loads `.env` from the parent directory of the checkout (`resolve(import.meta.dirname, "../.env")`), not the repository root, so local test credentials go in `../.env` and any `CODEX_AUTH_JSON*` there leaks into tests: a test that reads Codex slot env vars deletes every inherited `CODEX_AUTH_JSON*` key in `beforeEach` and restores `process.env` in `afterEach`, as `utils/codexHome.test.ts` does [source: https://github.com/anaclumos/pullfrog/pull/1]
