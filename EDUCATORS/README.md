# Educators — ESTATIO

**Project:** ESTATIO  
**Category:** REAL_ESTATE  
**Upstream:** https://github.com/estatio/estatio  
**Pinned commit:** `82817ed22d00467e33afd290498d684cacccb3f5`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `5ed352908d83f7837bc7f8cd385da6fadd729fb231caf56ab450eea13374ea95`  
**Date:** October 2026

## Teaching with ESTATIO

The project is usable as a worked example of offline-first packaging with a
cryptographic audit chain. It ships with the assurance suite, the evidence
register and the ledger, so students can verify claims rather than take them on
faith.

## Suggested exercises

1. Run `python tools/run_bench.py --out BENCH.json` and read the 16 results.
2. Recompute the SHA3-256 of a row's evidence file and compare to the register.
3. Walk the AIOSS chain from genesis to head `5ed352908d83f7837bc7f8cd385da6fadd729fb231caf56ab450eea13374ea95` and confirm every link.
4. Break one artifact and observe the chain fail to verify.

## Licence for teaching

Apache 2.0 terms apply to academic and teaching use. See `24_ANTICOMMONS_LICENSE`.
