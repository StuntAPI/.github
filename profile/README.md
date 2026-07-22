<p align="center">
  <img src="assets/stunt-banner.png" alt="stunt — local API simulators" width="100%">
</p>

<p align="center">
  <strong>Local API simulators — test against real public APIs without remote accounts, network, or bills.</strong>
</p>

<p align="center">
  <a href="https://stuntapi.com">stuntapi.com</a> ·
  <a href="https://github.com/stuntapi/stunt">stunt (the tool)</a> ·
  <a href="https://stuntapi.com/adapters">adapter catalog</a> ·
  <a href="https://github.com/stuntapi/stunt/blob/main/AGENTS.md">docs</a>
</p>

<p align="center">
  <img alt="license" src="https://img.shields.io/badge/license-Apache--2.0-FFD400?style=flat-square&colorA=0E0E0E">
  <img alt="adapters" src="https://img.shields.io/badge/adapters-91-FFD400?style=flat-square&colorA=0E0E0E">
  <img alt="language" src="https://img.shields.io/badge/built%20with-Go-FFD400?style=flat-square&colorA=0E0E0E">
  <img alt="status" src="https://img.shields.io/badge/status-pre--1.0-FFD400?style=flat-square&colorA=0E0E0E">
</p>

---

## What is stunt?

`stunt` is an open-source tool that spins up **local simulators** for the public APIs
your code calls — a **stunt double** for the real thing. Instead of creating remote
accounts, fighting rate limits, and paying for sandboxes, you run a faithful local mock
that behaves like the real API (stateful, real-shaped responses, webhooks).

```bash
brew install stuntapi/tap/stunt   # or: go install stuntapi.com/stunt/cmd/stunt@latest
stunt demo                         # boots a stateful Stripe-style sim + prints curl commands
```

## Why

You just want to write a feature. The API has other plans — account-gated sandboxes,
slow approval, rate limits at 2am, test modes that don't fire webhooks, surprise bills.
**stunt** stands in: a safe, local, deterministic stand-in so your tests run offline and
reset clean.

## Highlights

- **Stateful, not stubbed** — create a charge, list it, capture it, watch the webhook fire. SQLite-backed state survives across requests.
- **Sandboxed adapters** — adapter logic runs in a Starlark VM: no filesystem, no network, no `load()`. Safe to install a stranger's mock.
- **91 reference adapters** — Stripe, Twilio, GitHub, Slack, AWS, Google Workspace, and 86 more, all **embedded in the binary** (no cloning).
- **All four transports** — REST, gRPC (unary + streaming), WebSocket, and GraphQL.
- **Synthetic, enforced** — `stunt adapter lint` rejects real-looking data (emails, tokens, cards). Everything is fake by construction.
- **Operable by machines** — `--json` on catalog/plan/doctor, an `AGENTS.md`, and a `stunt llm` reference so coding agents drive it unaided.

## The repos

| Repo | What |
| --- | --- |
| [`stunt`](https://github.com/stuntapi/stunt) | The Go tool — the simulator engine, CLI, and 91 embedded adapters. |
| [`stunt-www`](https://github.com/stuntapi/stunt-www) | The stuntapi.com website (TanStack Start + Cloudflare Pages). |

## Get involved

- ⭐ Star [`stunt`](https://github.com/stuntapi/stunt) if it unblocks you.
- 🐛 [Open an issue](https://github.com/stuntapi/stunt/issues) for bugs or adapter requests.
- 🛠️ Adapters are just a YAML manifest + sandboxed Starlark — see [`CONTRIBUTING.md`](https://github.com/stuntapi/stunt/blob/main/CONTRIBUTING.md).

---

<p align="center">
  <sub>Made in Europe with care by <a href="https://github.com/stuntapi">@stuntapi</a> / <a href="https://github.com/deblasis">@deblasis</a></sub>
</p>
<p align="center">
  <sub>Apache-2.0 · pre-1.0 · the safe stand-in for the real thing</sub>
</p>
