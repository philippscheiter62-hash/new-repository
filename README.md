# Home Assistant mit Claude steuern

Ziel: Home Assistant aus Claude heraus steuern (Geräte schalten, Zustände
abfragen, Automationen bauen) und Dashboards direkt von Claude erstellen lassen.

Dafür nutzen wir den Community-MCP-Server
[**ha-mcp**](https://github.com/homeassistant-ai/ha-mcp). Der offizielle
„Model Context Protocol Server“ von Home Assistant kann nur Geräte über die
Assist-API steuern; **Dashboards bearbeiten kann er nicht**. ha-mcp kann beides
(u. a. `ha_config_get_dashboard`, `ha_config_set_dashboard`).

## 1. ha-mcp in Home Assistant installieren

Variante A: Add-on (am einfachsten, kein Token nötig)

1. *Einstellungen → Add-ons → Add-on Store → ⋮ → Repositories*:
   `https://github.com/homeassistant-ai/ha-mcp` hinzufügen.
2. **Home Assistant MCP Server** installieren und starten.
3. Im Tab **Log** steht die MCP-URL. Die brauchst du gleich.

Variante B: Integration über HACS

1. In HACS das Repository `homeassistant-ai/ha-mcp` hinzufügen und
   **HA-MCP Server** installieren, dann Home Assistant neu starten.
2. *Einstellungen → Geräte & Dienste → Integration hinzufügen → HA-MCP Server*.
3. Unter **Konfigurieren** die Connect-URL kopieren.

## 2. Von außen erreichbar machen

claude.ai und die Cloud-Sessions laufen nicht in deinem Heimnetz. Die MCP-URL muss
deshalb über HTTPS aus dem Internet erreichbar sein, zum Beispiel über
**Nabu Casa** (Home Assistant Cloud), einen Reverse-Proxy mit Domain oder einen
Cloudflare Tunnel. Die URL enthält einen geheimen Pfad. Behandle sie wie ein
Passwort.

> Wenn du Claude Code nur lokal im selben Netz nutzt, reicht die lokale URL
> (z. B. `http://homeassistant.local:...`).

## 3. Mit Claude verbinden

### claude.ai / Claude-App (empfohlen)

1. https://claude.ai/customize/connectors → **Benutzerdefinierten Connector hinzufügen**.
2. Name: `Home Assistant`, URL: die öffentliche MCP-URL aus Schritt 2.
3. Danach eine **neue** Unterhaltung oder Session starten. Connectoren werden beim
   Start geladen.

Der Connector steht dann im Chat, in der App und in Claude-Code-Sessions im Web
zur Verfügung.

### Claude Code (lokal oder Cloud) über dieses Repo

Die Datei `.mcp.json` bindet den Server ein. Die URL kommt aus der
Umgebungsvariable `HA_MCP_URL` und steht damit nicht im Repo.

- **Lokal:** `export HA_MCP_URL="https://…/dein-secret-pfad"`, dann `claude` im
  Repo starten, das Projekt-MCP freigeben und mit `/mcp` prüfen.
- **Cloud-Session (claude.ai/code):** In den Einstellungen der Cloud-Umgebung
  `HA_MCP_URL` als Umgebungsvariable setzen. Unter **Network access** die Domain
  deines Home Assistant bei *Allowed domains* eintragen (oder vollen Zugriff
  erlauben). Danach eine neue Session starten.
  Doku: https://code.claude.com/docs/en/cloud-environments#network-access

Richte pro Client nur **einen** Weg ein (Connector **oder** `.mcp.json`).
Doppelte Einträge für denselben Server können hängen bleiben.

## 4. Ausprobieren

- „Welche Lichter sind gerade an?“
- „Schalte das Wohnzimmerlicht auf 30 % und warmweiß.“
- „Erstelle ein Dashboard *Energie* mit Stromverbrauch, PV-Ertrag und
  Batteriestand als Graphen.“
- „Bau mir eine Automation: Flurlicht bei Bewegung nach Sonnenuntergang für 2 Minuten an.“

Claude sichert geänderte Dashboards als YAML in [`dashboards/`](dashboards/)
(siehe `CLAUDE.md`).

## Sicherheit

- Die MCP-URL mit Secret-Pfad bzw. der Long-Lived-Token gewährt Vollzugriff auf
  Home Assistant. Gib sie nicht weiter und committe sie nicht.
- Wenn du ein Token nutzt, lege dafür besser einen eigenen HA-Benutzer an. Den
  kannst du jederzeit sperren.
