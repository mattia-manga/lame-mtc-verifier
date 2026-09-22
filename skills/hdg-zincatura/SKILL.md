---
name: hdg-zincatura
description: >-
  Verifica se un articolo dichiarato HDG (hot-dip galvanizing / zincatura a caldo) cita nel certificato la norma di zincatura corretta (ASTM A153/A153M o ISO 1461/EN ISO 1461) — controllo di coerenza tra caratteristica dichiarata e norma citata, non ancora confronto numerico degli spessori. Usa SEMPRE questa skill quando l'utente chiede di verificare la zincatura di un articolo, o quando un certificato/DDT riporta un articolo HDG/galvanized/zincato.
  ---

  # Zincatura a caldo (HDG) — coerenza citazione norma

  ## Quando attivarla

  Un certificato/DDT riporta un articolo dichiarato HDG, galvanized o zincato. Oppure l'utente chiede di verificare la conformità normativa della zincatura di un articolo.

  ## Norma attesa in funzione del mercato

  | Mercato/riferimento in certificato | Norma attesa citata |
  |---|---|
  | ASTM, mercato Nord America | ASTM A153 o ASTM A153M |
  | EN, mercato europeo | ISO 1461 o EN ISO 1461 |

  Se il certificato non specifica il mercato/sistema di riferimento, verifica quale delle due norme compare citata esplicitamente, oppure segnala l'ambiguità.

  ## Come applicarla (fase attuale — verifica di coerenza citazione)

  Passo (1): verifica che l'articolo sia effettivamente dichiarato HDG/galvanized/zincato nel certificato o nei dati estratti. Passo (2): controlla che nel certificato compaia esplicitamente la citazione di ASTM A153/A153M oppure ISO 1461/EN ISO 1461 (o loro varianti di formattazione equivalenti, es. "EN ISO 1461:2009"). Passo (3): se l'articolo è HDG ma NESSUNA delle due norme compare citata, segnalalo come non conformità documentale, manca il riferimento normativo atteso. Passo (4): se compare una norma di zincatura diversa da queste due, o palesemente non pertinente, segnalalo come possibile incoerenza da verificare. Passo (5): questo controllo verifica SOLO la presenza/coerenza della citazione normativa, non i valori numerici di spessore del rivestimento — non dedurre conformità dello spessore dalla sola presenza della citazione corretta.

  ## Confronto numerico dettagliato (fase futura, non ancora attiva)

  Un controllo più approfondito richiederebbe le tabelle spessore-minimo-per-categoria delle due norme (in `references/astm-a153.md` e `references/iso-1461.md`, oggi non presenti), popolate dai testi ufficiali. Finché questi file non esistono, non stimare né dedurre a memoria uno spessore minimo: limitati al controllo di coerenza della citazione descritto sopra.
  
