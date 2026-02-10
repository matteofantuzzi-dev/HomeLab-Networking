# 🆘 Disaster Recovery & Troubleshooting Manual

Questo documento descrive le procedure da seguire per ripristinare la rete in meno di 10 minuti in caso di guasto critico.

## 🔄 Protocollo di Hard Reset (Dispositivo Bloccato)
Se lo switch non risponde o appare come "Managed by Other":
1.  Scollegare e ricollegare l'alimentazione.
2.  Con una clip, premere il tasto **RESET** per 10-12 secondi.
3.  Attendere il lampeggio del LED (stato Factory Default).
4.  Dal controller, eseguire l'adozione forzata.

## 💾 Gestione Backup (SOP - Standard Operating Procedure)
* **Frequenza:** Eseguire un backup manuale ogni volta che si cambia un nome o un IP.
* **Tipo di file:** `.unf` (UniFi Backup File).
* **Procedura:** Settings > System > Backups > Download.
* **Conservazione:** Una copia su questo repository GitHub (cartella privata) e una copia su Cloud esterno.

## 🚀 Risoluzione Rapida Problemi comuni
1.  **Dispositivo "Offline" sulla dashboard:** * Verifica che il PC `.111` sia acceso.
    * Verifica che l'app "UniFi OS Server" sia in stato "Running".
2.  **Adozione fallita (loop infinito):** * Controlla se l'IP del PC è cambiato (deve restare `.111`).
    * Disabilita momentaneamente il firewall di Windows per testare la connessione.
3.  **Errore Database:** * Riavviare la WSL con il comando `wsl --shutdown` e riaprire il controller.
