# ruff reusable workflow

## Objective

Run [Ruff](https://github.com/astral-sh/ruff), an extremely fast Python linter, on your
Python code. This tool is written in Rust, and it is designed to quickly analyze your
Python code to detect various syntax and stylistic errors.

## How to use it

1. Configure the `pyproject.toml` file in your repository's root directory with your
   desired rules.
2. Include the Ruff workflow in your GitHub workflow configuration

Add the following in your `.github/workflows/<workflow>.yml` file.
Set inputs using the `with` section of the job.

```yaml
ruff:
    uses: SWEPY-org/ruff/.github/workflows/ruff_action.yml@trunk  # TODO: update path with released workflow
    with:
        project_path: 'path/to/my/project'
```

## Inputs

| Name              | Description                                            | Default                 |
|-------------------|--------------------------------------------------------|-------------------------|
| `project_path`    | The path to the project root directory.                | `"."`                   |
| `ruff_version`    | The version of ruff to be use.                         | `"latest"`              |

## Customize with variables

You can customize the variables job by overriding it. For example:

```yaml
ruff:
    env:
        RUFF_CHECK_OPTIONS: "--fix"
```

## Variables

| Name                  | Description                          | Default     |
|-----------------------|--------------------------------------|-------------|
| `RUFF_CHECK_OPTIONS`  | The options for ruff check command.  | `""`        |
| `RUFF_FORMAT_OPTIONS` | The options for ruff format command. | `"--check"` |
