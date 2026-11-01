# gha-upload-artifact

A reusable GitHub Composite Action for uploading workflow artifacts, compatible with both GitHub Actions and local executions using [`act`](https://github.com/nektos/act).

## Overview

This action provides a unified interface for uploading artifacts in both GitHub Actions and local `act` environments.

It automatically selects the appropriate version of `actions/upload-artifact`:

- **GitHub Actions:** Uses `actions/upload-artifact@v7`.
- **Local `act` execution:** Uses `actions/upload-artifact@v5`.

The execution environment is detected automatically using the `ACT` environment variable. No additional configuration is required.

## Usage

Add the following step to your GitHub Actions workflow:

```yaml
- name: Upload artifact
  uses: ariaci/gha-upload-artifact@v1
  with:
    name: build-artifacts
    path: ./dist/
```

The same workflow can be executed locally using `act` without modifications.

## Inputs

| Input | Required | Description |
|---|---|---|
| `name` | Yes | Name of the artifact to upload. |
| `path` | Yes | Path to the file or directory to upload. |

## Requirements

- GitHub Actions or a compatible `act` environment.
- Appropriate permissions and artifact upload support in the execution environment.

## License

This project is licensed under the [MIT License](LICENSE).