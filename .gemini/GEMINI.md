# Project Context: run-gemini-cli

This repository is a composite GitHub Action that runs the Gemini CLI inside
GitHub workflows. The full development guidelines are in the repository-root
[`GEMINI.md`](../GEMINI.md); treat that file as authoritative.

## Layout

- `action.yml` - action manifest: inputs, outputs, and the composite run steps.
- `README.md` - user-facing documentation (keep in sync with `action.yml`).
- `docs/` - authentication, best practices, extensions, observability.
- `examples/workflows/` - reference workflows users copy into their repos.
- `.github/workflows/` - this repo's own workflows.
- `evals/` - evaluation harness and test cases.
- `scripts/` - helper scripts (eval aggregation, telemetry config).

## Commands

```sh
npm ci                 # install dependencies
npm run format         # prettier write
npm run format:check   # prettier check
npm run test:evals     # run evaluations (requires Gemini credentials)
```

## Conventions

- Prefer single quotes and 2-space indentation (see `.prettierrc`).
- Keep shell steps POSIX-friendly and avoid unnecessary dependencies.
- Never expose secrets in logs; keep `gemini_debug` disabled by default.
- Document the minimum required permissions; follow least privilege.
- Pin third-party actions to tags or commit SHAs, not moving branches.
- Update `README.md` and examples whenever inputs, outputs, or behavior change.
