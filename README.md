# Riemann & Generalized Riemann Hypothesis: Independent Epistemic Verification Dossier

[![Public Audit Dossier](https://img.shields.io/badge/Dossier-Public%20Evidence%20%26%20Certificates-0969da)](manuscript/preprint_rh_grh_epistemic_audit.md)
[![Audited by CoResearcher](https://img.shields.io/badge/Audited%20with-CoResearcher-1f883d)](https://github.com/Fundacion-de-Neurociencias/coresearcher)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](LICENSE)

This repository publishes the complete **verification evidence, cryptographic certificates, axiom traces, topological dependency cartography, and comparative forensic inventories** generated during our independent audit of two November 20, 2026 proof claims targeting the Riemann Hypothesis (RH) and Generalized Riemann Hypothesis (GRH):

1. **Levent Alpöge (+ Claude AI):** `175,187`-file Lean 4 formalization ([alpo.ge](https://alpo.ge/)).
2. **Alessandro Maria Masullo:** `940`-page informal human manuscript ([Ravi Vakil announcement](https://math216.wordpress.com/2026/11/20/hurried-announcement-alessandro-masullo-grh/)).

> [!IMPORTANT]
> **What This Repository Contains — And How To Replicate Automated Audits**
> This public dossier provides **all primary evidence records, logical verification criteria, and reproducible certificates** so any mathematician or reviewer can independently audit every claim and rerun standard Lean 4 (`v4.33.1`) commands.  
> The automated multi-gate auditing platform behind these evaluations is **CoResearcher**, maintained by Fundación de Neurociencias:  
> 👉 **[Explore CoResearcher → https://github.com/Fundacion-de-Neurociencias/coresearcher](https://github.com/Fundacion-de-Neurociencias/coresearcher)**

---

## Executive Summary of Verified Findings

| Target | Scale & Form | Kernel Compilation (`v4.33.1`) | Static Soundness | Structural / Logical Completeness | Epistemic Verdict |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Alpöge RH / Dirichlet GRH** | `175,187` `.lean` files (`17.37M` lines); `28`-line external TCB | **`lake build Main` `exit_code=0`** (`127,812s`) + **`leanchecker --fresh Main` `exit_code=0`** (`26,898s`) on Apple M4 Max 64 GB; `183,889` `.olean` | **0** `sorry`/`axiom`/`native_decide`/`unsafe`; `#print axioms` = `[propext, Classical.choice, Quot.sound]` | Canonical `Mathlib` `RiemannHypothesis` & `DirichletCharacter.LFunction`; ERH unformalized in note | **`VALID_OPAQUE`** (`Epistemia Risk: 0.245` on 5 theorems; `SUSPEND_JUDGMENT` on ERH prose) |
| **Masullo Hecke GRH** | `940`-page PDF (`6.76 MB`), `0` lines of Lean | Not formalized (`0%`) | 0% formal proof | **Critical gap in Chapter 13** (pp. 521–522): empty `13.1`–`13.2`, blank conclusive `Theorem 13.3.1.2`, `19` `??` refs | **`SUSPEND_JUDGMENT`** (`CLAIMED` draft; `Epistemia Risk: 0.850`) |

---

## Dossier Contents & Verifiable Artifacts

- **[Preprint Manuscript](manuscript/preprint_rh_grh_epistemic_audit.md)** — Full scientific manuscript formatted for archival dissemination (EdiTXT / Zenodo).
- **[Epistemic Verification Protocol](reports/epistemic_verification_protocol.md)** — Exact logical specification of the **8 sequential verification gates** and **Contestability Cards** explaining *what* each gate proves without leaking proprietary tooling internals.
- **[Mathematical Architecture Primer ("Chapter 0")](reports/mathematical_architecture_primer.md)** — Accessible mathematical exposition combining `remark.pdf` with dependency cartography across `ReciprocityTheory` (`UniformisationConclusion`, fan-in `2,390`) and the 6 real proof motifs (`15,750` unitary theta-lift modules, `109,260` Galois modularity modules, etc.).
- **[Comparative Forensic Audit: Alpöge vs. Masullo](reports/comparative_audit_alpoge_vs_masullo.md)** — Side-by-side empirical breakdown with exact page/section citations.
- **[Interactive Epistemic Spine Explorer](visualizations/epistemic_spine_explorer.html)** — Standalone D3 visualization of the 43-stratum DAG, 11 libraries, bottlenecks, and 6 barrier-breaking motifs.
- **[Certificates & Logs](certificates/)**:
  - [alpoge_rh_kernel_certificate.json](certificates/alpoge_rh_kernel_certificate.json) — Apple M4 Max compilation metrics, SHA-256 digests, and transparent verification limits.
  - [alpoge_rh_axioms.log](certificates/alpoge_rh_axioms.log) — Raw `#print axioms` trace (`SHA-256: 590d5252...`).
  - [alpoge_rh_leanchecker_fresh.log](certificates/alpoge_rh_leanchecker_fresh.log) — Verbatim `lake env leanchecker --fresh Main` transitive replay log (`26,898s`, `exit_code=0`, `SHA-256: ff8ea3d0...`).
  - [alpoge_static_soundness_summary.json](certificates/alpoge_static_soundness_summary.json) — Full 175,187-file AST/soundness & statement-fidelity audit.
  - [alpoge_epistemic_spine_summary.json](certificates/alpoge_epistemic_spine_summary.json) — Stratified library counts, top-15 pivot modules, and 6 real barrier motifs.
  - [masullo_forensic_summary.json](certificates/masullo_forensic_summary.json) — Verbatim page/section gap audit of the 940-page PDF.
  - [comparative_epistemic_verdicts.json](certificates/comparative_epistemic_verdicts.json) — Trust Ladder rungs, Epistemia risk states, and Contestability Cards.
- **[SHA256SUMS.txt](SHA256SUMS.txt)** — Cryptographic checksum manifest covering every file in this dossier.

---

## Honest Limits & Open Escalation Gates

We explicitly preserve epistemic humility where computational boundaries and kernel lineage distinctions remain open:
1. **Lean `v4.33.1` Compilation & Transitive `--fresh` Replay (Completed):** Clean `lake build Main` (`127,812s`, `exit_code = 0`), `#print axioms`, and full transitive `lake env leanchecker --fresh Main` replay from `mkEmptyEnvironment` (`26,898s` / `7 h 28 min 18 s`, `exit_code = 0`, `SHA-256: ff8ea3d0...`) confirm type-theoretic soundness and rule out `.olean` corruption or environment hacking under the reference Lean C++ kernel.
2. **Bounded-RAM `lean4lean` Module Replay (Active Streaming — `28,357 / 175,187` Cleared):** Using unmodified `digama0/lean4lean@67f63b0c` (`Lean4Lean.Replay.replayFromImports`, 3 workers × 10-module streaming chunks) directly on `.olean` binaries bypasses the monolithic ~`61.57 GB` export wall (`~15.47 GB` combined RSS, `88%` free system memory). As of `2026-11-24T05:19:45Z`, **`28,357 / 175,187`** modules (`616,173` declarations, `0` failures)—including `Statements` (`1/1`), `Lemmata` (`167/167`), `PositivityTheory` (`449/449`), `GroundTheory` (`8,507/8,507`), `Formalism` (`18,254/18,254`), and all `5` elevated-fuel `decide +kernel` modules (`SmallLoop` + `DyadicPrimeIntervals.Run1–Run4`)—have passed locally. **Open limits:** (i) remaining `ReciprocityTheory`, `CompanionTheory`, `Development`, and serial apex modules are still streaming; (ii) `lean4lean` is an external Lean-implemented port sharing C++ kernel design lineage rather than clean-room Rust/C reimplementations.
3. **Clean-Room Flat-Export Checkers (`nanoda` / `con-leche`):** Independent clean-room replay remains open locally on `64 GB` RAM because single-threaded monolithic NDJSON export (`~61.57 GB` full archive) stalled at `46.47 GB` and full flat replay requires high-memory cluster hardware (`82.6–98.8 GiB`+ peak RAM).

---

## Independent Verification Instructions

Anyone can verify checksum integrity locally:

```bash
sha256sum -c SHA256SUMS.txt
```

And independently re-run Lean 4 compilation on the original archive (`SHA-256: 9631b4f020199e580ba86178cb56c6e9b09f690c2369a80dc4334aa93f49c7fc`):

```bash
lake exe cache get
lake build Main
```

To run automated multi-gate scientific claims audits, manuscript gap forensics, statement-fidelity checks, and Epistemia/Contestability governance on your own proofs or preprints, visit **[CoResearcher](https://github.com/Fundacion-de-Neurociencias/coresearcher)**.
