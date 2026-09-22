---
name: verifica-dimensionale
description: Verifica se un articolo (flangia o raccordo) cita nel certificato la norma dimensionale corretta in base al tipo (ASME B16.5 per flange, B16.9 per buttweld, B16.11 per socket-weld/threaded) — controllo di coerenza tra tipo articolo dichiarato e norma citata, non ancora confronto numerico delle tolleranze. Usa SEMPRE questa skill quando l'utente chiede di verificare la norma dimensionale applicabile a una flangia o un raccordo, o subito dopo `quality-steel` per un controllo di coerenza sul tipo di articolo estratto.
---

# Verifica dimensionale — coerenza citazione norma per tipo articolo (ASME B16.5 / B16.9 / B16.11)

## Quando attivarla

L'utente chiede quale norma dimensionale si applica a una flangia o un raccordo, o se il certificato la cita correttamente. Oppure, dopo `quality-steel`, per controllare che il tipo di articolo estratto sia coerente con la norma citata nel certificato.

## Norma attesa in funzione del tipo di articolo

| Tipo di articolo | Norma attesa citata |
|---|---|
| Flangia (weld neck, slip-on, blind, socket weld, threaded, lap joint) | ASME B16.5 (o EN 1092-1 se mercato EN/PN) |
| Raccordo buttweld (gomito, tee, riduzione, cap, ritorno) | ASME B16.9 |
| Raccordo socket-weld o threaded (non buttweld) | ASME B16.11 |

## Come applicarla (fase attuale — verifica di coerenza citazione)

Passo (1): identifica il tipo di articolo dichiarato nel certificato (flangia, buttweld, socket-weld/threaded). Passo (2): verifica che il certificato citi esplicitamente la norma attesa per quel tipo (tabella sopra). Passo (3): se non è citata alcuna norma dimensionale, segnalalo come dato mancante. Passo (4): se è citata una norma diversa da quella attesa per quel tipo di articolo (es. B16.9 su una flangia), segnalalo come possibile incoerenza o errore di trascrizione. Passo (5): se un certificato riporta più articoli di tipo diverso, verifica la coerenza norma/tipo per ciascun articolo separatamente. Passo (6): questo controllo verifica SOLO la presenza/coerenza della citazione normativa, non i valori dimensionali effettivi (diametri, spessori, tolleranze) riportati nel certificato.

## Confronto numerico dettagliato (fase futura, non ancora attiva)

Un controllo più approfondito (dimensioni e tolleranze attese per ogni combinazione NPS/Class/tipo) richiederebbe le tabelle in `references/b16-5-flange.md`, `references/b16-9-buttweld.md`, `references/b16-11-socketweld-threaded.md`, oggi vuote in attesa delle edizioni ufficiali (B16.5-2025, B16.9-2024, B16.11-2021). Finché questi file restano vuoti, non stimare valori dimensionali a memoria: limitati al controllo di coerenza della citazione descritto sopra.
