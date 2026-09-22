---
name: tracciabilita-en10204
description: "Verifica se il tipo di certificato emesso (2.1, 2.2, 3.1, 3.2) rispetta i requisiti di EN 10204, in particolare se un 3.1 dichiarato ha davvero i requisiti di indipendenza del soggetto che rilascia il certificato, e se un 3.2 (terza parte indipendente) e' supportato da controfirma/validazione di un ente terzo effettivamente indipendente sia dal produttore che dall'acquirente. Usa SEMPRE questa skill quando l'utente chiede di verificare/controllare il tipo di certificato EN 10204, la sua validita' formale, o la differenza tra 3.1 e 3.2 per un certificato specifico. STATO ATTUALE: scheletro parzialmente utilizzabile, la logica 2.1/2.2/3.1/3.2 di EN 10204 e' concettualmente stabile e nota, ma i dettagli di formulazione esatta vanno confermati sull'edizione ufficiale (EN 10204:2004) prima di un giudizio formale su un certificato reale."
---

# Tracciabilità e tipo di certificato — EN 10204

Riferimento tecnico sui tipi di certificato secondo EN 10204, per verificare che il tipo dichiarato in un MTC corrisponda ai requisiti richiesti dall'ordine/dalla norma.

## Quando attivarla

L'utente chiede di verificare il tipo di certificato (2.1/2.2/3.1/3.2) di un MTC. Oppure serve capire se un 3.1 dichiarato è valido formalmente, o se serve un 3.2.

## Logica generale (da EN 10204, da confermare sull'edizione ufficiale prima di un giudizio vincolante)

| Tipo | Chi dichiara la conformità | Chi esegue le prove | Indipendenza richiesta |
|---|---|---|---|
| 2.1 | Produttore | Produttore | Nessuna verifica indipendente |
| 2.2 | Produttore | Produttore | Nessuna, ma con report di prova (non solo dichiarazione) |
| 3.1 | Produttore | Produttore | Il rappresentante che convalida il certificato deve essere indipendente dal reparto produzione, ma appartiene comunque all'organizzazione del produttore |
| 3.2 | Produttore + terza parte indipendente | Produttore e/o terza parte | Convalidato da un rappresentante indipendente sia dal produttore SIA dall'acquirente (es. ente di certificazione, ispettore designato dal cliente) |

**Questa tabella è una base concettuale, non ancora verificata parola per parola sull'edizione ufficiale EN 10204:2004** — prima di usarla per giudicare formalmente un certificato reale, conferma la formulazione esatta sulla norma.

## Come applicarla

Passo (1): identifica il tipo di certificato dichiarato (2.1/2.2/3.1/3.2) e chi lo ha firmato/controfirmato. Passo (2): per un 3.1, verifica che il firmatario sia identificato come indipendente dal reparto di produzione (non necessariamente un ente esterno). Passo (3): per un 3.2, verifica che compaia una firma/validazione di un soggetto realmente esterno sia al produttore che al cliente finale (non basta una seconda firma interna). Passo (4): se il tipo di certificato richiesto dall'ordine/PO non è noto, non presumere che il tipo emesso sia sufficiente, segnala che va confrontato con il requisito contrattuale. Passo (5): se la formulazione esatta di un requisito è dubbia rispetto a questa base concettuale, dillo esplicitamente e suggerisci di confermare sul testo ufficiale della norma prima di un giudizio vincolante.
