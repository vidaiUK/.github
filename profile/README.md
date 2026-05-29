# Vidai

**The sovereign AI control plane.** A single binary that sits in the
path of every AI request, governing cost, policy and audit from
inside your own infrastructure. Drop-in with any SDK, any provider.

---

## Why this exists

Every AI request your enterprise makes is a cost event, a policy
question, and an audit obligation. Today most teams meet that with
seven middleware libraries chained together at the application
layer — each with its own supply chain, its own update cadence,
and its own latency. Vidai replaces the chain with one boundary
the platform team can actually defend.

Opaque third-party APIs are a liability. The future belongs to
enterprises that own their model weights, their inference logs,
and their latency budgets.

---

## Products

### [Vidai.ControlPlane](https://vidai.uk) (commercial · free Community edition)

The control plane that lives in the request path of every AI call.

- **In-path attribution** — every request priced and tagged to a
  team, user, application and model the moment it returns
- **Enforced spend control** — hard caps that stop the next call when
  a budget is breached, not alerts about calls that already ran
- **Content-aware policy** — PII redaction, region locks, model
  allow-lists, applied inline
- **Sovereign deployment** — runs as a single binary inside your VPC
  or on-prem. No phone-home. No data egress.
- **Cross-provider neutrality** — OpenAI, Anthropic, Gemini, Bedrock,
  Vertex, Azure OpenAI, plus self-hosted Llama and Mistral

**Verified performance:** 21,803 requests per second sustained,
1.95 ms median overhead under load, 25 MB binary, zero data egress.
Measured on a single legacy 8-core node (Intel Xeon E3-1240 v3) so
the figure is a floor, not a ceiling.

→ Architecture, use cases and pricing at **[vidai.uk](https://vidai.uk)**
→ Documentation at **[docs.vidai.uk](https://docs.vidai.uk)**
→ Self-install Docker releases (Community / Scale / Enterprise — same bundle, your `vidai.license` chooses the edition) at **[github.com/vidaiUK/vidai-quickstart](https://github.com/vidaiUK/vidai-quickstart)**

### [Vidai.Mock](https://github.com/vidaiUK/VidaiMock) (open source · Apache 2.0)

A wire-accurate LLM mock server for CI. Production-accurate
streaming, errors and agent-loop termination for OpenAI, Anthropic,
Gemini, Bedrock — offline, deterministic, and free.

- Docker Compose for local, single binary for CI, or build from source
- Multi-arch Docker images (linux/amd64 + linux/arm64)
- Apache 2.0
- Releases are cosign-signed; verify with
  [vidai.uk/.well-known/cosign.pub](https://vidai.uk/.well-known/cosign.pub)

→ Repo: **[github.com/vidaiUK/VidaiMock](https://github.com/vidaiUK/VidaiMock)**

---

## Upstream contributions

### [adk-python](https://github.com/vidaiUK/adk-python) — fork of Google ADK (Apache 2.0)

A fork of [google/adk-python](https://github.com/google/adk-python) with
**one targeted change**: a single environment variable, `ADK_LLM_BASE_URL`,
that redirects the endpoint for every LLM provider at once — Gemini,
Anthropic, and OpenAI-compatible alike.

Upstream lets you set `base_url` per model in code. The maintainers
declined to add env-var support; reasonable for a framework whose
audience mostly runs Google's own models, but it leaves multi-vendor
developers wiring `base_url` by hand in every project.

This fork takes the other tradeoff: point an entire agent stack at a
proxy or gateway by setting one environment variable — no code changes,
vendor-independent by default. Auto-synced with upstream daily.

```bash
pip install "git+https://github.com/vidaiUK/adk-python.git@stable"
```

→ Repo: **[github.com/vidaiUK/adk-python](https://github.com/vidaiUK/adk-python)**

---

## Release verification

Every Vidai release artefact is signed with the Vidai release key,
published at:

```
https://vidai.uk/.well-known/cosign.pub
```

The canonical landing page with the SHA-256 fingerprint, the
verification principle, and the key-rotation policy is at
**[vidai.uk/cosign](https://vidai.uk/cosign)**.

---

## Engineered for efficiency

Modern AI infrastructure is bloated. We stripped it back. A core
written in Rust with a zero-copy data path eliminates waste — not
just to cut costs, but to make the latency budget predictable and
the environmental footprint honest. One node runs an order of
magnitude more traffic than the seven-library equivalent it replaces.

---

## Archived

- **VidaiSDK** — the original Python SDK shipped at
  [vidaiUK/vidaisdk](https://github.com/vidaiUK/vidaisdk) has been
  superseded. Vidai.ControlPlane works drop-in with the OpenAI,
  Anthropic and Gemini SDKs directly; no Vidai-specific SDK is
  needed. The repo remains visible for historical reference.

---

## Where to find us

- 🌐 **[vidai.uk](https://vidai.uk)** — marketing site, blog and benchmarks
- 📘 **[docs.vidai.uk](https://docs.vidai.uk)** — full product documentation
- 💼 **[LinkedIn](https://www.linkedin.com/company/vidai-uk)** — Vidai UK Limited
- 🏢 **[Crunchbase](https://www.crunchbase.com/organization/vidai-uk)** — company profile
- ✉️ **hello@vidai.uk** for general enquiries
- 🔒 **security@vidai.uk** for vulnerability disclosure
  (see also [vidai.uk/.well-known/security.txt](https://vidai.uk/.well-known/security.txt))

---

🏴󠁧󠁢󠁳󠁣󠁴󠁿 Glasgow, Scotland · UK · Vidai UK Limited
