# 🔐 Network Security & Firewall Orchestration

Per permettere la comunicazione bidirezionale tra i dispositivi fisici (Switch, AP) e il controller virtuale su WSL2, è stata implementata una politica di sblocco porte specifica nel Firewall di Windows.

## 🚦 Matrice delle Porte (Inbound Rules)

### 1. Management & Provisioning (Fondamentali)
* **TCP 8080 (Inform Port):** La porta più importante. I dispositivi inviano qui i pacchetti di stato. Se questa porta è chiusa, i dispositivi risulteranno "Offline" anche se funzionanti.
* **UDP 3478 (STUN):** Permette al controller di stabilire connessioni interattive con i dispositivi dietro NAT o firewall. Necessaria per l'apertura del terminale remoto (SSH via GUI).

### 2. Discovery & Adoption
* **UDP 1900 / 10001:** Utilizzate per il protocollo proprietario Ubiquiti Discovery. Permettono al controller di "vedere" uno switch nuovo appena collegato (stato *Pending Adoption*).

### 3. Accesso Utente & GUI
* **TCP 8443:** Porta di gestione web criptata (HTTPS). È l'indirizzo che digiti nel browser per configurare la rete.
* **TCP 8843 / 8880:** Porte dedicate al portale ospiti (Guest Portal) per l'autenticazione Wi-Fi.

## 🛠️ Risoluzione dei Conflitti di Porta
Se il controller fallisce l'avvio con l'errore *"Port 8080 is already in use"*:
1.  Aprire il terminale come amministratore.
2.  Eseguire: `netstat -ano | findstr :8080`.
3.  Identificare il PID e chiudere l'applicazione interferente.
4.  Riavviare il servizio UniFi OS Server.

> **Nota di Sicurezza:** Le regole del firewall sono limitate esclusivamente alla sottorete locale `192.168.8.0/24` per prevenire accessi non autorizzati dall'esterno.
