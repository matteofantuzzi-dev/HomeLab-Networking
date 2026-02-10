# 🌐 Homelab Networking Infrastructure (UniFi Virtualized Stack)

Benvenuti nel repository ufficiale di documentazione della rete domestica. Questo progetto non è una semplice lista di dispositivi, ma un manuale tecnico che descrive l'architettura di rete basata su un **Controller UniFi virtualizzato in ambiente WSL2**.

## 🏗️ Architettura del Sistema
Il cuore della rete non è un hardware dedicato (come una Cloud Key), ma un'istanza software che gira su un PC Windows 11 Pro attraverso il **Windows Subsystem for Linux (WSL2)**.

### Perché questa architettura?
* **Isolamento:** Il controller gira in un ambiente Linux pulito, separato dai processi quotidiani di Windows.
* **Scalabilità:** Facilità di upgrade delle risorse (RAM/CPU) assegnate al controller.
* **Centralizzazione:** Gestione di switch e access point tramite un unico IP statico (`192.168.8.111`).

## 📊 Dashboard di Riepilogo
| Parametro | Valore |
| :--- | :--- |
| **Hostname Controller** | UniFi-WSL-Server |
| **Indirizzo IPv4 Host** | `192.168.8.111` |
| **Porta Management** | `8443 (HTTPS)` |
| **Metodo di Adozione** | L3 Adoption via Override Inform Host |
| **Sottorete Principale** | `192.168.8.0/24` |

## 📂 Organizzazione dei Contenuti
* [`/setup-controller`](./setup-controller/): Guida all'installazione, dipendenze Java e configurazione WSL.
* [`/firewall-security`](./firewall-security/): Matrice delle porte e regole di comunicazione.
* [`/network-layout`](./network-layout/): Piano di indirizzamento IP e configurazione DNS.
* [`/devices`](./devices/): Inventario hardware e procedure di ripristino (Disaster Recovery).
