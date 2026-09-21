---
name: hdg-zincatura
description: >-
  Verifica se lo spessore/aspetto del rivestimento di zincatura a caldo (HDG - hot-dip galvanizing) riportato in certificato rispetta i minimi richiesti da ASTM A153 (per pezzi forgiati/hardware) o ISO 1461/EN ISO 1461 (mercato europeo) in funzione dello spessore/categoria del pezzo. Usa SEMPRE questa skill quando l'utente chiede di verificare/controllare la zincatura, lo spessore di rivestimento HDG, o quando un certificato/DDT riporta un articolo zincato ("HDG", "galvanized", "zincato") e serve controllarne la conformità.

    STATO ATTUALE: scheletro non ancora operativo — la tabella degli spessori minimi per categoria/spessore pezzo è vuota in attesa dell'edizione ufficiale della norma applicabile. Finché resta vuota, questa skill deve dichiararlo esplicitamente e non improvvisare i minimi.
    ---

    # Zincatura a caldo (HDG) — ASTM A153 / ISO 1461

    Riferimento tecnico sui requisiti di rivestimento per articoli zincati a caldo prodotti/gestiti da LAME Srl. Usala SOLO per articoli dichiarati HDG/galvanized/zincati — non è pertinente per articoli non rivestiti.

    ## Quando attivarla

    - L'utente chiede di verificare/controllare la zincatura o lo spessore di rivestimento di un articolo.
    - Un certificato/DDT riporta un articolo HDG e serve controllarne lo spessore minimo di rivestimento.

    ## Quale norma applicare

    | Mercato/riferimento in certificato | Norma | File da leggere |
    |---|---|---|
    | ASTM, mercato Nord America | ASTM A153/A153M | `references/astm-a153.md` |
    | EN, mercato europeo | ISO 1461 / EN ISO 1461 | `references/iso-1461.md` |

    Se il certificato non specifica quale norma di zincatura è stata applicata, chiedilo o segnalalo come dato mancante prima di scegliere un file a caso.

    ## Cosa devono tabellare i file di riferimento (DA POPOLARE)

    **Edizione da annotare in cima a ciascun file una volta creato.**

    Entrambe le norme fissano lo spessore minimo di rivestimento (in µm o g/m²) in funzione di categoria dell'articolo (es. hardware/fasteners vs pezzi strutturali/forgiati) e/o dello spessore del materiale base — più il materiale è sottile, minore è lo spessore minimo richiesto. Vanno raccolte le fasce di spessore materiale base → spessore minimo rivestimento per ciascuna norma, oltre agli eventuali requisiti di aspetto (superficie continua, priva di bolle/scaglie, ecc.).

    ## Come applicarla

    1. Se il file di riferimento pertinente non ha ancora le fasce popolate: dillo esplicitamente all'utente e NON stimare uno spessore minimo a memoria.
    2. Una volta popolato: individua la fascia di spessore del materiale base dell'articolo, recupera lo spessore minimo di rivestimento richiesto, e confrontalo con quello dichiarato in certificato.
    3. Segnala se lo spessore dichiarato è sotto il minimo, e se mancano dati di aspetto/continuità richiesti dalla norma.
    
