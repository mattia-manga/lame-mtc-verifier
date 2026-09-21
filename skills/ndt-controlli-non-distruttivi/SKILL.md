---
name: ndt-controlli-non-distruttivi
description: >-
  Verifica se i controlli non distruttivi (NDT - visivo, liquidi penetranti PT, particelle magnetiche MT, ultrasuoni UT, radiografia RT) riportati in un certificato sono quelli richiesti dal grado materiale/servizio dichiarato e se l'esito riportato è conforme ai criteri di accettazione. Usa SEMPRE questa skill quando l'utente chiede di verificare/controllare i controlli non distruttivi, gli esiti PT/MT/UT/RT di un certificato, o quando serve sapere quali NDT sono richiesti per un certo grado/servizio.

    STATO ATTUALE: scheletro non ancora operativo — i criteri di accettazione per metodo NDT sono vuoti in attesa delle norme ufficiali di riferimento (tipicamente ASME BPVC Sez. V per l'esecuzione, ASTM E165/E709/E213/E1032 per metodo, criteri di accettazione da PO/spec cliente). Finché restano vuoti, questa skill deve dichiararlo esplicitamente e non improvvisare i criteri.
    ---

    # Controlli non distruttivi (NDT) — PT / MT / UT / RT

    Riferimento tecnico sui requisiti NDT per flange e raccordi forgiati prodotti/gestiti da LAME Srl. A differenza delle altre skill di questo plugin, il requisito "quale NDT è richiesto" dipende spesso dall'ordine/specifica cliente e non solo dal grado materiale — questa skill verifica coerenza interna al certificato (metodo eseguito + esito riportato), non presume da sola cosa il cliente avesse richiesto.

    ## Quando attivarla

    - L'utente chiede di verificare/controllare un controllo non distruttivo o il suo esito.
    - Serve sapere quali NDT sono tipicamente richiesti per un certo grado materiale/servizio (es. servizio sour, alta pressione).

    ## Cosa deve tabellare `references/ndt-metodi.md` (DA POPOLARE)

    **Edizione/norma da annotare in cima al file una volta creato** (tipicamente ASME BPVC Sez. V per l'esecuzione generale, più le norme ASTM specifiche per metodo: E165 per PT, E709 per MT, E213/E273 per UT, E94/E1032 per RT).

    Per ciascun metodo va raccolto: cosa deve riportare il certificato per considerare l'esame eseguito correttamente (procedura, livello di sensibilità/qualificazione operatore se richiesto), e i criteri di accettazione/rigetto tipici (es. dimensione massima ammessa di indicazioni per PT/MT, criteri di classificazione difetti per UT/RT). Se questi criteri sono spesso specificati da PO/spec cliente più che da una tabella fissa di norma, va annotato esplicitamente qui invece di presentarli come limiti universali.

    ## Come applicarla

    1. Se `references/ndt-metodi.md` non ha ancora i criteri popolati per il metodo in esame: dillo esplicitamente all'utente e NON stimare criteri di accettazione a memoria.
    2. Una volta popolato: verifica che il certificato riporti metodo, procedura ed esito in modo completo, e che l'esito dichiarato ("accettabile"/valori misurati) rientri nei criteri applicabili.
    3. Se il certificato dichiara un metodo NDT eseguito ma non ne riporta l'esito o i criteri di accettazione usati, segnalalo come dato mancante.
    4. Non presumere quale NDT fosse richiesto dall'ordine se il certificato non lo specifica: limita la verifica a "il metodo dichiarato è stato eseguito ed è conforme ai suoi stessi criteri", segnalando che la pertinenza rispetto all'ordine va confermata separatamente.
    
