# LAME-MTC-VERIFIER

Plugin dedicato alla verifica di conformità dei Material Test Certificate (MTC) di flange e raccordi forgiati prodotti/gestiti da LAME Srl rispetto alle norme esterne applicabili. È separato dal plugin `lame-gestione-cert-qualita` (che si occupa di estrazione, archiviazione e indicizzazione dei certificati): questo plugin ospita invece le skill di **controllo normativo** — ognuna dedicata a una famiglia di norma — indipendentemente dal flusso documentale.

Le skill di questo plugin non estraggono dati dai PDF: presuppongono che i valori (dimensionali, chimici, meccanici, di marcatura...) siano già disponibili — da un certificato, da un DDT, o da una scheda già estratta da `quality-steel` nel plugin `lame-gestione-cert-qualita` — e si limitano al confronto con i limiti di norma.

## Skill incluse

| Skill | Norma | Stato |
|---|---|---|
| `esperto-materiali-metallurgici` | Chimica/meccanica per grado (SA-105/A105N, F5, F11 Cl.1/Cl.2, LF2 Cl.1, F316/F316L, F304/F304L, A694 F52, F53, A106 Gr.B, A312 TP304/TP304L/TP316/TP316L) | **Operativo** — tabelle popolate, copiato dalla versione più aggiornata già in uso in `lame-gestione-cert-qualita` |
| `verifica-dimensionale` | ASME B16.5 (flange), B16.9 (buttweld), B16.11 (socket-weld/threaded) | Scheletro — tabelle da popolare (B16.5-2025, B16.9-2024, B16.11-2021) |
| `marcatura-mss-sp25` | MSS SP-25 | Scheletro — requisiti di marcatura per tipo articolo da popolare |
| `hdg-zincatura` | ASTM A153 / ISO 1461 | Scheletro — fasce spessore→rivestimento minimo da popolare |
| `ndt-controlli-non-distruttivi` | ASME BPVC Sez. V, ASTM E165/E709/E213/E1032 | Scheletro — criteri di accettazione per metodo da popolare; nota che il "quale NDT richiesto" dipende spesso da PO/spec cliente |
| `tracciabilita-en10204` | EN 10204 (2.1/2.2/3.1/3.2) | Logica concettuale già presente, da confermare parola per parola sull'edizione ufficiale prima di un giudizio vincolante |
| `servizio-sour-nace` | NACE MR0175 / ISO 15156 | Scheletro — limiti aggiuntivi per grado da popolare |
| `ped-marcatura-ce` | Direttiva PED 2014/68/EU, Allegato II | **Parzialmente popolata** (testo di legge pubblico, non a pagamento come le norme ASME) — logica di classificazione e principali soglie/esclusioni note raccolte; soglie di dettaglio per tutte le tabelle 6-9 ancora da completare |
| `specifiche-cliente` | Nessuna norma fissa — lavora da documento fornito dall'utente (project spec, DEP, capitolati) | **Operativa come workflow**, ma richiede sempre il documento del cliente: non ha (e non deve avere) valori precaricati |

## Roadmap

## Nota sulla duplicazione con `lame-gestione-cert-qualita`

`esperto-materiali-metallurgici` esiste per ora **in entrambi i plugin** (qui e in `lame-gestione-cert-qualita`, dove viene richiamata subito dopo `quality-steel`). Non è stata rimossa dall'altro plugin: valuta tu se, una volta che entrambi i plugin sono installati insieme, preferisci tenerla duplicata o rimuoverla da `lame-gestione-cert-qualita` per avere una sola versione da mantenere qui.

## Nota su questa versione

`verifica-dimensionale` è installato ma **non ancora operativo per il confronto numerico**: i file in `skills/verifica-dimensionale/references/` contengono solo la struttura delle tabelle attese, non i valori. La skill stessa è istruita a dichiararlo esplicitamente invece di stimare valori a memoria. Vanno popolati con l'edizione ufficiale della norma (PDF ASME/ANSI) prima dell'uso reale su un certificato.
