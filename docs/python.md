---
title: My Python Setup
description: Python versions, virtual environments, and packages using uv.
permalink: /python/
---

# Python Setup

This guide covers how I manage **Python** for projects using **uv** (fast Python/packaging tool).

## Requirements
- **uv** installed — see the [uv page]({{ "/uv/" | relative_url }})

## Install / Select Python versions

**Install specific versions**
```bash
uv python install 3.12
uv python install 3.11 3.12
```

**Pin a project to a version (writes .python-version)**
```bash
uv python pin 3.12
```
---

**Create & activate a virtual environment**
```bash
uv venv
source .venv/bin/activate
```

**explicit specify python version and venv folder**
```bash
uv venv --python 3.12 .venv312
source .venv312/bin/activate
```
---

## Packages (pip interface)

**Install a package**
```bash
uv pip install PACKAGE
```

**Upgrade a package**
```bash
uv pip install -U PACKAGE
```

**Editable install (from a local repo)**
```bash
uv pip install -e .
```
---

## Tools: `uvx` and persistent installs [uv tools](https://docs.astral.sh/uv/concepts/tools/)

**Run a tool once (ephemeral)**
```bash
uvx ruff --version
uvx httpie --help
```

**Install a tool persistently and use it**
```bash
uv tool install ruff
ruff --version
```

**Run a specific version or alternate source**
```bash
uvx ruff@latest check
uvx --from git+https://github.com/httpie/cli httpie --help
```

**If a tool isn’t on your PATH after install**
```bash
uv tool update-shell
```
