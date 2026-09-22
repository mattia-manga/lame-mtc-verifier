---
name: marcatura-mss-sp25
description: >-
  Verifica se un articolo dichiarato threaded/NPT o comunque soggetto a marcatura secondo MSS SP-25 cita nel certificato la norma di marcatura corretta — controllo di coerenza tra caratteristica dichiarata e norma citata, non ancora confronto dettagliato del contenuto della marcatura. Usa SEMPRE questa skill quando l'utente chiede di verificare la marcatura di flange/raccordi/valvole, o quando un certificato riporta un articolo NPT/threaded/forgiato che dovrebbe citare MSS SP-25.
  ---

  # Marcatura — coerenza citazione MSS SP-25 (e norma filettatura per articoli threaded/NPT)

  ## Quando attivarla

  L'utente chiede di verificare la marcatura di una flangia, di un raccordo o di una valvola. Oppure un certificato riporta un articolo forgiato (flangia, raccordo, valvola) per cui ci si attende una marcatura secondo MSS SP-25. Oppure un certificato riporta un articolo threaded/NPT, per cui ci si attende anche il riferimento alla norma di filettatura (tipicamente ASME B1.20.1).

  ## Norma attesa in funzione della caratteristica

  | Caratteristica dichiarata | Norma attesa citata |
  |---|---|
  | Flangia, raccordo forgiato o valvola (marcatura generale) | MSS SP-25 |
  | Raccordo/articolo threaded o NPT (filettatura) | ASME B1.20.1 (o norma di filettatura equivalente esplicitamente citata) |

  ## Come applicarla (fase attuale — verifica di coerenza citazione)

  Passo (1): identifica se l'articolo è un tipo per cui MSS SP-25 è pertinente (flangia, raccordo forgiato, valvola) e/o se è dichiarato threaded/NPT. Passo (2): controlla che il certificato citi esplicitamente MSS SP-25 per la marcatura generale, e ASME B1.20.1 (o equivalente) se l'articolo è threaded/NPT. Passo (3): se la norma attesa non compare citata, segnalalo come dato mancante nel certificato. Passo (4): se compare una norma diversa o non pertinente al posto di quella attesa, segnalalo come possibile incoerenza. Passo (5): questo controllo verifica SOLO la presenza/coerenza della citazione normativa, non il contenuto effettivo della marcatura sul pezzo (elementi obbligatori, formato) né la conformità dimensionale della filettatura.

  ## Verifica dettagliata del contenuto marcatura/filettatura (fase futura, non ancora attiva)

  Un controllo più approfondito (quali elementi devono comparire nella marcatura, formato esatto, tolleranze di filettatura NPT) richiederebbe le tabelle di dettaglio in `references/mss-sp25.md`, oggi non presenti, popolate dai testi ufficiali. Finché questo file non esiste, non improvvisare requisiti di dettaglio: limitati al controllo di coerenza della citazione descritto sopra.
  
