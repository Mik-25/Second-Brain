# Schema Second Brain — istruzioni per l'agente LLM

Sei il maintainer di questo wiki. Non scrivi mai nelle Raw Sources (PDF/appunti caricati), le leggi soltanto. Scrivi/aggiorni solo file .md nelle cartelle wiki.

## Struttura
- `Giurisprudenza/{Anno}/{Semestre}/{Materia}/Materiali-Elly/` = sorgenti immutabili (dispense, slide)
- `Giurisprudenza/{Anno}/{Semestre}/{Materia}/Sbobine-Appunti/` = sorgenti immutabili (sbobine, appunti)
- `Giurisprudenza/{Anno}/{Semestre}/{Materia}/index.md` = sintesi materia (LLM la crea/aggiorna a ogni ingest)
- `Programmazione/{Linguaggio}/...` = stessa logica: sorgenti nelle sottocartelle, sintesi in index.md
- `Mike-Personale/` = area libera, no schema fisso

## Operazioni
1. **Ingest**: nuovo file caricato → leggilo → aggiorna `index.md` della materia/linguaggio con: riassunto, concetti chiave, collegamenti ad altre pagine → aggiungi riga a `log.md` root (formato: `## [YYYY-MM-DD] ingest | percorso file`)
2. **Query**: leggi prima `index.md` di primo livello (root) per capire dove cercare, poi entra nelle sottocartelle pertinenti, poi rispondi citando le fonti
3. **Lint periodico**: cerca pagine orfane, contraddizioni tra sbobine/materiali, concetti citati ma senza pagina propria

## Convenzioni
- Ogni index.md ha in cima: `Ultimo aggiornamento: YYYY-MM-DD`
- Materie/linguaggi non ancora usati restano vuoti (cartella + .gitkeep) finché non arriva il primo file
- Rinominare `Materia-Esempio` con il nome reale della materia alla prima ingest
