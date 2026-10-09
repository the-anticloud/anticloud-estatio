# Technical Architecture — ESTATIO

**Upstream:** [https://github.com/estatio/estatio](https://github.com/estatio/estatio)
**License:** Apache 2.0
**Category:** REAL_ESTATE
**Anticloud Integration:** PAX L5 Narrow L2 General 27B + AIOSS + Offline-First

## Upstream Description

Open estate management built on Apache Isis

## Anticloud Architectural Changes

1. PAX L5 Narrow L2 General 27B local property description generation (offline, no API calls)
2. AES-256 encryption at rest for all tenant and lease records
3. Single-binary deployment via PyInstaller — no Docker, no cloud dependency
4. AIOSS append-only audit chain on every lease mutation and payment record
5. Offline floor plan analysis using quantized vision model
6. Zero-telemetry: all analytics replaced with local aggregation
7. CLI management interface replacing web-only admin panel
8. SQLite-first persistence replacing cloud database defaults

## Integration Points

- **PAX Inference Socket:** Local HTTP endpoint at `127.0.0.1:11434/v1/chat` — same OpenAI-compatible API, zero cloud
- **AIOSS Hook:** Every write operation calls `aioss_append(event, payload)` before commit
- **Encryption Layer:** All file I/O routed through `anticloud_crypto.encrypt_at_rest()`
- **Single Binary Build:** `pyinstaller anticloud_estatio.spec` or `go build -o estatio`

## Deployment Modes

| Mode | Hardware | Notes |
| --- | --- | --- |
| Edge CPU | Raspberry Pi 4 / Intel NUC | Full feature set, PAX on CPU |
| Desktop GPU | RTX 3060 / A10 | PAX GPU inference, <1s latency |
| Server | 2× A100 | Full batch throughput |
| Air-gapped | Any x86/ARM | Zero network dependency |