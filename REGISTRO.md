# Registro di ciò che abbiamo costruito (Thomas)

Leggi questo file a inizio sessione. Prima di costruire qualcosa di nuovo, controlla se esiste già.
Questo repository contiene solo puntatori: niente dati aziendali, mail, chiavi o database.

## Strumenti (PC aziendale Windows)

| Strumento | A cosa serve | Dove | Come si avvia | Stato |
|---|---|---|---|---|
| Assistente F&I (flottante) | App Windows Python/tkinter sempre a schermo: chat, posta, agenda/task, archivio, indice dei file, immagini, "cervello" (cervello.db) | `C:\Users\thomas.avallone\tools\assistente-fi\` (backup: `assistente-fi-backup`, copia ripulita: `assistente-fi-github`) | Doppio clic su `Assistente F&I.pyw` | Attivo. Test `test_*.py`. Log in `assistente.log` |
| Revisione codice assistente | Ogni giorno ChatGPT scrive un report sul repo ripulito; Claude verifica ogni voce, corregge e ripubblica | `tools\assistente-fi-github` (`report/`, `report/esiti/`) | Attività pianificata `revisione-codice-assistente-fi` | Attiva, giornaliera alle 10:30 |
| Archiviazione F&I | Sposta i file sciolti nelle cartelle tematiche (`_INDICE.md`, `_MOVIMENTI_riordino.csv`) | `Desktop\F&I`; script `tools\assistente-fi\riclassifica_radice.py` | Skill `archivia-fi` e attività del venerdì | Attiva, mai senza conferma di Thomas |
| Strumenti web F&I (Hub, F&I Tracker, Bonus Dealer Usato, Foglio Analisi, Creatore Cartelline, Conteggio Estintivo, Provvigioni FIRST) | Tool HTML/JS con Firebase | `Desktop\STRUMENTI\` (la sua `CLAUDE.md` è la memoria tecnica) | `Hub.html` | Attivi. "Monday bug scan" ogni lunedì |
| Skill Audi | audi-deck-builder, liquidato-report, rinnovi-kpi | `~/.claude/skills` | Si attivano da sole | Attive |
| Altre attività pianificate | archivia-fi-settimanale, bozze-rinnovi-11-11, rivedi-dashboard-scadenze-trend, pac-pic-simulator-implementation, resume-risparmi-patrimonio-finish | `~/.claude/scheduled-tasks` | | Da verificare quali sono ancora attive |

## Strumenti personali

| Strumento | A cosa serve | Dove | Stato |
|---|---|---|---|
| Siro Calcetto / Scontro in Concessionaria | Giochi/artifact | artifact claude.ai `a2e8949b-3039-4e98-89a5-a617049cae3f` | Fatto |
| Telefono (Motorola Edge 50 Ultra) | Pulizia, ottimizzazione e suono notifiche Switch (`Switch_Snap_v2.wav`) via ADB | Nessun codice, solo comandi adb su USB con debug USB | Fatto. Ricordare di scollegare e spegnere il debug USB |
| Salute telefono | Scansione settimanale in sola lettura (spazio, batteria, RAM, cartelle pesanti, cache, app vecchie) con report e notifica | `C:\Users\thomas.avallone\tools\salute-telefono\` (`scansione.sh`) | Script pronto e provato dal PC via ADB. Manca Termux sul telefono per l'esecuzione autonoma (da fare con l'ok di Thomas) |
| Esperimenti | gemini.py, Ghidra/JDK (reverse), REA, chatbox multi-IA, ROM Gameboy→APK | `tools\` e sessioni di ottobre | Esperimenti |

## Progetti su GitHub (account ThomasAvallone, usati da Mac e iPad)

| Progetto | A cosa serve | Dove | Note |
|---|---|---|---|
| App-calcetto | App del calcetto (statistiche SIRO), con audit giornalieri in `audit-reports/` | github.com/ThomasAvallone/App-calcetto | README vuoto |
| Motion-Graphics-Calcetto | Grafiche broadcast per i video di calcetto 5v5 per Final Cut Pro | github.com/ThomasAvallone/Motion-Graphics-Calcetto | `npm install`, poi `node partita.mjs partita.json`. Playwright e ffmpeg. Skill `calcetto-motion` |
| calcettocam | Comando Python con ffmpeg: incrocia i dati salvati dal Garmin durante la partita e taglia in automatico il video (girato con DJI Osmo Action 6 sulla testa) in corrispondenza dei lap inseriti dall'orologio | github.com/ThomasAvallone/calcettocam | Creato sul Mac: il codice potrebbe esistere solo in locale, la repo su GitHub ha solo un commit iniziale e il README è vuoto |
| MoToM | Sistema di lavoro del canale YouTube MoToM: idee, script, trend. Repo privata | github.com/ThomasAvallone/MoToM | Ha un suo CLAUDE.md e le skill `motom-script`, `motom-trend` |

## Regole di lavoro
- Rispondi in italiano.
- Chiedi prima di scaricare, cancellare, installare o cambiare configurazioni.
- Non inserire PIN o password e non sbloccare il telefono.
- I dati aziendali non vanno a servizi esterni né in questo repository.

## Come tenerlo aggiornato
A fine lavoro su uno strumento nuovo si aggiunge una riga qui, poi `git pull`, commit e `git push`.
Sugli altri dispositivi: `git pull` prima di iniziare. I percorsi `C:\...` valgono solo per il PC aziendale.
