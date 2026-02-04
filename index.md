# IPR-Datacenter — Index

Questo repository definisce il modello **IPR-Datacenter**:
un’infrastruttura di calcolo che esegue azioni **solo se precedute**
da un Identity Primary Record (IPR) valido e verificabile ex-ante.

Il futuro non accade.
Si scrive prima.

---

## Cosa NON è

- Non è un nuovo tipo di datacenter fisico
- Non è una nuova autorità
- Non è un sistema di sorveglianza
- Non è un meccanismo di valutazione del merito

---

## Cosa È

- Un vincolo tecnico ex-ante
- Un modello fail-closed
- Un’infrastruttura stateless rispetto all’identità
- Un meccanismo di prevenzione del rischio
- Un abilitatore di audit opponibile nel tempo

---

## Principio fondamentale

Nessuna azione digitale deve essere eseguita
se prima dell’esecuzione
non esiste una prova verificabile di:
- attribuzione
- decisione
- responsabilità
- esposizione temporale

In assenza di prova → nessuna esecuzione.

---

## Architettura logica

1. Origine  
   La decisione nasce fuori dal datacenter.

2. Vincolo  
   L’IPR rende l’azione eseguibile nel tempo.

3. Calcolo  
   Il datacenter esegue solo se il vincolo è soddisfatto.

Il calcolo non governa.
Il tempo governa.

---

## Contenuto del repository

- `README.md`  
  Introduzione e principi

- `specs/`  
  Specifica tecnica IPR-Datacenter

- `schemas/`  
  Schemi JSON (IPR Manifest, Evidence Pack)

- `openapi/`  
  API del Decision Gate (verifica ex-ante)

- `reason-codes/`  
  Codici di blocco verificabili

- `verify/`  
  Verifica pubblica e audit

---

## Stato

- Modello: definito
- Architettura: coerente
- Integrazione: incrementale su datacenter esistenti
- Regime: UE-first, hash-only, fail-closed

---

## Chiusura

IPR-Datacenter non introduce nuove promesse.
Introduce una condizione tecnica:

**se non esiste una decisione prima,
l’azione non accade.**
