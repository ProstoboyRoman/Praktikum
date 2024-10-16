# DNS Setup Praktikanten

## Teil 1 - Bind9 Basis Config

* VM Setup (beststehende verwenden)
* BIND9 Installieren (z.B. [Anleitung auf ubuntuusers.de](https://wiki.ubuntuusers.de/DNS-Server_Bind/))
* BIND9 konfigurieren, dass auf TCP und UDP gelauscht wird
    * Überprüfen: `ss -tulpn` oder`netstat -tulpn`
    * Du hast zwar `bind9` installiert, der Prozess heißt aber `named`!
    * Für was stehen die einzelnen Buchstaben in `tulpn`? (`man netstat`, `man ss`)
    * Wo finden sich die Logs von bind? Wie kannst du dir diese ansehen? 
    * Wie kannst du den Service neu starten?
* Zone "talakh.de." konfigurieren
    * A-Record: roman.talakh.de auf `127.123.123.1` anlegen
    * AAAA-Record: roman.talakh.de auf ``::1` anlegen
* Einträge verifizieren
    * Vom Server: `host roman.talakh.de 127.0.0.1` sollte folgendes zurückgeben:
      ```
      roman.talakh.de has address 127.123.123.1
      roman.talakh.de has IPv6 address ::1
      ```
        * Warum steht an dem `host` command als zweites Argument `127.0.0.1`?
        * Wie kannst du mit `host` explizit eine Anfrage über TCP oder UDP absetzen?

## Teil 2 - Bind9 Secondary Setup

* Forwarding auf 8.8.8.8 & 8.8.4.4 konfigurieren
    * Was bewirkt das?
    * Lokales aufloesen von externen Eintraegen `host heise.de 127.0.0.1`
    * Von deinem Macbook: wie kannst du den DNS-Server erreichen? 
        * Stichwork Netzwerkinterface Konfig im Virtual Box
* Setup eines DNS Secondarys
    * Zone Replication mit AXFR einrichten
    * Automatisches Update der Secondary Zone bei Update auf Primary
* Neuen DNS CNAME Record erstellen: `dgi.talakh.de` soll auf `roman.talakh.de` zeigen
    * Von deinem Macbook sollte damit `host dgi.talakh.de [secondary DNS-Server]` das Richtige zurück geben
        * Was ist ein CNAME Record?
        * Wie unterscheidet dieser sich von einem ALIAS Record? 

## Teil 3 - Monitoring

* Setup von Prometheus & Grafana
* Installation von [node_exporter](https://github.com/prometheus/node_exporter) auf beiden Servern
* Installation von [bind_exporter](https://github.com/prometheus-community/bind_exporter) auf beiden Servern
* Einbindung der Exporter in Prometheus
* Erstellung von Dashboards in Grafana
