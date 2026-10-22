# Home Assistant über Claude

Dieses Repo verbindet Claude mit Home Assistant über den MCP-Server `ha-mcp`
(https://github.com/homeassistant-ai/ha-mcp). Die Tools heißen `ha_*`.

## Regeln beim Arbeiten mit Home Assistant

- Bevor du ein bestehendes Dashboard änderst: aktuelle Konfiguration mit
  `ha_config_get_dashboard` holen und als YAML unter `dashboards/<url_path>.yaml`
  sichern, damit man zurückrollen kann.
- Neue oder geänderte Dashboards ebenfalls als YAML in `dashboards/` ablegen.
- Nur Entitäten verwenden, die es wirklich gibt (vorher abfragen), keine IDs raten.
- Vor riskanten Aktionen (Schlösser, Alarmanlage, Heizung abschalten, Automationen
  löschen) nachfragen.
- Keine Tokens oder URLs mit Secret-Pfad ins Repo schreiben.
