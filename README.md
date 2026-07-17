# pidman.dev

Containerized [Pi Coding Agent](https://www.npmjs.com/package/@earendil-works/pi-coding-agent) powered by Debian Sid and Node.js 26.

A ready-to-use Docker/Podman image that bundles the Pi coding agent with essential development tools in an isolated, reproducible environment.

## Quick Start

### Prerequisites

- [Podman](https://podman.io/) or [Docker](https://www.docker.com/)

### Build

```bash
podman build -t pidman.dev -f Dockerfile.pi .
```

### Run

```bash
podman run --rm -it \
  -v "$(pwd):/workspace:Z" \
  -v "$HOME/.config/pi.dev:/root/.pi/agent:Z" \
  pidman.dev
```

Replace `$(pwd)` with your project directory path. The second volume mount persists the agent's configuration across runs.

## Image Contents

| Component       | Version / Details          |
| --------------- | -------------------------- |
| Base image      | Debian Sid (slim)          |
| Node.js         | 26.5.0                     |
| Pi Coding Agent | Latest from npm            |

### Included Tools

`bash`, `ca-certificates`, `curl`, `git`, `gnupg`, `jq`, `libatomic1`, `make`, `openssh-client`, `procps`, `ripgrep`, `tree`, `unzip`, `wget`, `xz-utils`, `zip`

## License

This project is provided as-is. See the [Pi Coding Agent](https://www.npmjs.com/package/@earendil-works/pi-coding-agent) for its licensing terms.