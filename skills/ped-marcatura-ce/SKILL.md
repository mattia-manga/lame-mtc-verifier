---
name: ped-marcatura-ce
description: >-
  Verifica se un articolo con marcatura CE dichiarata cita nel certificato la direttiva corretta (PED 2014/68/EU) — controllo di coerenza tra marcatura dichiarata e norma citata. Include anche la logica di classificazione per capire se PED si applica o meno (vedi file per i dettagli). Usa SEMPRE questa skill quando l'utente chiede se un pezzo è soggetto a PED/marcatura CE, o quando un certificato cita CE, PED, categoria I/II/III/IV, SEP.
  ---

  # PED 2014/68/EU / marcatura CE — coerenza citazione

  ## Quando attivarla

  Un certificato riporta una marcatura CE. Oppure l'utente chiede se un articolo è soggetto a PED o richiede marcatura CE.

  ## Norma attesa

  | Caratteristica dichiarata | Norma attesa citata |
  |---|---|
  | Marcatura CE presente sul certificato | Direttiva 2014/68/EU (PED) |

  ## Come applicarla (fase attuale — verifica di coerenza citazione)

  Passo (1): verifica se il certificato riporta una marcatura CE. Passo (2): se presente, controlla che citi esplicitamente la direttiva 2014/68/EU (PED) come riferimento, non una direttiva generica o non pertinente (es. non confondere con altre direttive CE che non sono PED). Passo (3): se la marcatura CE è dichiarata ma non è citata la direttiva PED 2014/68/EU, segnalalo come citazione incompleta/da verificare. Passo (4): se l'articolo NON ha marcatura CE, verifica solo se il certificato dichiara esplicitamente lo status "SEP" (Sound Engineering Practice), un articolo piping industriale comune spesso non richiede PED e questo è normale, non un'anomalia. Passo (5): questo controllo verifica SOLO la presenza/coerenza della citazione normativa, non la correttezza della categoria di rischio (I/II/III/IV) assegnata.

  ## Classificazione della categoria di rischio (logica nota, soglie parziali)

  Per un primo orientamento su quale categoria PED si applichi (basato su DN, PS, gruppo fluido), la logica generale e alcune soglie note sono raccolte più sotto in questo stesso file — utile se l'utente chiede "che categoria PED ha questo pezzo", ma va sempre trattata come orientamento, non come giudizio vincolante senza verifica sul testo ufficiale dell'Allegato II.

  Per il piping, la classificazione dipende da: gruppo fluido (1 = pericoloso, 2 = non pericoloso), stato fisico (gas/vapore vs liquido a bassa tensione di vapore), e dalla formula di rischio PS × DN.

  Esclusioni note per Gruppo 2 (fluidi non pericolosi, il caso più comune per raccorderia industriale generica): piping per liquidi di Gruppo 2 escluso da PED (SEP) se DN ≤200 qualunque sia la pressione, oppure se DN >200 e PS ≤500 bar. Piping per gas di Gruppo 2 escluso da PED (SEP) se DN ≤100, oppure se PS×DN ≤3500.

  Se il caso non rientra chiaramente in queste esclusioni note, dillo esplicitamente e consiglia di verificare sul testo ufficiale della direttiva prima di un giudizio vincolante — non stimare le soglie delle categorie I/II/III/IV che non sono ancora raccolte qui in dettaglio.
  
