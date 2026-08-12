# TRNEIS v2 — Pre-registrazioni pubbliche

Registro pubblico delle previsioni di **TRNEIS v2**, un esperimento personale di
previsione finanziaria falsificabile (10 previsioni a settimana con probabilità
esplicite, risolte da codice deterministico e misurate con Brier score contro
baseline ingenue).

## Come funziona

- **All'emissione** (ogni lunedì) qui viene pubblicato solo `<cohort>.sha256`:
  una riga con l'impronta SHA-256 delle previsioni della settimana. L'impronta
  non rivela nulla del contenuto, ma la data del commit prova che le previsioni
  esistevano — identiche — in quel momento.
- **A cohort risolta** viene pubblicato anche `<cohort>.json` in chiaro, con le
  domande, le probabilità e gli esiti.

## Verifica (chiunque, in qualsiasi momento)

L'hash pubblicato all'emissione deve coincidere con lo SHA-256 del JSON rivelato:

    certutil -hashfile 2026-W34.json SHA256      (Windows)
    sha256sum 2026-W34.json                      (Linux/macOS)

e il risultato deve essere identico al contenuto di `2026-W34.sha256`, il cui
commit precede la risoluzione (fa fede la cronologia Git).

## Meta-previsioni

`E1-E2-E3.md` contiene le tre previsioni pre-registrate **sull'esperimento
stesso** (probabilità dichiarate 0.40 / 0.40 / 0.15) con le definizioni di
risoluzione. Verdetto E1: 10 dicembre 2026, scritto dal codice, mai a mano.
