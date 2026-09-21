---
name: marcatura-mss-sp25
description: >-
  Verifica se la marcatura riportata sul pezzo/certificato (grado materiale, size, rating/class, produttore, heat number) rispetta il formato e i contenuti richiesti da MSS SP-25 per flange, raccordi e valvole. Usa SEMPRE questa skill quando l'utente chiede di verificare/controllare la marcatura di una flangia o di un raccordo, chiede cosa deve comparire sulla marcatura secondo MSS SP-25, o subito dopo `quality-steel`/`verifica-dimensionale` per controllare la marcatura dell'articolo prima di considerare la scheda definitiva.

    STATO ATTUALE: scheletro non ancora operativo — la tabella dei requisiti di marcatura per tipo di articolo è vuota in attesa dell'edizione ufficiale di MSS SP-25. Finché resta vuota, questa skill deve dichiararlo esplicitamente e non improvvisare i requisiti.
    ---

    # Marcatura — MSS SP-25 (Standard Marking System for Valves, Fittings, Flanges, and Unions)

    Riferimento tecnico sui requisiti di marcatura per flange e raccordi forgiati prodotti da LAME Srl. Usala per controllare che la marcatura dichiarata nel certificato (o fotografata/descritta dall'utente) contenga tutti gli elementi richiesti da MSS SP-25 per quel tipo di articolo, nel formato previsto.

    ## Quando attivarla

    - L'utente chiede di verificare/controllare la marcatura di un pezzo o di un certificato.
    - Dopo `quality-steel`/`verifica-dimensionale`, per controllare che la marcatura dichiarata sia coerente con grado, size, rating dell'articolo appena estratto.
    - Quando serve sapere quali elementi di marcatura sono obbligatori per un certo tipo di articolo.

    ## Cosa deve tabellare `references/mss-sp25.md` (DA POPOLARE)

    **Edizione da annotare in cima al file di riferimento una volta creato** (es. "MSS SP-25-2018" o edizione più recente disponibile).

    Per ciascun tipo di articolo (flangia, raccordo forgiato socket-weld/threaded, raccordo buttweld) MSS SP-25 specifica quali elementi sono obbligatori tra: marchio del produttore, grado/materiale (con eventuale simbolo abbreviato), size nominale, rating/class di pressione, e in quali casi il numero di colata (heat number) va marcato sul pezzo stesso oltre che sul certificato. Vanno raccolte anche le eventuali abbreviazioni normalizzate dei gradi materiale (es. come deve comparire "F316L" marcato sul pezzo secondo la norma) per poter confrontare la marcatura reale con quella attesa.

    ## Come applicarla

    1. Se `references/mss-sp25.md` non esiste o non ha ancora i requisiti popolati per il tipo di articolo in esame: dillo esplicitamente all'utente — "non ho ancora i requisiti di marcatura MSS SP-25 per questo tipo di articolo, serve popolare il file di riferimento con l'edizione ufficiale" — e NON dedurre i requisiti a memoria.
    2. Una volta popolato: verifica che ogni elemento obbligatorio per quel tipo di articolo sia presente nella marcatura dichiarata, e che il formato (es. abbreviazione del grado) sia quello previsto dalla norma.
    3. Segnala ogni elemento mancante o in formato non conforme, non fermarti al primo.
    4. Se il tipo di articolo non rientra tra quelli coperti dal file di riferimento, dillo esplicitamente invece di applicare requisiti di un tipo di articolo simile.
    
