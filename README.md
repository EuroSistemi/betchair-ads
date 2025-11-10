# BetChair Pubblicità 🎮

Sistema di gestione pubblicità dinamica per dispositivi BetChair.

## Panoramica

Questo repository contiene tutte le immagini pubblicitarie utilizzate dal sistema BetChair:

- **Pubblicità Generica**: Mostrata all'avvio del sistema
- **Pubblicità per Giochi**: Mostrate quando l'utente seleziona un gioco specifico

## Struttura File

### Immagini Pubblicitarie
- `pubblicita-generica.png` - Pubblicità di default all'avvio
- `pulsante1-pubblicita.png` - Shining Crown  
- `pulsante2-pubblicita.png` - Triple Phoenix Power Combo
- `pulsante3-pubblicita.png` - Alpha Gods Anubis
- `pulsante4-pubblicita.png` - Royal Secrets

### File di Configurazione
- `configurazione-pubblicita.json` - Configurazione completa con GitHub Raw URLs
- Contiene mappatura pulsanti → nomi giochi → URL download
- Include configurazione schermata fallback

## Specifiche Tecniche

### Formato Immagini
- **Formato**: PNG
- **Risoluzione**: 1920x1080 (Full HD)
- **Modalità colore**: RGB
- **Compressione**: Ottimizzata per velocità caricamento

### Funzionamento Sistema

1. **Avvio Sistema**: 
   - Git pull per aggiornare configurazione
   - Download `pubblicita-generica.png` da GitHub Raw URL
2. **Pressione Pulsante** (modalità idle): 
   - Sistema esegue `git pull` per configurazione aggiornata
   - Download pubblicità specifica del gioco da GitHub Raw URL
   - Se download fallisce: mostra schermata "Hai scelto [Nome Gioco]"
3. **Connessione USB**: Transizione all'interfaccia BetChair

### Processo Upload Cliente

Per aggiornare le pubblicità il cliente può:

1. **Via GitHub Web Interface**:
   - Accede al repository betchair-pubblicita
   - Upload/sostituisce file PNG 
   - Sistema si aggiorna automaticamente

2. **Via Git Push** (per utenti tecnici):
   - Clone locale del repository
   - Sostituisce immagini e push
   
3. **Aggiornamento URL** (se necessario):
   - Modifica `configurazione-pubblicita.json`
   - Commit e push

### Modalità Fallback

Se una pubblicità specifica non è disponibile, il sistema mostra:
