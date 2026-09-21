---
name: verifica-dimensionale
description: >-
  Verifica se le dimensioni riportate in un certificato o DDT (diametro esterno, spessore, centro-fine, socket depth, numero/diametro fori bulloni) rispettano le tolleranze di norma per flange e raccordi forgiati secondo ASME B16.5 (flange), B16.9 (buttweld) e B16.11 (socket-welding/threaded). Usa SEMPRE questa skill quando l'utente chiede di verificare/controllare le dimensioni o tolleranze di una flangia o raccordo, o subito dopo `quality-steel` per controllare i dati dimensionali estratti. Scheletro non ancora operativo: le tabelle in references/ sono vuote in attesa delle edizioni ufficiali B16.5-2025/B16.9-2024/B16.11-2021.
  ---

  # Verifica dimensionale — flange e raccordi forgiati (B16.5 / B16.9 / B16.11)

  **STATO ATTUALE: scheletro non ancora operativo.** Le tabelle numeriche di riferimento in `references/` sono vuote in attesa delle edizioni ufficiali delle norme (B16.5-2025, B16.9-2024, B16.11-2021). Finché i file `references/*.md` restano vuoti, questa skill deve dichiarare esplicitamente all'utente di non poter eseguire il confronto numerico, non improvvisare valori.

  Riferimento tecnico sulle tolleranze dimensionali per gli articoli prodotti da LAME Srl. Usala per controllare che le dimensioni riportate in un certificato, DDT o scheda Heat già estratta da `quality-steel` rientrino nei valori previsti dalla norma di riferimento per quella size/class/tipo articolo. Non è una skill di estrazione: presuppone che i valori dimensionali siano già disponibili (dal PDF o da un documento già generato) e si limita al confronto/validazione.

  Le tabelle dimensionali per ciascuna norma sono in file separati sotto `references/`, non in questo file: leggi SOLO il/i file della norma effettivamente pertinente al tipo di articolo che stai controllando, non l'intera cartella. Questo file contiene la logica di smistamento e le istruzioni comuni.

  ## Quando attivarla

  - L'utente chiede di verificare, validare, controllare le dimensioni/tolleranze di una flangia o di un raccordo.
  - - Dopo una estrazione `quality-steel`, per controllare se le dimensioni riportate per l'articolo sono coerenti con size/class/tipo dichiarati, prima di considerare la scheda definitiva.
    - - Quando in un certificato compare una combinazione size/class/tipo articolo coperta sotto e serve sapere quali sono le dimensioni attese.
     
      - ## Come riconoscere il tipo di articolo e quale file leggere
     
      - | Tipo di articolo in certificato | Norma applicabile | File da leggere |
      - |---|---|---|
      - | Flangia (weld neck, slip-on, blind, socket weld, threaded, lap joint), class 150–2500, NPS 1/2–24 | ASME B16.5 | `references/b16-5-flange.md` |
      - | Raccordo buttweld (gomito 90°/45° long/short radius, tee, riduzione concentrica/eccentrica, cap), NPS 1/2–48 | ASME B16.9 | `references/b16-9-buttweld.md` |
      - | Raccordo socket-weld (class 3000/6000/9000) o threaded (class 2000/3000/6000) | ASME B16.11 | `references/b16-11-socketweld-threaded.md` |
     
      - Note generali di riconoscimento:
     
      - - Un certificato può riportare più articoli con tipo/norma diversi (es. flange + gomiti nello stesso DDT): leggi un file di riferimento diverso per ciascun gruppo di articoli con la stessa norma applicabile, non un'unica lettura cumulativa.
        - - Se il tipo di articolo non è determinabile con certezza dai dati disponibili (es. non è chiaro se un raccordo è socket-weld o threaded), dillo esplicitamente invece di scegliere il file più permissivo.
          - - Se il tipo di articolo dichiarato non rientra in nessuna delle tre norme sopra (es. flange EN/PN, raccordi filettati NPT non-forgiati, ecc.), dillo esplicitamente all'utente: non improvvisare tolleranze per un tipo di articolo non documentato in questi file.
           
            - ## Come applicarla nell'analisi di un certificato o scheda
           
            - 1. Identifica il tipo di articolo dichiarato e apri (Read) il solo file di riferimento corrispondente dalla tabella sopra.
              2. 2. **Se il file di riferimento non ha ancora le tabelle numeriche popolate (contiene solo la struttura/TODO):** dillo esplicitamente all'utente — "non ho ancora i valori di norma per [size/class/tipo], serve popolare `references/<file>.md` con l'edizione ufficiale" — e NON stimare o dedurre valori a memoria. Questo vale in particolare per tolleranze e quote critiche (bolt circle, socket depth, spessori minimi): un valore sbagliato qui invalida un certificato di qualità reale.
                 3. 3. Una volta che il file ha le tabelle popolate: per ogni quota dichiarata nel certificato (diametro esterno, spessore, center-to-end, socket depth, PCD, numero/diametro fori, ecc.), confronta con il valore nominale ± tolleranza indicati nel file per quella combinazione size/class.
                    4. 4. Elenca sempre TUTTE le quote fuori tolleranza trovate (non fermarti alla prima), indicando quota misurata, valore nominale di norma, tolleranza ammessa e di quanto è fuori range.
                       5. 5. Se una quota richiesta dalla norma per quella size/class non è riportata nel certificato, segnalala come dato mancante, non presumere conformità.
                          6. 6. Se le quote sono sistematicamente incompatibili con la combinazione size/class dichiarata (non uno scostamento isolato, ma un pattern che corrisponde a un'altra size o class), segnala il sospetto di size/class errata in certificato, non limitarti a elencare le quote fuori range una per una.
                            
                             7. Questi limiti devono riflettere l'edizione della norma effettivamente in vigore (o quella citata nel certificato/ordine, se più restrittiva o specifica): l'edizione usata per popolare ciascun file references/*.md va annotata in cima al file stesso, così è verificabile quale versione è stata trascritta.
                             8. 
