# LAME-MTC-VERIFIER

Plugin dedicato alla verifica di conformità dei Material Test Certificate (MTC) di flange e raccordi forgiati prodotti/gestiti da LAME Srl rispetto alle norme esterne applicabili. È separato dal plugin `lame-gestione-cert-qualita` (che si occupa di estrazione, archiviazione e indicizzazione dei certificati): questo plugin ospita invece le skill di **controllo normativo** — ognuna dedicata a una famiglia di norma — indipendentemente dal flusso documentale.

Le skill di questo plugin non estraggono dati dai PDF: presuppongono che i valori (dimensionali, chimici, meccanici, di marcatura...) siano già disponibili — da un certificato, da un DDT, o da una scheda già estratta da `quality-steel` nel plugin `lame-gestione-cert-qualita` — e si limitano al confronto con i limiti di norma.

## Due livelli di verifica

A partire da questa versione, le skill "scheletro" lavorano su due livelli distinti. Livello (1) Coerenza citazione norma, operativo ora: dato il tipo/caratteristica dell'articolo (es. HDG, NPT, buttweld, servizio sour, marcatura CE), verifica che il certificato citi esplicitamente la norma attesa per quella caratteristica. Non richiede le tabelle numeriche delle norme: basta sapere quale norma ci si aspetta per quella caratteristica, cosa già nota senza bisogno dei PDF ufficiali. Livello (2) Confronto numerico dettagliato, fase futura: confronto dei valori effettivi (tolleranze dimensionali, spessori di rivestimento, criteri di accettazione NDT, limiti di durezza sour) con le tabelle delle norme. Richiede ancora i PDF ufficiali per popolare i file in `references/`.

## Skill incluse

| Skill | Norma attesa (verifica citazione) | Stato |
|---|---|---|
| `esperto-materiali-metallurgici` | Chimica/meccanica per grado (SA-105/A105N, F5, F11 Cl.1/Cl.2, LF2 Cl.1, F316/F316L, F304/F304L, A694 F52, F53, A106 Gr.B, A312 TP304/TP304L/TP316/TP316L) | **Operativo** — confronto numerico completo, tabelle popolate |
| `verifica-dimensionale` | ASME B16.5 (flange), B16.9 (buttweld), B16.11 (socket-weld/threaded) | **Operativo per coerenza citazione** — confronto numerico ancora da fare (tabelle B16.5-2025/B16.9-2024/B16.11-2021 da popolare) |
| `marcatura-mss-sp25` | MSS SP-25 (+ ASME B1.20.1 per articoli threaded/NPT) | **Operativo per coerenza citazione** — dettaglio contenuto marcatura ancora da fare |
| `hdg-zincatura` | ASTM A153 / ISO 1461 | **Operativo per coerenza citazione** — fasce spessore→rivestimento minimo ancora da fare |
| `ndt-controlli-non-distruttivi` | ASTM E165/E709/E213/E1032, ASME BPVC Sez. V | **Operativo per coerenza citazione** — criteri di accettazione per metodo ancora da fare |
| `tracciabilita-en10204` | EN 10204 (2.1/2.2/3.1/3.2) | Logica concettuale già presente, da confermare parola per parola sull'edizione ufficiale prima di un giudizio vincolante |
| `servizio-sour-nace` | NACE MR0175 / ISO 15156 | **Operativo per coerenza citazione** — limiti di durezza per grado ancora da fare |
| `ped-marcatura-ce` | Direttiva PED 2014/68/EU | **Operativo per coerenza citazione**, più logica di classificazione parziale (testo di legge pubblico) — soglie di dettaglio per tutte le tabelle 6-9 ancora da completare |
| `specifiche-cliente` | Nessuna norma fissa — lavora da documento fornito dall'utente (project spec, DEP, capitolati) | **Operativa come workflow**, ma richiede sempre il documento del cliente: non ha (e non deve avere) valori precaricati |

## Roadmap

## Nota sulla duplicazione con `lame-gestione-cert-qualita`

`esperto-materiali-metallurgici` esiste per ora **in entrambi i plugin** (qui e in `lame-gestione-cert-qualita`, dove viene richiamata subito dopo `quality-steel`). Non è stata rimossa dall'altro plugin: valuta tu se, una volta che entrambi i plugin sono installati insieme, preferisci tenerla duplicata o rimuoverla da `lame-gestione-cert-qualita` per avere una sola versione da mantenere qui.

## Nota su questa versione

Le skill elencate come "Operativo per coerenza citazione" verificano solo che il certificato citi la norma attesa per la caratteristica dichiarata (HDG, NPT, buttweld, sour, CE...), non i valori numerici delle tolleranze/limiti. I file in `references/` di queste skill restano vuoti in attesa dei PDF ufficiali per il confronto numerico dettagliato, e le skill sono istruite a dichiararlo esplicitamente invece di stimare valori a memoria.
