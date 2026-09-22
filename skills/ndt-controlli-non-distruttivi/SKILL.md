---
name: ndt-controlli-non-distruttivi
description: >-
  Verifica se un controllo non distruttivo (PT, MT, UT, RT) dichiarato in un certificato cita la norma/metodo di esecuzione corretta (es. ASTM E165 per PT, E709 per MT, E213/E273 per UT, E94/E1032 per RT, ASME BPVC Sez. V per l'esecuzione generale) — controllo di coerenza tra metodo dichiarato e norma citata, non ancora confronto dei criteri di accettazione. Usa SEMPRE questa skill quando l'utente chiede di verificare un controllo non distruttivo riportato in un certificato.
  ---

  # Controlli non distruttivi (NDT) — coerenza citazione norma per metodo

  ## Quando attivarla

  Un certificato riporta un controllo PT, MT, UT o RT eseguito sull'articolo. Oppure l'utente chiede di verificare la conformità normativa di un controllo non distruttivo.

  ## Norma attesa in funzione del metodo

  | Metodo dichiarato | Norma attesa citata |
  |---|---|
  | PT (liquidi penetranti) | ASTM E165 (esecuzione generale: ASME BPVC Sez. V) |
  | MT (particelle magnetiche) | ASTM E709 (esecuzione generale: ASME BPVC Sez. V) |
  | UT (ultrasuoni) | ASTM E213 o E273 (esecuzione generale: ASME BPVC Sez. V) |
  | RT (radiografia) | ASTM E94 o E1032 (esecuzione generale: ASME BPVC Sez. V) |

  ## Come applicarla (fase attuale — verifica di coerenza citazione)

  Passo (1): identifica quale/i metodo/i NDT sono dichiarati eseguiti sul certificato. Passo (2): per ciascun metodo, controlla che il certificato citi esplicitamente la norma ASTM attesa per quel metodo (e idealmente ASME BPVC Sez. V per l'esecuzione). Passo (3): se per un metodo dichiarato non compare alcuna norma citata, segnalalo come dato mancante. Passo (4): se compare una norma diversa o non pertinente a quel metodo, segnalalo come possibile incoerenza. Passo (5): questo controllo verifica SOLO la presenza/coerenza della citazione normativa, non l'esito del controllo né i criteri di accettazione/rigetto applicati.

  ## Verifica dettagliata dei criteri di accettazione (fase futura, non ancora attiva)

  Un controllo più approfondito (criteri di accettazione/rigetto per metodo, spesso specifici di PO/spec cliente) richiederebbe la tabella di dettaglio in `references/ndt-metodi.md`, oggi non presente. Finché questo file non esiste, non improvvisare criteri di accettazione: limitati al controllo di coerenza della citazione descritto sopra.
  
