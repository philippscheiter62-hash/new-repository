# Website (Strato)

Die Website liegt als statisches HTML in `site/`. Ein Push auf `main` lädt `site/`
per SFTP auf den Strato-Webspace hoch (`.github/workflows/deploy.yml`).

- Änderungen auf einem Feature-Branch machen. Live geht erst der Merge nach `main`.
- Der Deploy löscht nichts auf dem Server. Dateien, die hier entfernt werden,
  bleiben online, bis sie auf dem Server gelöscht werden. Darauf hinweisen.
- Keine Zugangsdaten ins Repo schreiben. Sie liegen als GitHub-Secrets vor.
