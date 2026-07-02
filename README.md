# Libretto d'uso — Second Brain

## 1. Cos'è
Wiki mantenuto da un LLM. I file caricati (fonti) restano intatti; l'LLM li legge e scrive sintesi collegate (`index.md`) che si accumulano nel tempo. Diverso da upload RAG classico: qui la conoscenza si stratifica invece di essere ricalcolata ogni volta.

## 2. Struttura
```
SecondBrain/
├── index.md        # mappa generale
├── log.md          # storico cronologico
├── CLAUDE.md / AGENTS.md / GEMINI.md   # istruzioni per l'LLM
├── Giurisprudenza/
│   └── {Anno 1-5}/{Semestre 1-2}/{Materia}/
│       ├── Materiali-Elly/      # dispense, slide docente
│       └── Sbobine-Appunti/     # sbobine + appunti tuoi
├── Programmazione/
│   ├── Arduino/  → Corso, Braccio, Programmi-Arduino
│   ├── C/        → C, C++, C#
│   ├── Java/     → Java, JavaScript
│   ├── HTML/
│   ├── Python/   → Python, MicroPython
│   ├── Swift/, CyberSecurity/, M5Stack/
│   └── IDE/      → VisualStudioCode, Thonny, Processing
└── Mike-Personale/   # area libera
```
Rinomina `Materia-Esempio` col nome reale alla prima ingest.

## 3. Caricamento file
Trascina il file nella sottocartella corretta → chiedi all'LLM: *"ho aggiunto [file] in [percorso], aggiorna il wiki"*. L'agente aggiorna `index.md` locale + riga in `log.md` (root).

## 4. Query
Chiedi normalmente (es. "confronta C e C++"). L'LLM legge `index.md` root → entra nelle pagine pertinenti → risponde con citazioni. Risposte utili → salvale come nuove pagine, non lasciarle in chat.

## 5. Collegamento tool
| Tool | Come |
|---|---|
| Claude | legge `CLAUDE.md`, carica cartella/repo |
| Codex | legge `AGENTS.md` |
| Gemini | legge `GEMINI.md` |
| ChatGPT | Project + istruzioni di CLAUDE.md incollate |
| NotebookLM | carica `Materiali-Elly`/`Sbobine-Appunti` come sources |
| Notion | Import → Markdown |

## 6. Manutenzione
Ogni tanto: *"fai un lint del wiki"* → cerca pagine orfane, contraddizioni, concetti senza pagina propria.

## 7. Consigli
- Obsidian per graph view / link automatici
- Un file per ingest, resta coinvolto a controllare le sintesi
- Git sulla cartella per versioning/backup
- `log.md` = timeline di tutto ciò che è stato fatto
