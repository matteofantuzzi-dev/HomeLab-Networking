# 📈 IP Management & Device Inventory

Una rete professionale si distingue per la gestione rigorosa degli indirizzi statici. Non ci affidiamo al DHCP per i componenti dell'infrastruttura.

## 🗺️ Piano di Indirizzamento (IP Schema)
| Dispositivo | IP Statico | MAC Address | Ruolo Tecnico |
| :--- | :--- | :--- | :--- |
| **Controller PC** | `192.168.8.111` | *[Inserisci MAC]* | Host Network Server (WSL2) |
| **Switch Core** | `192.168.8.128` | *[Inserisci MAC]* | USW-Flex-Mini (Distribuzione) |
| **Local DNS** | `192.168.8.107` | *[Inserisci MAC]* | DNS Primario (Ad-Blocking) |
| **Gateway ISP** | `192.168.8.1` | *[Inserisci MAC]* | Router / Uscita Internet |

## ⚙️ Configurazione "L3 Override"
Per garantire la massima stabilità, abbiamo configurato l'**Override Inform Host**. 
* **Funzione:** Impedisce ai dispositivi di cercare il controller tramite broadcast (spesso inaffidabile).
* **Valore:** `192.168.8.111`.
* **Effetto:** Anche in caso di riavvio dello switch, esso saprà esattamente che deve "bussare" all'indirizzo `.111` per ricevere la configurazione.

## 🌐 Parametri DNS & Subnet
* **Subnet Mask:** `255.255.255.0`
* **DNS Primario:** `192.168.8.107` (Ottimizzato per velocità e sicurezza).
* **DNS Secondario:** `8.8.8.8` (Failover Google).
