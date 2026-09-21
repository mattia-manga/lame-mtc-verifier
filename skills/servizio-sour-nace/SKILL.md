---
name: servizio-sour-nace
description: >-
  Verifica se un materiale/certificato dichiarato per servizio sour (presenza di H2S) rispetta i requisiti aggiuntivi di NACE MR0175 / ISO 15156 — tipicamente limiti di durezza più stringenti, eventuali restrizioni di trattamento termico o composizione rispetto alla norma materiale base. Usa SEMPRE questa skill quando l'utente chiede di verificare/controllare la conformità sour di un materiale, quando un certificato/ordine menziona "sour service", "NACE", "H2S", "MR0175" o "ISO 15156".

    STATO ATTUALE: scheletro non ancora operativo — i limiti di durezza/requisiti aggiuntivi per grado sono vuoti in attesa dell'edizione ufficiale di ISO 15156 (parti 1-3) / NACE MR0175. Finché restano vuoti, questa skill deve dichiararlo esplicitamente e non improvvisare i limiti.
    ---

    # Servizio sour — NACE MR0175 / ISO 15156

    Riferimento tecnico sui requisiti aggiuntivi per materiali destinati a servizio sour (ambienti contenenti H2S) prodotti/gestiti da LAME Srl. Si applica SOLO quando l'ordine/certificato dichiara esplicitamente servizio sour — non è un requisito di default per gli altri gradi già coperti da `esperto-materiali-metallurgici`.

    ## Quando attivarla

    - L'ordine/certificato dichiara servizio sour, NACE, H2S, MR0175 o ISO 15156.
    - L'utente chiede se un grado/durezza è conforme per servizio sour.

    ## Cosa deve tabellare `references/nace-mr0175.md` (DA POPOLARE)

    **Edizione da annotare in cima al file una volta creato** (ISO 15156 è divisa in tre parti: Part 1 principi generali, Part 2 acciai al carbonio/basso legati, Part 3 leghe resistenti alla corrosione — verificare quale parte si applica al grado in esame).

    Per ciascun grado materiale già coperto da `esperto-materiali-metallurgici`, vanno raccolti gli eventuali limiti aggiuntivi per servizio sour: durezza massima (spesso più bassa del limite della norma base — es. molti PO richiedono ≤22 HRC per gradi HSLA, ≤237 HB per carbon steel, limiti specifici per duplex/super duplex), eventuali restrizioni sul trattamento termico, e limiti di composizione aggiuntivi se presenti.

    ## Come applicarla

    1. Se `references/nace-mr0175.md` non ha ancora i limiti popolati per il grado in esame: dillo esplicitamente all'utente e NON stimare un limite di durezza a memoria — la differenza tra un limite sour e quello della norma base può essere ampia e non è un dettaglio da approssimare.
    2. Una volta popolato: verifica che la durezza (e altri requisiti aggiuntivi) dichiarati in certificato rientrino nel limite sour per quel grado, non solo nel limite della norma materiale base.
    3. Se il certificato dichiara servizio sour ma non riporta un valore di durezza (o lo riporta ma non è chiaro se sia il criterio sour o quello base), segnalalo come dato mancante/ambiguo.
    4. Verifica sempre anche il PO/spec cliente: alcuni requisiti sour sono specifici del progetto e più stringenti della sola norma base ISO 15156.
    
