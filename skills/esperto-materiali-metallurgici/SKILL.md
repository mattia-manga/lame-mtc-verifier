---
name: esperto-materiali-metallurgici
description: Verifica se i valori di composizione chimica e proprietà meccaniche riportati in un certificato materiale (o già estratti in una scheda Output/Scheda_Heat_*.pdf da quality-steel) rispettano i limiti di norma per i gradi SA-105/A105N, SA-182 F5, SA-182 F11 Cl.1, SA-182 F11 Cl.2, SA-350 LF2 Cl.1, SA-182 F316, SA-182 F316L, SA-182 F304, SA-182 F304L, A694 F52, SA-182 F53, A106 Gr.B, A312 TP304/TP304L, A312 TP316/TP316L. Usa SEMPRE questa skill quando l'utente chiede di verificare/controllare/validare la conformità di un materiale o di una colata alla norma, quando chiede quali sono i limiti chimici/meccanici ammessi per uno di questi gradi, o subito dopo che `quality-steel` ha estratto i dati di un Heat con uno di questi gradi, per segnalare eventuali valori fuori specifica prima di considerare la scheda definitiva.
---

# Esperto materiali metallurgici — restrizioni chimiche e meccaniche

Riferimento tecnico sui gradi materiale usati da LAME Srl. Usala per controllare che i valori di analisi chimica di colata e di prove meccaniche riportati in un certificato (o già estratti da `quality-steel` in una Scheda Heat) rientrino nei limiti previsti dalla norma di riferimento. Non è una skill di estrazione: presuppone che i valori numerici siano già disponibili (dal PDF o da una scheda già generata) e si limita al confronto/validazione.

Le tabelle dei limiti per ciascun grado sono in file separati sotto `references/`, non in questo file: leggi SOLO il/i file del grado effettivamente dichiarato nel certificato che stai controllando, non l'intera cartella. Questo file contiene la logica di smistamento e le istruzioni comuni a tutti i gradi.

## Quando attivarla

