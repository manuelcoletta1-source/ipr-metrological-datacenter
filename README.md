# IPR DataCenter Metrologico (HERMETICUM)

Infrastruttura europea per la **misura ex-ante** della legittimità tecnica delle azioni digitali
tramite **Identity Primary Record (IPR)**.

Questo repository descrive un **DataCenter metrologico**.  
**Non governa, non decide, non autorizza.**  
Misura ex-ante la coerenza tecnica di un’azione rispetto a un riferimento IPR.

In assenza di prova verificabile → **blocco** (fail-closed).

---

## Definizione (one-liner)

Un **IPR DataCenter Metrologico** è un’infrastruttura di control-plane che consente
l’esecuzione di azioni digitali, algoritmiche o robotiche **solo se precedute**
da un Identity Primary Record verificabile ex-ante, operando in regime fail-closed
e senza custodia di dati personali.

---

## Perché “metrologico”

Questo DataCenter non esercita autorità.

È **metrologico** perché:
- non valuta contenuti o finalità;
- non decide nel merito delle azioni;
- misura la coerenza tecnica rispetto a un riferimento immutabile (IPR);
- rende la verifica riproducibile e auditabile nel tempo.

> La legittimità non è concessa.  
> È **misurata**.

---

## Principio fondamentale

Un’azione **NON deve essere eseguita** se, prima dell’esecuzione,
non esistono condizioni tecnicamente verificabili di:
- attribuzione umana;
- decisione esplicita;
- tracciabilità opponibile;
- esposizione temporale auditabile.

In assenza di prova → **nessuna esecuzione**.

---

## Funzionamento ex-ante

1. Decisione esterna al DataCenter (umana o istituzionale)
2. Emissione di un IPR (hash-only)
3. Richiesta di esecuzione
4. Misura ex-ante (PASS / FAIL)
5. Esecuzione consentita o bloccata
6. Audit opponibile nel tempo

Il DataCenter **non introduce eccezioni** e **non applica fallback permissivi**.

---

## Cosa fa

- verifica IPR ex-ante;
- opera in modalità **fail-closed**;
- consente l’esecuzione solo in stato PASS;
- produce evidenze tecniche auditabili;
- blocca automaticamente in assenza di prova.

## Cosa NON fa

- non decide nel merito;
- non custodisce identità o dati personali;
- non riscrive eventi passati;
- non esercita discrezionalità;
- non sostituisce autorità umane o istituzionali.

---

## Integrazione nel sistema HERMETICUM

- **IPR** → riferimento
- **JOKER Gate** → misura ex-ante
- **Precheck API** → interfaccia tecnica PASS / FAIL
- **DataCenter Metrologico** → esecuzione vincolata

Il DataCenter è **esecutore condizionato**, non arbitro.

---

## Allineamento normativo UE

- **AI Act** → human oversight tecnico reale ex-ante
- **GDPR** → minimizzazione, hash-only, nessuna custodia dati
- **NIS2** → prevenzione del rischio a monte
- **eIDAS (principi)** → tracciabilità e opponibilità nel tempo

Questo repository **non introduce nuove leggi**
e **non sostituisce autorità esistenti**:
rende tecnicamente applicabili obblighi già presenti.

---

## Stato del progetto

- Architettura: definita
- Regime: fail-closed
- Audit: nativo
- Custodia dati: assente
- Ambito: B2G / B2B / infrastrutture critiche / AI ad alto impatto

---

## Formula canonica

IPR è il riferimento.  
JOKER è la misura.  
Il DataCenter è l’esecutore vincolato.  

**Non cambio chi decide.  
Cambio quando un’azione è ammessa.**
