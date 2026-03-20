# Code quality tooling

This repository includes baseline Clang tooling configuration at the repository root:

- `.clang-format`
- `.clang-tidy`
- `.clangd`

## Formatting check

Run formatting checks without rewriting files:

```bash
clang-format --dry-run --Werror <files>
```

Example:

```bash
clang-format --dry-run --Werror appstate.cpp pumps.cpp
```

## Static analysis check

Run clang-tidy using compile commands from the repository-root `compile_commands.json`:

```bash
clang-tidy -p . <files>
```

Example:

```bash
clang-tidy -p . appstate.cpp pumps.cpp
```

## Notes

- The formatting column limit is set to 100 to match the guideline target, with 120 treated as a
  soft upper bound for exceptional cases.
- Indentation is spaces-only (`UseTab: Never`).
