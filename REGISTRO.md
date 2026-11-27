# Registro di ciò che abbiamo costruito (Thomas)

Leggi questo file a inizio sessione. Prima di costruire qualcosa di nuovo, controlla se esiste già.
Questo repository contiene solo puntatori: niente dati aziendali, mail, chiavi o database.

## Strumenti (PC aziendale Windows)

| Strumento | A cosa serve | Dove | Come si avvia | Stato |
|---|---|---|---|---|
| Assistente F&I (flottante) | App Windows Python/tkinter sempre a schermo: chat, posta, agenda/task, archivio, indice dei file, immagini, "cervello" (cervello.db) | `C:\Users\thomas.avallone\tools\assistente-fi\` (backup: `assistente-fi-backup`, copia ripulita: `assistente-fi-github`) | Doppio clic su `Assistente F&I.pyw` | Attivo. Test `test_*.py`. Log in `assistente.log` |
| Revisione codice assistente | Ogni giorno ChatGPT scrive un report sul repo ripulito; Claude verifica ogni voce, corregge e ripubblica | `tools\assistente-fi-github` (`report/`, `report/esiti/`) | Attività pianificata `revisione-codice-assistente-fi` | Attiva, giornaliera alle 10:30 |
| Archiviazione F&I | Sposta i file sciolti nelle cartelle tematiche (`_INDICE.md`, `_MOVIMENTI_riordino.csv`) | `Desktop\F&I`; script `tools\assistente-fi\riclassifica_radice.py` | Skill `archivia-fi` e attività del venerdì | Attiva, mai senza conferma di Thomas |
| Organizzatore Downloads | Tiene ordinata Downloads: file nuovi nella radice per 14 giorni, poi `Archivio\AAAA-MM\<famiglia>`; lettere di estinzione rinominate per cliente in `Estinzioni\AAAA`; installatori nel Cestino dopo 30 giorni; doppioni identici nel Cestino | `C:\Users\thomas.avallone\Downloads\OrganizeDownloads.ps1` (+ `RenameRules.ps1`, `ISTRUZIONI.txt`); versione per estensione salvata in `tools\organizzatore-downloads-backup-20261127` | Attività pianificata `OrganizzatoreDownloads` all'accesso; log in `%LOCALAPPDATA%\OrganizzatoreDownloads\log.txt` | v2 dal 27/11/2026 (riordino una tantum fatto, 26 installatori cestinati) |
| Strumenti web F&I (Hub, F&I Tracker, Bonus Dealer Usato, Foglio Analisi, Creatore Cartelline, Conteggio Estintivo, Provvigioni FIRST) | Tool HTML/JS con Firebase | `Desktop\STRUMENTI\` (la sua `CLAUDE.md` è la memoria tecnica) | `Hub.html` | Attivi. "Monday bug scan" ogni lunedì |
| Skill Audi | audi-deck-builder, liquidato-report, rinnovi-kpi | `~/.claude/skills` | Si attivano da sole | Attive |
| Altre attività pianificate | archivia-fi-settimanale, bozze-rinnovi-11-11, rivedi-dashboard-scadenze-trend, pac-pic-simulator-implementation, resume-risparmi-patrimonio-finish | `~/.claude/scheduled-tasks` | | Da verificare quali sono ancora attive |

## Strumenti personali

| Strumento | A cosa serve | Dove | Stato |
|---|---|---|---|
| Siro Calcetto / Scontro in Concessionaria | Giochi/artifact | artifact claude.ai `a2e8949b-3039-4e98-89a5-a617049cae3f` | Fatto |
| Telefono (Motorola Edge 50 Ultra) | Pulizia, ottimizzazione e suono notifiche Switch (`Switch_Snap_v2.wav`) via ADB | Nessun codice, solo comandi adb su USB con debug USB | Fatto. Ricordare di scollegare e spegnere il debug USB |
| Salute telefono | Scansione settimanale in sola lettura (spazio, batteria, RAM, cartelle pesanti, cache, app vecchie) con report e notifica | `C:\Users\thomas.avallone\tools\salute-telefono\` (`scansione.sh`) | Attivo dal 25/11/2026: Termux, scansione settimanale con storico CSV e controllo giornaliero allarmi (spazio < 500 GB, batteria calda). Grafici: `python grafico.py`. Briefing meteo Bologna (job Termux 2: 7-8 oggi, 20-22 domani) e allarmi (job 1) girano solo in Termux, senza ADB. Mini file server SFTP (Termux, porta 8022, solo chiave) da usare a casa dal Mac: `sftp-on.sh`/`sftp-off.sh`, manca ancora la chiave del Mac. Registro batteria ogni 30 min (`batteria.csv`, grafico `grafico_batteria.py`, job 3) e report mensile file pesanti con notifica dei 3 file piu vecchi in Download (`pesanti.sh`, job 4, solo elenco, mai cancella). Meteo per la bici (`bici.sh`, job 5): lun-ven, 4 fasce (8, 12:30, 14, 18:30), verdetto pioggia/ghiaccio/vento/vestiti, con le allerte della Protezione Civile Emilia-Romagna (zona C2). Grafico dei tragitti: `python grafico_tragitti.py`. Cruscotto sul telefono (`cruscotto.py` in Termux, 27/11/2026): pagina unica con diario della settimana modificabile (tocca una casella o il nome del giorno; server locale `--serve` con codice casuale, aggiunge righe a `tragitti.csv` senza cancellare), tragitti, risparmio e spesa stimata in carburante, benzina, batteria, telefono, file pesanti e controllo bici; si apre dal pulsante "Apri cruscotto" nelle notifiche di riepilogo o dall'icona Termux:Widget (installato 0.15.0 da F-Droid) e gira su un server locale 127.0.0.1:8790 che si spegne dopo 10 min. Icona in Home messa il 27/11/2026 (ultima pagina); Termux ha il permesso "Mostra sopra altre app": serve per far aprire Chrome dall'icona, senza Android blocca l'apertura. Diario tragitti: pulsanti "In bici"/"Auto"/"Altro" (Moto, Non lavoro tutto/mattina/pomeriggio) sulla notifica, al ritorno "Ancora <mezzo dell andata>", "Cambia" per 30 min, promemoria alle 21 per le tratte senza scelta, niente avvisi nei festivi e nelle ferie (`sh tragitto.sh ferie DA A`), avviso controllo bici ogni 300 km (`tragitto.sh`, `tragitti.csv`) e riepilogo settimanale (domenica sera) e mensile (`riepilogo.sh`, job 6) con spesa e risparmio calcolati sui consumi reali (auto 15 km/l, moto 17 km/l; 6,5 km a tratta in bici, 7,5 in auto/moto) e riepilogo annuale il 31/12 (mese migliore) e prezzo medio della benzina self a Bologna dai dati aperti MIMIT (`prezzo.sh`, `benzina.csv`). Cartelle di scambio `Da-Mac`/`Da-Telefono` + `scambio-mac.sh` (da provare a casa). Dopo un riavvio `adb tcpip 5555` serve solo per la scansione settimanale completa |
| Visore Osmo + VLC portatile | Pagina HTML locale per vedere i video della DJI Osmo con segnatempi in CSV. I video sono H.265: Edge senza estensione HEVC non mostra l'immagine, quindi si usa VLC 3.0.24 portatile (zip da videolan.org, hash verificato, non installato) | `C:\Users\thomas.avallone\tools\visore-osmo\visore.html` e `C:\Users\thomas.avallone\tools\vlc-portatile\Apri Osmo.bat` | Doppio clic su `Apri Osmo.bat`. Non copia né invia nulla | Creato 25/11/2026, VLC da verificare con i video reali |
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
