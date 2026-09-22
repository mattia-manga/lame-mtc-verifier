---
name: servizio-sour-nace
description: >-
  Verifica se un materiale/certificato dichiarato per servizio sour (presenza di H2S) cita nel certificato la norma sour corretta (NACE MR0175 / ISO 15156) — controllo di coerenza tra caratteristica dichiarata e norma citata, non ancora confronto dei limiti di durezza. Usa SEMPRE questa skill quando l'utente chiede di verificare la conformità sour di un materiale, o quando un certificato/ordine menziona servizio sour, NACE, H2S, MR0175 o ISO 15156.
  ---

  # Servizio sour — coerenza citazione NACE MR0175 / ISO 15156

  ## Quando attivarla

  L'ordine/certificato dichiara servizio sour, H2S, o menziona genericamente "NACE" senza citare la norma specifica. Oppure l'utente chiede di verificare la conformità sour di un materiale.

  ## Norma attesa

  | Caratteristica dichiarata | Norma attesa citata |
  |---|---|
  | Servizio sour / H2S dichiarato | NACE MR0175 e/o ISO 15156 (una delle due, o entrambe) |

  ## Come applicarla (fase attuale — verifica di coerenza citazione)

  Passo (1): verifica se l'ordine/certificato dichiara servizio sour o H2S. Passo (2): se dichiarato, controlla che il certificato citi esplicitamente NACE MR0175 e/o ISO 15156. Passo (3): se il servizio sour è dichiarato ma nessuna delle due norme compare citata, segnalalo come dato mancante, un servizio sour senza riferimento normativo esplicito è un'anomalia documentale da segnalare. Passo (4): se compare una citazione generica ("materiale sour") senza numero di norma, segnalalo come citazione incompleta. Passo (5): questo controllo verifica SOLO la presenza/coerenza della citazione normativa, non il valore di durezza dichiarato né la sua conformità al limite sour specifico del grado.

  ## Verifica dettagliata dei limiti di durezza (fase futura, non ancora attiva)

  Un controllo più approfondito (limite di durezza massimo per grado in servizio sour, spesso più stringente della norma base) richiederebbe la tabella di dettaglio in `references/nace-mr0175.md`, oggi non presente. Finché questo file non esiste, non stimare un limite di durezza sour a memoria: limitati al controllo di coerenza della citazione descritto sopra.
  
