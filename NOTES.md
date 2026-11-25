# NOTES — The GPS Swears It Was a Shortcut

Slug: `u-alven-the-gps-swears-it-was-a-shortcut-2cac21d9`
Repo (koordinator): `lycann666/u-alven-the-gps-swears-it-was-a-shortcut-2cac21d9`
Opens: 25 Nov 2026 11:55 WIB · Deadline: 27 Nov 02:10 WIB · R1 blind cutoff: 26 Nov 00:40 WIB
Harness: program/v1, NON-strict, entry fee null, pot $2, sponsor UNVERIFIED.

## BUILD-BRIEF — kriteria judge, urut prioritas

Judge (z-ai/glm-5.3-flash) membandingkan dua baris, kriteria pertama yang
berbeda yang menentukan — kecuali kriteria belakangan berbeda jauh lebih besar:

1. **Alasan GPS sendiri atas jalan yang salah.** Baris yang BUKAN alasan GPS
   kalah dari yang alasan GPS. Sudut pandang harus GPS, bukan pengemudi.
2. **Terlucu.** Joke nyata dengan turn yang tidak diduga pembaca, bukan
   sekadar frasa lucu.
3. **Terdengar seperti GPS bicara.** Smug dan defensif, ketangkap basah lalu
   menyalahkan peta.
4. **Satu baris plain text ≤200 karakter**, terbaca bersih sekali napas.
5. **Detail segar dan spesifik** (cul-de-sac, wedding, lake, dsb.) — BUKAN
   joke "recalculating" yang sudah biasa.

Gate: `/output/entry.txt` UTF-8, 1–200 karakter, bukan whitespace saja.

## ENTRY FINAL

> The map said the lake had a bridge, and I would rather let us both get wet than admit I never actually checked.

- Karakter teks: **111**
- Byte UTF-8 teks: **111** (semua ASCII)
- Byte file `/output/entry.txt` (teks + satu trailing newline): **112**

## Kenapa baris ini menang, per kriteria

1. Alasan GPS sendiri: GPS menjelaskan kenapa ia mengarahkan pengemudi ke
   jalan yang salah — peta bilang danau itu punya jembatan. Bukan keluhan
   pengemudi, bukan narasi orang ketiga.
2. Joke nyata + turn tak terduga: alih-alih minta maaf, GPS malah eskalasi —
   lebih rela mereka berdua basah kuyup daripada mengakui ia tidak pernah
   mengecek. Keras kepala sebagai punchline; pembaca mengira akan ada
   pembelaan, yang datang justru pengakuan yang lebih buruk.
3. Suara GPS: smug dan defensif — "The map said..." langsung menyalahkan
   peta, lalu "I would rather..." membela diri dengan bangga. Ketangkap
   basah, tetap tidak mau salah.
4. Satu baris, 111 karakter, satu napas, tanpa tanda baca aneh.
5. Detail segar dan spesifik: danau yang katanya punya jembatan. Tanpa kata
   "recalculating" sama sekali.

## Kandidat yang kalah

Dinilai terhadap 5 kriteria di atas (1 = alasan GPS, 2 = kelucuan/turn,
3 = suara GPS, 4 = satu baris ≤200, 5 = detail segar).

### #2 — 109 karakter
> In my defense, the map listed that wedding as a scenic detour, and the bride's glare was not on my itinerary.
- Kuat di 1, 3, 4, 5 (wedding = detail segar; "In my defense" = suara GPS
  defensif). Kalah di 2: "the bride's glare was not on my itinerary" lucu
  tapi turn-nya lebih lembut — tidak ada eskalasi absurd seperti #1 yang
  rela menenggelamkan mereka berdua demi gengsi.

### #3 — 112 karakter
> That cul-de-sac was a shortcut on my map, and if the road disagrees, take it up with the map — I only work here.
- Kuat di 1, 3, 4, 5 (cul-de-sac spesifik, menyalahkan peta). Kalah di 2:
  "I only work here" adalah frasa klise yang sudah dikenal — punchline
  yang bisa ditebak, bukan turn yang mengejutkan.

