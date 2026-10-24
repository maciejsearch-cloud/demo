# Dane rozbioru zdań (warstwa rozumienia)

Pliki `*-pdb-*.json.gz` / `test-pdb.json.gz`: UD_Polish-PDB (Alina Wróblewska i in., IPI PAN),
https://github.com/UniversalDependencies/UD_Polish-PDB, rev 27235e131fae – licencja **CC BY-NC-SA 4.0**
(https://creativecommons.org/licenses/by-nc-sa/4.0/). Zmiany: konwersja CoNLL-U → JSON (form, lemma, upos, feats, head, deprel).

Pliki `*-lfg-*.json.gz` / `test-lfg.json.gz`: UD_Polish-LFG (Agnieszka Patejuk, Adam Przepiórkowski, IPI PAN),
https://github.com/UniversalDependencies/UD_Polish-LFG, rev 890f3855c915 – licencja **GPL-3.0**. Zmiany: jak wyżej.

`walenty.json.gz`: Walenty – słownik walencyjny języka polskiego (IPI PAN), https://zil.ipipan.waw.pl/Walenty,
wersja 2021-07-12, schematy zweryfikowane – licencja **CC BY-SA 4.0**. Zmiany: schematy → listy pytań (KTO/CO, KOMU/CZEMU…).

Podziały są oficjalne (train / dev / test); test służy wyłącznie do bramki role-F1 (`meta.json` → `eval_files`, `eval_sha`).
Generowanie: `scripts/export_rozbior.py`, `scripts/export_walenty.py`.
