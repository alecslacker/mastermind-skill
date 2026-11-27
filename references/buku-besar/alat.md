# Daftar Alat

Nama, path, versi, untuk apa, batasan. Hanya alat yang sudah jadi dan teruji.

- **patcher.py** — `scripts/patcher.py`, stdlib Python 3.9+. Patch biner berbasis profil JSON; `--check/--apply/--restore`, `--abaikan-hash`, exit code 0–5. Kontrak terverifikasi via `--help` [TERBUKTI 2026-11-27]. Batasan: offset 0-based dari awal berkas; patch semantik (lompatan/NOP) BELUM DIUJI — butuh gcc (lihat ../contoh-patch.md).
- **panintel.py** — `scripts/panintel.py`, stdlib Python 3.9+, offline. Subcommand `check` (satu PAN), `audit` (dump, `--json`, `--limit`), `gen` (PAN sintetis, `--brand`, `-n`, `--broken`, `--out`); exit 0/2/3. Kontrak terverifikasi via `--help` [TERBUKTI 2026-11-27]. Batasan: validasi struktur PAN (Luhn/brand/panjang), bukan kehidupan kartu.
- **lab docker** — `assets/lab/docker-compose.yml`. Lab rentan lokal. BELUM DIUJI di mesin ini (butuh Docker).
- **templat deteksi** — `assets/detection/indikator.yar`, `indikator-sigma.yml`. Templat; isian per sampel belum ada.
