# Specifica tecnica — IPR-Datacenter

## 1. Scopo (Scope)

Definire un modello di datacenter che subordina l’esecuzione di qualsiasi azione digitale
alla verifica preventiva di un Identity Primary Record (IPR).

## 2. Principio fondamentale

Un’azione NON deve essere eseguita se, prima dell’esecuzione,
non esistono condizioni verificabili di responsabilità e tracciabilità.

Modalità operativa: FAIL-CLOSED.
In assenza di prova → nessuna esecuzione.

## 3. Campo di applicazione

La specifica si applica a:
- servizi di calcolo (CPU/GPU/AI)
- storage e processing ad alto impatto
- orchestratori di workload (Kubernetes, Slurm, Nomad, ecc.)
- ambienti B2B e B2G
- contesti soggetti a obblighi di audit, accountability e conformità UE

## 4. Non-obiettivi

La specifica:
- non valuta il merito delle decisioni;
- non sostituisce autorità umane o istituzionali;
- non costituisce certificazione automatica di conformità;
- non richiede custodia di dati personali.

## 5. Definizioni operative

### 5.1 Azione (Job / Task)
Qualsiasi operazione che produca un effetto tecnico, economico o sociale
non reversibile o solo parzialmente reversibile.

### 5.2 IPR (Identity Primary Record)
Traccia tecnica ex-ante che attesta:
- attribuzione umana/istituzionale
- decisione esplicita
- prova opponibile (hash-only)
- responsabilità non neutralizzabile
- esposizione temporale auditabile

### 5.3 Decision Gate (DGC / JOKER)
Modulo che verifica le condizioni ex-ante e abilita o blocca l’azione.

## 6. Requisiti minimi ex-ante (Mandatory)

Prima dell’esecuzione di qualsiasi azione, il sistema DEVE verificare:
- R1 Attribuzione (soggetto responsabile identificabile)
- R2 Decisione esplicita (no default silenziosi)
- R3 Traccia opponibile (prova deterministica e persistente)
- R4 Responsabilità/costo non neutralizzabile
- R5 Esposizione temporale (verificabilità futura)

## 7. Comportamento del sistema

### 7.1 Caso conforme
Se tutti i requisiti sono soddisfatti:
- il Decision Gate emette PASS
- l’orchestratore abilita l’azione
- il sistema produce Evidence Pack

### 7.2 Caso non conforme
Se almeno un requisito non è soddisfatto:
- il Decision Gate emette FAIL + reason_code
- l’orchestratore NON esegue l’azione
- l’evento è registrato come tentativo bloccato
- nessun fallback permissivo è ammesso

## 8. Output

Per ogni azione:
- AUTHORIZED + EvidencePack (hash-only)
oppure
- DENIED + reason_code (verificabile)
