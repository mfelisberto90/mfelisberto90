# Murilo Felisberto

**Full-Stack Product & Systems Engineer** | Founder at **[RoleLane](https://rolelane.co.uk)**  
Edinburgh, Scotland, UK | [rolelane.co.uk](https://rolelane.co.uk)

I build multi-tenant SaaS products, deterministic financial backends, and low-footprint Linux systems where your tenant boundaries and your money maths aren't allowed to drift.

When you're shipping billing, margin controls, or compliance workflows for real businesses, "mostly right" isn't good enough. I don't rely on hidden UI buttons for authorisation, and I won't let binary floats touch our commercial ledgers. Instead, I enforce row-level isolation directly inside PostgreSQL 17, price every contract in exact integer minor units (`pence` and `cents`) or `fractions.Fraction`, and gate every pull request we merge behind automated E2E and security-invariant checks.

## Production Systems

### [RoleLane](https://rolelane.co.uk)
Multi-tenant UK staffing, rate-card margin, compliance, and billing SaaS that I've built and operate from Edinburgh.

We handle shift lifecycles, statutory compliance checks, rate-card margin calculations, and client invoicing inside one workspace, and we make sure agencies and client teams can't read a single row outside their own boundary. Under the hood, we run **PostgreSQL 17 `FORCE ROW LEVEL SECURITY` across 70+ tables** under a least-privilege `NOBYPASSRLS` runtime role, paired with **Laravel 12 / PHP 8.4**, **Vue 3 / Inertia v2**, **PHPStan Level 8**, and **Playwright E2E** suites.

## Open-Source Repositories

- **[`msfPDF`](https://github.com/mfelisberto90/msfPDF)** [![CI](https://github.com/mfelisberto90/msfPDF/actions/workflows/ci.yml/badge.svg)](https://github.com/mfelisberto90/msfPDF/actions/workflows/ci.yml)  
  Sub-millisecond (0.16–0.47 ms) zero-rendering-dependency `%PDF-1.4` vector document engine with 1:1 parity across **Rust**, **Web-Standard TypeScript** (`0` runtime `npm` dependencies), and a **standalone CLI**. We bypass 500 MB headless Chromium bloat and HTML/SVG SSRF risks entirely by compiling declarative JSON specs (`A4`, `Letter`, and 80 mm thermal slips) directly into pure 7-bit ASCII vector primitives, built-in Standard Type 1 `/WinAnsiEncoding` octal typography, pure `GF(256)` Reed-Solomon vector QR codes, exact minor-unit currency maths, and an atomic `0600` multi-tenant vault.
- **[`ledger-guard`](https://github.com/mfelisberto90/ledger-guard)** [![CI](https://github.com/mfelisberto90/ledger-guard/actions/workflows/ci.yml/badge.svg)](https://github.com/mfelisberto90/ledger-guard/actions/workflows/ci.yml)  
  My hexagonal Python 3.12 commercial order pricing, exact `Fraction` unit-of-measure conversion, and four-eyes margin-approval reference engine. We run FastAPI HTTP routes and a Model Context Protocol (`POST /mcp`) JSON-RPC tool server over the exact same `OrderService`. If your caller lacks `valuation:cost:read` or `orders:margin:read`, we strip raw cost and margin fields before serialisation while still enforcing your margin floor server-side, backed by PostgreSQL 17 `FORCE RLS` DDL and 65 OWASP ASVS Level 2 tests.
- **[`hybridbox`](https://github.com/mfelisberto90/hybridbox)**  
  An async Python (FastAPI + WebSockets) and Linux/ARM64 systems bridge I wrote so you can turn spare Android hardware into low-latency headless Linux/X11 and media appliances instead of leaving good silicon in a drawer.

## Core Stack & Standards I Ship By

1. **Deterministic Money & Margin Maths**: If you split a 3-pack case (`1/3` ratio) or spread header discounts across lines, our `fractions.Fraction` and `ROUND_HALF_EVEN` minor-unit arithmetic won't leak pennies, and pass-through freight never inflates your margin basis.
2. **Database-Enforced Tenant Isolation**: We pair PostgreSQL 17 `FORCE ROW LEVEL SECURITY` with two-stage transaction-local context binding, optimistic concurrency `version` checks, and `SHA-256` payload-bound idempotency (`409` on mismatch).
3. **Dual-Transport AI & Web Security**: Whether your team hits REST endpoints or connects an AI copilot over MCP tools, you get identical server-side RBAC, `HMAC-SHA256` multi-bucket rate limiters, per-request CSP nonces, and Luhn PAN log redaction.
4. **Core Stack & CI Gates**: I work daily across Python 3.12 (`FastAPI`, `uv`, `pytest`, `mypy --strict`, `ruff`), PHP 8.4 (`Laravel 12`, `PHPStan Level 8`), Rust (`Axum`, `Tokio`, `<15 MB` single-binary daemons), TypeScript (`Vue 3`, `Playwright`), and PostgreSQL 17 on Linux.
