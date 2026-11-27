# Operasi & Temuan

Format: satu entri per operasi, max 10 baris, beri label [TERBUKTI]/[HIPOTESIS].
Baca sebelum operasi baru; tulis entri baru di bawah. Tanpa tanggal = tidak berlaku.

## [2026-11-18] curl.exe (System32, 711.736 byte) — patch banner
- hasil: offset 542880 (0x55 'U' → 0x58 'X') mengubah "Usage" jadi "Xsage" [TERBUKTI]
- bukti: ../contoh-patch.md (rantai REA CLI + uji --check/--apply/--restore)
- jebakan: offset 542880 dari REA cocok dengan pencarian manual — jalur REA tak mengarang
- ulang: patcher.py --file curl.exe --profil <prof.json> --check (lalu --apply, --restore)

## [2026-11-27] patcher.py & panintel.py — verifikasi identitas
- hasil: kedua script --help jalan, exit 0, stdlib saja, Python 3 [TERBUKTI]
- bukti: eksekusi --help di Windows (Git Bash) sesi ini; kontrak flag/subcommand tercatat di alat.md
- jebakan: --abaikan-hash hanya untuk build mirip, bukan untuk salinan yang diserahterimakan
- ulang: python3 scripts/patcher.py --help && python3 scripts/panintel.py --help
