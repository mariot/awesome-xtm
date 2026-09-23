# Awesome XTM [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of tools, utilities, and projects for working with the **XTM suite** ([OpenCTI](https://github.com/OpenCTI-Platform/opencti) + [OpenAEV](https://github.com/OpenAEV-Platform/openaev)) — deployment, infrastructure provisioning, developer tooling, and testing/simulation.

Inspired by [Awesome-Geospatial](https://github.com/sacridini/Awesome-Geospatial), [awesome-compose](https://github.com/docker/awesome-compose), and [awesome-copilot](https://github.com/github/awesome-copilot).

## Contents

- [Deployment & Infrastructure](#deployment--infrastructure)
- [Developer Tooling](#developer-tooling)
- [Testing & Simulation](#testing--simulation)
- [Contributing](#contributing)

## Deployment & Infrastructure

- **[Liftoff](https://github.com/mariot/liftoff)** — Ansible deployment toolkit for the XTM suite on Linux hosts. Installs Docker, deploys OpenCTI/OpenAEV plus their connectors/collectors/injectors and supporting infrastructure services, using the same playbook for local VM testing (via Multipass) and cloud provisioning (via Mars/OVH).
- **[Mars](https://github.com/mariot/mars)** — Provisions OVH OpenStack virtual machines for XTM deployments. Creates the SSH keypair and VM on OVH and outputs the public IP, either standalone or chained straight into Liftoff (`just mars-up-and-deploy`) for a one-command cloud deploy.

## Developer Tooling

- **[gh-xtm-launchpad](https://github.com/mariot/gh-xtm-launchpad)** — A GitHub CLI extension (Go/Cobra) that syncs the `connectors` and `collectors` upstream repos locally, builds their Docker images, and runs them with an env file generated from `docker-compose.yml` — a fast local loop for developing/testing a connector or collector image.
- **[poetry2uv](https://github.com/mariot/poetry2uv)** — A CLI that migrates a Poetry-managed `pyproject.toml` to a uv-native one, including the "conditional local-path dependency" pattern used by OpenAEV collectors that `uvx migrate-to-uv` can't handle. Verified to produce package sets identical to `poetry install` across the full collectors repo.
- **[xtm-copilot-skills](https://github.com/mariot/xtm-copilot-skills)** — GitHub Copilot skills and Docker Compose stacks to spawn an isolated OpenAEV, OpenCTI, or full XTM suite (with XTM Composer, Mailpit, RabbitMQ, etc.) from a released image or a local build, for testing connectors, collectors, injectors, and executors through Composer or the platform directly.

## Testing & Simulation

- **[Mimikyu](https://github.com/mariot/Mimikyu)** — A small Flask app to simulate and manage inject expectations and traces: a web UI plus API endpoints that generate payloads for expectations, documents, and security platforms, backed by a self-initializing SQLite database.
- **[ofapi](https://github.com/mariot/ofapi)** — Fake APIs (FastAPI) simulating third-party data sources and services (Shodan, Censys, Slack, Gmail, Microsoft Graph, and more), so OpenCTI connectors and OpenAEV injectors/collectors can be exercised end to end without real credentials or external network calls.

## Contributing

Contributions welcome! If you have a tool that helps working with the XTM suite (OpenCTI/OpenAEV), see [CONTRIBUTING.md](CONTRIBUTING.md) and open a PR.

## License

[CC0](https://creativecommons.org/publicdomain/zero/1.0/) — to the extent possible under law, this list and its contents are dedicated to the public domain.
