# CI Consumer Fixture

This minimal CMake project is used by `.github/workflows/test-ci-integration.yml`
to validate the analyzer in a "consumer project" scenario:

- a real `compile_commands.json` generated in CI,
- analysis executed through the composite GitHub Action (`uses: ./`),
- JSON/SARIF artifacts validation.

The code intentionally contains one out-of-bounds stack write to keep the test
signal stable and easy to validate.



## CI integration modes

This demo repository contains both supported integration styles:

- GHCR image (pinned tag): `.github/workflows/coretrace-analysis.yml`
- GitHub Action module (pinned tag): `.github/workflows/coretrace-analysis-action-tag.yml`

Notes:
- The GHCR workflow runs on push/PR/main and uses `ghcr.io/coretrace/coretrace-stack-analyzer-ci:v0.1.2`.
- The Action-tag workflow is `workflow_dispatch` only to avoid duplicate runs.
