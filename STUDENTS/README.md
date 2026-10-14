# Students — ESTATIO

**Project:** ESTATIO  
**Category:** REAL_ESTATE  
**Upstream:** https://github.com/estatio/estatio  
**Pinned commit:** `82817ed22d00467e33afd290498d684cacccb3f5`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `5ed352908d83f7837bc7f8cd385da6fadd729fb231caf56ab450eea13374ea95`  
**Date:** October 2026

## What this project gives you

A complete worked example of offline-first packaging with a cryptographic audit
chain: source pinned at `82817ed22d00467e33afd290498d684cacccb3f5`, a 16-check assurance suite, an evidence register
with per-check hashes, and an AIOSS ledger chain ending at `5ed352908d83f7837bc7f8cd385da6fadd729fb231caf56ab450eea13374ea95`.

## Learn by verifying

```
python tools/run_bench.py --out BENCH.json
```

Then take any row from `ISOLATED_LAB_RESULTS/03_Result_Register.md`, recompute
the SHA3-256 of its evidence file, and confirm it matches. If it does not match,
the record has been altered — that is the whole point of the chain.

## Licence

Apache 2.0 terms apply to study and teaching use.
