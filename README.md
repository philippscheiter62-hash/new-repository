# Website

Statische Website, gehostet bei Strato. Die Dateien liegen in [`site/`](site/).
Jeder Push auf `main`, der etwas in `site/` ändert, lädt die Seite automatisch
per SFTP zu Strato hoch.

## Einrichtung (einmalig)

### 1. SFTP-Zugang bei Strato anlegen

Strato-Kundenlogin → **Datenbanken und Webspace → SFTP & SSH**:

- Oben rechts steht der **Servername** (Muster `5xxxxxxxx.ssh.wN.strato.hosting`).
- **+ Neu anlegen**: Typ **SFTP**, Passwort vergeben, Startverzeichnis wählen.
  Am besten das Verzeichnis, in dem deine Website liegt.
- Den angezeigten **Benutzernamen** (z. B. `su…`) notieren.

### 2. Secrets in GitHub hinterlegen

Repo → **Settings → Secrets and variables → Actions**:

| Typ      | Name                | Wert                                         |
|----------|---------------------|----------------------------------------------|
| Secret   | `STRATO_HOST`       | Servername aus Schritt 1                     |
| Secret   | `STRATO_USER`       | SFTP-Benutzername                            |
| Secret   | `STRATO_PASSWORD`   | SFTP-Passwort                                |
| Variable | `STRATO_REMOTE_DIR` | optional, Zielordner relativ zum Startverzeichnis (Standard: `.`) |

### 3. Bestehende Website ins Repo holen

Den aktuellen Inhalt deines Webspace (z. B. per FileZilla mit denselben
SFTP-Daten heruntergeladen) nach `site/` legen und committen.

## Arbeitsweise

1. Claude ändert die Dateien in `site/` auf einem Branch.
2. Du prüfst die Änderung im Pull Request.
3. Nach dem Merge nach `main` geht sie automatisch live. Der Status steht unter **Actions**.

Manuell auslösen: **Actions → Deploy to Strato → Run workflow**.

> Der Deploy lädt nur hoch und **löscht nichts** auf dem Server. Wird hier eine
> Datei entfernt, muss sie auch auf dem Server gelöscht werden.
