# ASTM A106 Gr.B — tubo senza saldatura in acciaio al carbonio per servizio alta temperatura

Chimica (%): C ≤0.30 · Mn 0.29–1.06 · P ≤0.035 · S ≤0.035 · Si ≥0.10 (nessun massimo fissato in norma) · Cr ≤0.40 · Cu ≤0.40 · Mo ≤0.15 · Ni ≤0.40 · V ≤0.08 · **Cr+Cu+Mo+Ni+V ≤1.00**

**Compensazione C↔Mn (nota Tabella 1 di ASTM A106, stessa logica di A105/A105M):** il massimo di Mn per il Grado B (1.06%) non è un tetto fisso. Per ogni riduzione di 0.01% del Carbonio misurato sotto il massimo di norma (0.30% per il Grado B), è ammesso un aumento di 0.06% sul massimo di Mn, fino a un tetto assoluto di 1.35%. Calcola il Mn massimo realmente consentito con:

`Mn_max_consentito = min(1.35, 1.06 + 6 × (0.30 − C_misurato))`

prima di segnalare un Mn come fuori specifica — non usare il semplice 1.06% fisso come soglia. Esempio: C=0.17% → Mn_max_consentito = min(1.35, 1.06+6×0.13) = 1.35%, quindi un Mn misurato fino a 1.35% è comunque conforme.

(La stessa tabella ASTM A106 riporta anche i tetti per i Gradi A e C, con basi C/Mn diverse: Grado A C≤0.25/Mn 0.27–0.93, Grado C C≤0.35/Mn 0.29–1.06 — applica la stessa formula con il rispettivo massimo di C se in futuro serve verificare quei gradi, non solo il Grado B.)

Meccanica: Rm ≥415 MPa (60 ksi) · Rp0.2 ≥240 MPa (35 ksi) · A: valore base 30% su provino standard 2in/50mm, ma la norma prevede un adeguamento per pareti sottili tramite formula (A106 §7: e≈625000·A^0.2/U^0.9 in unità metriche, dove A è l'area della sezione del provino e U il carico di rottura) — se il certificato riporta un'elongation inferiore al 30% base, verifica che sia giustificata dallo spessore/geometria del provino secondo la formula prima di considerarla non conforme, non accettarla per default senza controllo.

Nota: A106 Gr.B non impone un limite di durezza nella norma base; verifica sempre PO/capitolato per requisiti aggiuntivi (es. servizio sour, limite di Carbonio Equivalente).

Designazioni equivalenti in certificato: "A106 Gr.B", "ASTM A106-B", "ASME SA-106 Gr.B", "A106 Grade B".
