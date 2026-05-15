# cbt_hyb_exm

**CBT Hybrid Examination — a conceptual architecture for large-scale secure examinations.**

This repository hosts the open-source conceptual model.
The full architecture brief lives in **[`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md)**.

---

## What it is

A modular, auditable framework for compiling, randomising, and distributing large-scale examination question papers — built for transparency, security, and adaptability.

- Question papers are **compiled early** by domain contributors and deduplicated by an AI filter.
- The question paper is **generated late** — exactly one hour before the exam (T−60) — by a seeded RNG plus a non-collision Scrambler.
- Sealed sets are **distributed via CDN** to exam centres; the decryption key is released at T−15.
- Execution is **hybrid**: computers *render* the paper; candidates *answer* on a paper OMR sheet.
- The hall runs **offline** during the session.

No real organisation, board, or institution is referenced. This is a neutral conceptual proposal.

---

## Read first

| Document | Purpose |
|---|---|
| **[`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md)** | The complete architecture brief — overview, workflow, pipeline, modules, operational rules, deployment, Mermaid diagrams. |

If you only have time to read one file, read `docs/ARCHITECTURE.md`.

---

## Operational stages at a glance

| # | Stage | Purpose |
|---|---|---|
| 1 | **Compile** | Domain contributors submit per quota. |
| 2 | **Filter** | AI deduplication; ceiling check. |
| 3 | **Book** | Locked, version-controlled question pool. |
| 4 | **Generate** | At T−60, RNG draws a paper; Scrambler ensures non-collision. |
| 5 | **Deliver** | Sealed sets distributed via CDN; decryption key released at T−15. |
| 6 | **Execute** | Offline session; computer renders, candidate marks OMR. |

---

## Repository usage

Clone the repository and read the brief:

```bash
git clone https://github.com/nishanbhuinya/cbt_hyb_exm.git
cd cbt_hyb_exm
$EDITOR docs/ARCHITECTURE.md
```

Mermaid diagrams in `docs/ARCHITECTURE.md` render natively on GitHub.

---

## License

[MIT](LICENSE) — use freely, adapt freely, share improvements.

---

## Contributing

Adaptations are welcome. The model is intentionally modular — every parameter is a variable, every stage is replaceable. If you build a variant, please document it.
