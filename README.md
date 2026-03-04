# WOL-Manager

Ein grafischer Wake-on-LAN (WoL) Manager für Linux Mint, entwickelt als Workaround für
Probleme ab dem Kernel 6.8.0-100.

<img width="496" height="326" alt="screenshot" src="https://github.com/user-attachments/assets/4228c147-f3d2-406d-b100-d7bf0d5b1ca7" />

## Hintergrund
Seit dem Update auf Kernel 6.8.0-100 funktioniert Standard-WoL auf vielen Systemen nicht mehr zuverlässig. Dieses Tool nutzt eine spezifische Bash-Bridge via `netcat`, um das Magic Packet so zu senden, dass der Kernel es korrekt verarbeitet.

## Features
* **GTK3 Oberfläche**: Einfache und intuitive Bedienung.
* **4 Server-Slots**: Speichere Namen und MAC-Adressen dauerhaft.
* **Persistenz**: Die Daten werden in `~/.wol_config.json` gespeichert.
* **Abhängigkeits-Check**: Prüft beim Start, ob `netcat` installiert ist.

## Voraussetzungen
Das Tool benötigt Python 3 und `netcat`. Unter Linux Mint/Ubuntu installierst du die Abhängigkeiten so:

```bash
sudo apt update
sudo apt install python3-gi netcat-openbsd
```

## Installation
### Option 1: Manuell (Skript)
1. Repository klonen oder Skript herunterladen.
2. Ausführbar machen:
```bash
chmod +x wol_manager.py
```
3. Starten
```bash
./nwol_manager.py
```
### Option 2: Als Debian-Paket (Empfohlen)
.deb Datei bauen
```bash
dpkg-buildpackage -us -uc
```
Wenn du die .deb-Datei gebaut hast, installiere sie mit:
```bash
sudo dpkg -i nwol-manager_1.0_all.deb
sudo apt install -f
```
### Nutzung
1. Trage die Namen und MAC-Adressen deiner Server in die Felder ein.

2. Klicke auf Speichern, um die Daten dauerhaft zu sichern.

3. Wähle den gewünschten Server über den Radio-Button aus.

3. Klicke auf Sende Magic Packet (via Bash), um den Server zu wecken.
