<div align="center">

# Siamang Labs

### Open-source tools that treat hard problems as code — from reproducible research to LLM inference.

*Version your questionnaire in Git · deploy a live survey · fit ~20x more LLM context into the
same GPU.*

[**🌐 siamang.org**](https://siamang.org/?utm_source=github&utm_medium=oss&utm_campaign=beta30)
·
[**🧪 Try the demo (no signup)**](https://demo.siamang.org/?utm_source=github&utm_medium=oss&utm_campaign=beta30)
·
[**⭐ tamarin**](https://github.com/Siamang-Labs/tamarin)
·
[**⭐ siamang**](https://github.com/Siamang-Labs/siamang)
·
[**in LinkedIn**](https://www.linkedin.com/company/siamang-labs)

</div>

---

## What we build

| Project | What it is | |
|---|---|---|
| **[tamarin](https://github.com/Siamang-Labs/tamarin)** | Reversible **KV-cache compression** for LLM inference — fit ~20x more context into the same GPU, without deleting tokens. | `🆕 open source` |
| **[siamang](https://github.com/Siamang-Labs/siamang)** | The open-source survey/research **engine** — questionnaire-as-code, validation, deploy, analysis. | `⭐ open source` |
| **Siamang Cloud** | The managed platform on top of siamang — repos, live deploys, response DB, dashboards, connectors. | [`siamang.org`](https://siamang.org/?utm_source=github&utm_medium=oss&utm_campaign=beta30) |

## 🐒 Tamarin — compression as an index, not a deletion

At long context the KV cache, not the weights, decides whether your workload fits. Tamarin (the
`hsq` package — Hierarchical Semantic Quantization) compresses it **reversibly**: compressed
tokens act as routing keys, and their exact originals are pulled back into attention when the
query actually needs them.

- **12–28x smaller GPU KV cache** — and the ratio *grows* with context (22.8x @8K, 27.9x @32K).
- **<0.5% perplexity overhead on 4–14B models**, 96–97% token-for-token agreement with baseline.
- **Retrieval statistically equivalent to baseline** (paired battery, n=500 per cell) up to 32K.
- **Composes with int4 weight quantization for free** — weights /4 and KV /21 on one GPU.

Status: **beta**, statistically validated on Qwen3 0.6B–14B — full report with CIs in
[docs/RESULTS.md](https://github.com/Siamang-Labs/tamarin/blob/main/docs/RESULTS.md).
Apache-2.0.

## 📋 Research-as-code — treat surveys like software

- **Version control** for the whole instrument — commits, review, rollback.
- **Validation on every commit** — catch broken logic before it reaches a respondent.
- **A real data layer** — Postgres, with exports to CSV / XLSX / **SPSS .sav** / Parquet / JSON.
- **Reproducible analysis** — scripts, not hand-edited spreadsheets.
- **Open engine, no lock-in.**

### 🎁 Open beta — 30 days of Pro, free (no credit card)

**[Siamang Cloud](https://siamang.org/?utm_source=github&utm_medium=oss&utm_campaign=beta30)** is
the managed platform: unlimited projects & responses, all live connectors, team roles, scheduled
runs. It's an **early beta** — expect a few rough edges, and tell us what breaks.

## Get involved

⭐ Star [tamarin](https://github.com/Siamang-Labs/tamarin) and
[siamang](https://github.com/Siamang-Labs/siamang) · 💬 Join
[Discussions](https://github.com/Siamang-Labs/siamang/discussions) · ✉️ Questions, commercial
inquiries, collaboration — **info@siamang-team.org**

<sub>📄 <a href="https://github.com/Siamang-Labs/siamang/blob/main/docs/cloud/terms-of-use.md">Terms</a> ·
<a href="https://github.com/Siamang-Labs/siamang/blob/main/docs/cloud/privacy-policy.md">Privacy</a></sub>

<sub>© 2026 Siamang Labs LLC</sub>
