---
name: specifiche-cliente
description: >-
  Verifica se un certificato materiale (MTC) rispetta i requisiti aggiuntivi di una specifica cliente/progetto (project spec, Shell DEP, Saudi Aramco Engineering Standards, o altro capitolato tecnico) allegata o già nota. Usa SEMPRE questa skill quando l'utente allega/menziona una specifica cliente, un PO con requisiti tecnici aggiuntivi, o chiede di verificare un certificato "secondo il capitolato" o "secondo la spec del cliente [nome]".

    NATURA DIVERSA DALLE ALTRE SKILL DI QUESTO PLUGIN: non esiste una tabella di norma fissa da popolare una volta per tutte — ogni cliente/progetto ha la propria specifica, spesso più restrittiva delle norme base (B16.5/9/11, ASTM/ASME, MSS SP-25...) già coperte dalle altre skill. Questa skill lavora SEMPRE a partire da un documento di specifica fornito dall'utente (allegato o incollato), non da valori a memoria.
    ---

    # Verifica rispetto a specifiche cliente / progetto

    A differenza delle altre skill di questo plugin, qui non c'è nulla da "popolare" una volta per tutte: i requisiti cambiano per ogni cliente/progetto. Questa skill struttura COME confrontare un certificato con una specifica cliente, non COSA richiede una specifica cliente specifica (quello va sempre letto dal documento fornito).

    ## Quando attivarla

    - L'utente allega o incolla una specifica cliente/progetto (project spec, DEP, capitolato) e chiede di verificare un certificato rispetto a quella.
    - L'utente chiede quali requisiti aggiuntivi impone un certo cliente/progetto, avendo già fornito o indicato dove trovare la specifica.
    - Un ordine/PO fa riferimento a una specifica esterna che va controllata insieme al certificato.

    ## Come applicarla

    1. **Richiedi sempre la specifica se non è già fornita.** Non tentare di ricostruire a memoria cosa richiede una specifica cliente per nome (es. "Shell DEP 31.40.10.19" o "Saudi Aramco SAES-D-001") senza il documento: sono capitolati proprietari, spesso non pubblici, e un requisito sbagliato è peggio di nessuna verifica.
    2. Una volta ottenuta la specifica (PDF, testo incollato, o estratto rilevante), identifica i requisiti che si aggiungono o restringono rispetto alle norme base già coperte da questo plugin (es. durezza massima più bassa di quella norma per servizio sour, NDT aggiuntivi, marcatura specifica, documentazione supplementare richiesta, restrizioni di tracciabilità oltre EN 10204).
    3. Confronta il certificato punto per punto con questi requisiti aggiuntivi, segnalando esplicitamente quali sono più restrittivi della norma base (in quel caso la specifica prevale) e quali invece richiamano semplicemente la norma base già verificata dalle altre skill (evita di duplicare quel controllo, rimanda alla skill pertinente: `esperto-materiali-metallurgici`, `verifica-dimensionale`, `marcatura-mss-sp25`, `hdg-zincatura`, `ndt-controlli-non-distruttivi`, `tracciabilita-en10204`, `servizio-sour-nace`).
    4. Se la specifica cliente è ambigua, incompleta, o cita a sua volta un'altra norma/edizione non disponibile, dillo esplicitamente invece di presumere il requisito.
    5. Se ricorre spesso una stessa specifica cliente per LAME, valuta con l'utente se ha senso salvare un file di riferimento dedicato (es. `references/<nome-cliente>.md`) con i requisiti ricorrenti già estratti — ma solo su richiesta esplicita e a partire da un documento realmente fornito, non di iniziativa.

    ## Nota su copyright/riservatezza

    Molte specifiche cliente (Shell DEP, Saudi Aramco Engineering Standards, ecc.) sono documenti proprietari a distribuzione limitata. Se l'utente chiede di cercarle o recuperarle online invece di fornirle, segnala che potrebbero non essere liberamente disponibili e che è preferibile lavorare dalla copia in possesso di LAME/del cliente.
    
