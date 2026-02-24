# CI Consumer Fixture

This minimal CMake project is used by `.github/workflows/test-ci-integration.yml`
to validate the analyzer in a "consumer project" scenario:

- a real `compile_commands.json` generated in CI,
- analysis executed through the composite GitHub Action (`uses: ./`),
- JSON/SARIF artifacts validation.

The code intentionally contains one out-of-bounds stack write to keep the test
signal stable and easy to validate.