- L'utente chiede di verificare, validare, controllare la conformità di un materiale/colata a una norma.
- - Dopo una estrazione `quality-steel`, per controllare se i valori chimici/meccanici della colata sono entro i limiti del grado dichiarato in certificato, prima di considerare la scheda definitiva.
  - - Quando in un certificato compare un grado materiale tra quelli coperti sotto e serve sapere quali sono i limiti applicabili.
   
    - ## Come riconoscere il grado e quale file leggere
   
    - I certificati usano designazioni non uniformi: normalizza la designazione, poi apri SOLO il file di riferimento corrispondente.
   
    - | Designazioni in certificato | Grado normalizzato | File da leggere |
    - |---|---|---|
    - | "A105", "SA-105", "A105N", "ASTM A 105" | SA-105 / SA-105N | `references/a105-a105n.md` |
    - | "F11", "Gr. F11", "1.25Cr-0.5Mo" (Cl.1 o Cl.2) | SA-182 F11 Cl.1 / Cl.2 | `references/f11.md` |
    - | "LF2 Cl.1", "SA-350 LF2" | SA-350 LF2 Cl.1 | `references/lf2-cl1.md` |
    - | "F316", "F316L", "F316/F316L" | SA-182 F316 / F316L | `references/f316-f316l.md` |
    - | "F304", "F304L", "F304/F304L" | SA-182 F304 / F304L | `references/f304-f304l.md` |
    - | "F53", "UNS S32750", "2507", "Super Duplex" | SA-182 F53 | `references/f53.md` |
    - | "F5", "5Cr-0.5Mo" | SA-182 F5 | `references/f5.md` |
    - | "A694 F52", "ASME SA-694 Gr.F52" | A694 F52 | `references/a694-f52.md` |
    - | "A106 Gr.B", "ASTM A106-B", "ASME SA-106 Gr.B" | A106 Gr.B | `references/a106-grb.md` |
    - | "TP304/TP304L", "A312 TP304/304L", "TP316/TP316L", "A312 TP316/316L" | A312 TP304/TP304L / TP316/TP316L | `references/a312-tp304-tp316.md` (chimica: vedi anche `f304-f304l.md` o `f316-f316l.md`, indicato nel file A312 stesso) |
   
    - Note generali di riconoscimento, valide su tutti i gradi:
   
    - - La lettera "N" in A105N NON cambia la chimica, indica solo trattamento termico di normalizzazione — non dedurla dai soli valori chimici, verifica che compaia nel certificato.
      - - Per F11, la Classe (Cl.1/Cl.2) si distingue da valori meccanici o trattamento termico dichiarato; se ambigua, segnalalo invece di indovinare.
        - - Per le doppie certificazioni (F316/F316L, F304/F304L, TP304/TP304L, TP316/TP316L): il dettaglio di quando è valida la doppia designazione vs. la sola designazione "semplice" è nel file di riferimento del grado specifico — leggilo prima di giudicare la doppia certificazione.
          - - Per i gradi a tubo (A312, A106): la chimica può coincidere con un grado forgiato equivalente, ma la meccanica NON coincide mai — usa sempre il file del grado a tubo per i minimi meccanici.
            - - Un certificato con più Heat di gradi diversi richiede di leggere un file di riferimento diverso per ciascun gruppo di Heat con lo stesso grado — non un'unica lettura cumulativa.
             
              - Se il grado dichiarato non compare in questa tabella, dillo esplicitamente all'utente: non improvvisare limiti per un grado non documentato in questi file.
             
              - ## Come applicarla nell'analisi di un certificato o scheda Heat
             
              - 1. Identifica il grado dichiarato e apri (Read) il solo file di riferimento corrispondente dalla tabella sopra.
                2. 2. Per ogni elemento chimico riportato nell'analisi di colata, confronta con il range indicato nel file. Un elemento presente in colata ma assente dalla tabella (es. elemento residuo) non è di per sé una non conformità, salvo che rientri in un vincolo combinato esplicitamente indicato nel file (es. Cu+Ni+Cr+Mo+V, Cr+Mo).
                   3. 3. Per i gradi A105/A105N e A106 Gr.B, il file di riferimento contiene una formula di compensazione C↔Mn: NON usare mai il tetto fisso di Mn (1.05%/1.06%) per giudicare una non conformità su questi due gradi. Calcola sempre prima il Mn massimo consentito con la formula riportata nel file, usando il Carbonio effettivamente misurato in quella colata, e confronta il Mn misurato con quel valore calcolato.
                      4. 4. Per ogni proprietà meccanica riportata (Rm, Rp0.2, A%, Z%, durezza, energia d'urto), confronta con i minimi/massimi/range del file, convertendo le unità se necessario (ksi ↔ MPa: 1 ksi ≈ 6.895 MPa; ft·lbf ↔ J: 1 ft·lbf ≈ 1.356 J).
                         5. 5. Elenca sempre TUTTI i valori fuori limite trovati (non fermarti al primo), indicando valore misurato, limite di norma e di quanto è fuori range. Per un Mn A105/A105N o A106 Gr.B fuori range, indica sia il valore misurato sia il Mn massimo consentito calcolato con la compensazione C↔Mn (non il tetto fisso).
                            6. 6. Se un dato richiesto dalla norma (es. prova d'urto per LF2 Cl.1, PREN per F53, giustificazione formula per elongation ridotta in A106) manca nel certificato, segnalalo come dato mancante, non presumere conformità.
                               7. 7. Se la chimica riportata è incompatibile con il grado dichiarato in modo sistemico (non un singolo elemento leggermente fuori range, ma un pattern che assomiglia a un altro grado — vedi l'avviso specifico in `f304-f304l.md`), segnala il sospetto di grado errato o certificato/colata abbinati per errore, non limitarti a elencare gli elementi fuori range uno per uno.
                                  8. 8. Se la classe/il grado non è determinabile con certezza dai dati disponibili, dillo esplicitamente invece di scegliere il file più permissivo.
                                    
                                     9. Questi limiti riflettono le edizioni più diffuse di ASTM/ASME A105, A106, A182, A312, A350, A694 note al momento della stesura; se un certificato cita un'edizione specifica della norma o un requisito di capitolato/PO più restrittivo, quel documento prevale sui valori qui riportati.
                                     10. 
