# 🛠️ Manutenzione Database e Ottimizzazione Risorse

Questo documento descrive le operazioni periodiche necessarie per garantire che il controller UniFi rimanga reattivo e non saturi le risorse del PC host.

## 1. Ottimizzazione della Memoria Java (Xmx/Xms)
Il controller UniFi è basato su Java, che di default può tentare di allocare più RAM di quella necessaria, rallentando Windows.
* **Configurazione:** È stato verificato il file `system.properties` per limitare l'uso della memoria.
* **Parametri consigliati:** Se il PC ha 16GB di RAM, limitare Java a 2GB aggiungendo `unifi.xmx=2048` nel file di configurazione.
* **Perché farlo:** Evita che il processo `java.exe` causi rallentamenti durante le sessioni di gioco o di lavoro sul PC.

## 2. Manutenzione del Database (MongoDB)
UniFi utilizza MongoDB per memorizzare le statistiche di traffico. Se non gestito, il database può crescere a dismisura.
* **Data Retention:** Impostata nelle impostazioni del controller (Settings > System > Data Retention).
* **Pulizia manuale:** In caso di database corrotto o troppo pesante, è documentata la procedura di "Pruning" tramite script ufficiale Ubiquiti per rimuovere i log storici mantenendo le configurazioni dei dispositivi.

## 3. Gestione degli Aggiornamenti
* **Aggiornamento Software:** Prima di aggiornare la Network Application su Windows, eseguire sempre un backup `.unf`.
* **Aggiornamento Firmware Dispositivi:** Lo switch USW-Flex-Mini deve essere aggiornato solo dopo aver verificato la stabilità della versione sul forum ufficiale (UI Community), per evitare che l'adozione fallisca dopo l'update.

## 4. Script di Controllo Stato (WSL)
Per verificare rapidamente se il "motore" del controller è attivo senza aprire la GUI:
1. Aprire il terminale (PowerShell/CMD).
2. Digitare: `netstat -ano | findstr :8443`.
3. Se non restituisce nulla, il servizio è spento e va riavviato.
