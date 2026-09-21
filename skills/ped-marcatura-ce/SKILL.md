---
name: ped-marcatura-ce
description: >-
  Verifica se un articolo (flangia o raccordo) rientra nell'ambito della direttiva PED 2014/68/EU, quale categoria di rischio gli si applica secondo l'Allegato II, e se la marcatura CE dichiarata in certificato è coerente con quella categoria. Usa SEMPRE questa skill quando l'utente chiede se un pezzo è soggetto a PED, quale categoria PED si applica, se serve la marcatura CE, o quando un certificato/ordine cita PED, CE, categoria I/II/III/IV, Sound Engineering Practice (SEP), o un ente notificato.

    STATO ATTUALE: parzialmente utilizzabile — la logica generale di classificazione (DN × PS, gruppo fluido, esclusioni note) è già raccolta qui da fonti pubbliche della direttiva, ma le soglie esatte di categoria per OGNI tabella (6/7/8/9) e per articoli/eccezioni particolari non sono ancora complete: usarla per un primo orientamento, non come giudizio definitivo senza controllo sul testo ufficiale dell'Allegato II.
    ---

    # PED 2014/68/EU — applicabilità e categoria di rischio per piping

    A differenza degli standard ASME, la direttiva PED è un testo di legge dell'Unione Europea liberamente consultabile (non è uno standard a pagamento come B16.5/B16.9/B16.11). Questo file raccoglie la logica generale nota, ma alcune soglie di dettaglio vanno verificate sul testo ufficiale dell'Allegato II prima di un giudizio vincolante — annotalo sempre nella risposta.

    ## Quando attivarla

    - L'utente chiede se un articolo (flangia/raccordo) è soggetto a PED e/o richiede marcatura CE.
    - L'utente chiede quale categoria PED (I/II/III/IV o SEP - Sound Engineering Practice) si applica a un certo DN/PS/fluido.
    - Un certificato/ordine cita PED, CE, categoria, ente notificato, modulo di valutazione conformità (H, H1, G, ecc.).

    ## Logica di classificazione (nota, da confermare su Allegato II per soglie esatte non ancora raccolte qui)

    Per il piping (tubazioni e relativi accessori, incluse flange e raccordi), la classificazione dipende da:

    1. **Gruppo fluido**: Gruppo 1 = fluidi pericolosi (esplosivi, infiammabili, tossici, comburenti); Gruppo 2 = tutti gli altri fluidi (non pericolosi).
    2. **Stato fisico**: gas/vapori/liquidi con tensione di vapore alla temperatura massima ammissibile >0.5 bar sopra la pressione atmosferica → tabelle 6/7; liquidi con tensione di vapore ≤0.5 bar → tabelle 8/9.
    3. **Formula di rischio per piping**: PS × DN (pressione massima ammissibile in bar × diametro nominale in mm), diversa dalla formula PS × V usata per i recipienti.

    | Tabella Allegato II | Fluido | Stato |
    |---|---|---|
    | Tabella 6 | Gruppo 1 (pericoloso) | Gas/vapore o liquido con tensione vapore >0.5 bar |
    | Tabella 7 | Gruppo 2 (non pericoloso) | Gas/vapore o liquido con tensione vapore >0.5 bar |
    | Tabella 8 | Gruppo 1 (pericoloso) | Liquido con tensione vapore ≤0.5 bar |
    | Tabella 9 | Gruppo 2 (non pericoloso) | Liquido con tensione vapore ≤0.5 bar |

    **Soglie note per Tabella 6 (piping, gas/vapore gruppo 1 — pericoloso):**
    - DN ≤25: PED non applicabile, nessuna marcatura CE richiesta.
    - DN ≤100 e PS×DN ≤1000: Categoria I.
    - 25 <DN ≤350 e PS×DN ≤3500: Categoria II.
    - DN >350 (fino a PS=10 bar) o comunque PS×DN >3500 per PS <10 bar: Categoria III.
    - **Nota:** questi tre punti derivano da una fonte secondaria che riassume la Tabella 6; non ho ancora raccolto qui i punti di soglia per la Categoria IV né l'immagine completa del diagramma — da verificare sul testo ufficiale prima di escludere la Categoria IV per un caso reale.

    **Esclusioni note per Gruppo 2 (fluidi non pericolosi, tipicamente il caso più comune per raccorderia industriale generica):**
    - Piping per liquidi di Gruppo 2: escluso da PED (= SEP, "Sound Engineering Practice", nessuna marcatura CE) se DN ≤200 qualunque sia la pressione, oppure se DN >200 e PS ≤500 bar.
    - Piping per gas di Gruppo 2: escluso da PED (SEP) se DN ≤100, oppure se PS×DN ≤3500.
    - Queste esclusioni coprono la maggior parte della raccorderia industriale standard in servizio non pericoloso: se il fluido dichiarato è Gruppo 2 e il DN rientra in queste soglie, il pezzo è tipicamente SEP e non richiede marcatura CE PED (verifica comunque il valore PS×DN reale, non presumere).

    **Non ancora raccolte qui (da verificare sul testo ufficiale se il caso lo richiede):**
    - Soglie esatte Tabelle 7, 8, 9 per Categoria I/II/III/IV (solo le esclusioni SEP sono note con certezza sopra).
    - Regole speciali/eccezioni per assiemi, accessori di sicurezza, moduli di valutazione conformità (H, H1, G, B+D, ecc.) associati a ciascuna categoria.

    ## Come applicarla

    1. Identifica gruppo fluido (1 o 2), stato fisico (gas/vapore vs liquido a bassa tensione vapore), DN e PS massimo ammissibile dell'articolo.
    2. Calcola PS × DN e confrontalo con le soglie note sopra per la tabella pertinente.
    3. Se il caso rientra chiaramente in una soglia di esclusione (SEP) o in una categoria nota (I/II/III per Tabella 6), dallo come risposta con il grado di certezza indicato dalla fonte.
    4. Se il caso è vicino a una soglia non ancora raccolta con certezza (es. serve sapere se è Categoria III o IV, o si tratta di Tabella 7/8/9), dillo esplicitamente e consiglia di verificare sul testo ufficiale della direttiva 2014/68/EU, Allegato II, prima di un giudizio vincolante — non stimare.
    5. Se il certificato dichiara già una categoria/marcatura CE, verifica solo la coerenza con quanto calcolato, segnalando eventuali discrepanze come da confermare (non come errore certo) se la soglia esatta non è tra quelle raccolte sopra.
    