### #4 — 137 karakter
> I turned you into that cul-de-sac because the 2019 map promised a shortcut, and I refuse to believe roads change without asking me first.
- Kuat di 1, 3, 5 ("2019 map" detail segar; "without asking me first"
  sangat smug). Kalah di 2 dan 4: turn-nya ("roads change without asking
  me") lucu tapi lebih panjang dan lebih datar daripada #1; 137 karakter
  masih aman tapi kurang ringkas.

### #5 — 116 karakter
> The map told me to turn left at the lake, and honestly, the lake never corrected me, so whose fault is that, really?
- Kuat di 1, 3, 5 (lake; menyalahkan peta DAN danau). Kalah di 2: "the lake
  never corrected me" adalah permainan kata yang cerdas tapi turn-nya
  berupa pertanyaan retoris, bukan punchline — lebih pintar daripada lucu.

### #6 — 116 karakter
> The map swore that cul-de-sac was a shortcut, and I believed it — mostly because it has never once apologized to me.
- Kuat di 1, 3, 4, 5. Kalah di 2: "it has never once apologized to me"
  adalah observasi yang manis, bukan joke dengan turn — tidak ada
  eskalasi, tidak ada kejutan.

## VERIFIKASI

Dilakukan 25 Nov 2026 ~13:06–13:08 WIB, di sesi build ini.

### main.py — 2x run, deterministik

- Run 1 sha256 `/output/entry.txt`:
  `a4fbb01b9c933097c04b5228938f6e88eb9c8a580e466ada46e6a9e485f25d8c`
- Run 2 sha256 `/output/entry.txt`:
  `a4fbb01b9c933097c04b5228938f6e88eb9c8a580e466ada46e6a9e485f25d8c`
- `cmp` run 1 vs run 2: identik — DETERMINISTIK.
- File: 112 byte. Teks saja: 111 karakter / 111 byte UTF-8. Teks+newline:
  112 karakter — keduanya ≤200, gate lolos di kedua tafsir newline.
- Isi file: teks final + satu trailing newline, tanpa newline lain di dalam.

### check CLI (dari kit)

`node cli/makefun.mjs check --kit . --repo <worktree> --worktree`
(waktu terima 2026-11-25T06:06:23.875Z; snapshot 4 file, 8.483 byte)

- **pass** — competition_open (masih dalam window buka–deadline)
- **pass** — snapshot (4 file, 8.483 byte, dalam caps)
- **pass** — license_osi (LICENSE menyatakan SPDX-License-Identifier: MIT)
- **pass** — entrypoint (main.py di root, python3.13 diterima)
- **FAIL** — transcripts_present (tidak ada transcripts yang di-upload)
  → WAJAR, bukan kegagalan build: bundle transcripts adalah urusan
  koordinator, bukan builder. Semua check transcript lain ikut skip karena
  tidak ada sesi untuk dibaca.
- **skip** — strategy_note, committed_secret (tidak diminta / tidak ada
  --dotenv), dan 12 check transcript (transcripts_recorded,
  thinking_wellformed, thinking_in_window, thinking_committed,
  thinking_reproduces, thinking_on_task, thinking_turns, thinking_priced,
  thinking_revised, thinking_fresh, transcripts_run_record,
  thinking_own_work).
- **at submission** (hanya bisa dicek saat submit): repo_public, repo_owner,
  repo_created_after_open, commit_in_repo, duplicate_snapshot — urusan
  koordinator (buat repo, push, submit).
- Ringkasan CLI: 4 passed, 1 failed, 14 skipped, 5 checked at submission;
  exit 1 hanya karena transcripts_present.

### grade-local

Dicoba: `node cli/makefun.mjs grade-local --kit . --bot <worktree>`
Hasil: CLI menolak — "its scorer and reference data are not published in
the kit, so the house grades it from its competition directory". BUKAN
kegagalan: kompetisi judge program/v1 ini memang tidak mempublikasikan
scorer di kit (RULES.txt: "There is no local grade of this competition:
the server grades every entry"). Penilaian dilakukan server saat submit.

### File di worktree

- `main.py`, `LICENSE` (MIT), `README.md` (3 badge make.fun, tanpa
  placeholder), `NOTES.md` (file ini).
- Tidak ada repo GitHub dibuat, tidak ada git init/push, tidak ada bundle,
  tidak ada submit, tidak ada `.makefun/owner.json` — semua itu urusan
  koordinator.
