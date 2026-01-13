## Hi there 👋

# VidAI

A Scotland-based startup building a high-performance **AI gateway with built-in guardrails** for production LLM deployments.

We focus on what matters in production: **security**, **reliability**, **latency**, and **control**—not just swapping model providers.

---

## Core Offering

### ⚙️ Vidai.Server *(Enterprise)*  
An AI gateway that enforces **runtime guardrails**, **rate limits**, **audit trails**, and **structured output guarantees**—without sacrificing performance.

- Sub-15ms p99 latency, 6,000+ RPS per core
- Zero-copy Rust data plane
- Full sovereignty: your prompts, responses, and logs never leave your infrastructure
- Pluggable guardrail policies (e.g., PII redaction, prompt injection detection, schema enforcement)

> Guardrail *models* (e.g., classifiers, validators) are optional extensions—you bring your own or use lightweight defaults.

---

## Open Source Tools

### 🧪 [VidaiMock](https://github.com/vidaiUK/VidaiMock)  
Realistic, zero-dependency mock server for LLM APIs (OpenAI, Anthropic, Bedrock, etc.).  
- Simulates streaming, tool calls, errors, and latency  
- ~7MB static binary—no Docker, no DB  
- Ideal for testing, CI, and local dev

### 🧰 [VidaiSDK](https://github.com/vidaiUK/vidaisdk)  
Python SDK with drop-in OpenAI compatibility and **automatic structured output**.  
- Enforces JSON/schema compliance at the client  
- Works standalone or with Vidai.Server for end-to-end guarantees  
- Supports aliasing and clean provider abstraction

---

## Under the Hood

- Models can be optimized via **ONNX** or **Candle** for lower latency—but this is optional. The gateway works with any standard LLM endpoint.
- No vendor lock-in. No hidden telemetry.
- Built for teams that need **production-grade control** without bloated middleware.

---

> 🏴 Based in Scotland. Open source where it helps developers. Enterprise-ready where it matters.

Opaque third-party APIs are a liability. The future belongs to enterprises that own their:
- **Model weights**  
- **Inference logs**  
- **Latency budgets**

VidAI provides the infrastructure to deploy cutting-edge AI **privately, securely, and efficiently**—bridging the gap between frontier models and controlled, on-prem or sovereign cloud environments.

## Radical Efficiency

Modern AI software is bloated. We stripped it back. By engineering our core in **Rust** with **zero-copy architecture**, we eliminate waste—not just to cut costs, but to ensure **long-term reliability** and **environmental responsibility**.

---

> 🏴 VidAI is proudly headquartered in **Scotland**, committed to sustainable innovation and open, transparent AI infrastructure.
