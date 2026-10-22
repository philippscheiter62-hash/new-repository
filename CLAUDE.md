# Website (Strato)

Website der Praxis Lena Beßler (Kinder- und Jugendlichenpsychotherapie,
Ibbenbüren-Laggenbeck). Hintergrund, Entscheidungen und offene Punkte:
`docs/notizen.md` – vor inhaltlichen Änderungen lesen und danach aktualisieren.

Die Website liegt als statisches HTML in `site/`. Ein Push auf `main` lädt `site/`
per SFTP auf den Strato-Webspace hoch (`.github/workflows/deploy.yml`).

- Änderungen auf einem Feature-Branch machen. Live geht erst der Merge nach `main`.
- Der Deploy löscht nichts auf dem Server. Dateien, die hier entfernt werden,
  bleiben online, bis sie auf dem Server gelöscht werden. Darauf hinweisen.
- Keine Zugangsdaten ins Repo schreiben. Sie liegen als GitHub-Secrets vor.

## Regeln für Änderungen

- Design „Ruhig & klar“ beibehalten: nur die vier Farben aus `docs/notizen.md`,
  Gelb `#F2C443` als einziger Akzent; Fraunces für Überschriften und
  Telefonnummern, Atkinson Hyperlegible für Text.
- Kein Tracking, keine Cookies, keine externen Skripte, Schriften oder Embeds
  (Google Maps nur verlinkt). Sonst muss die Datenschutzerklärung angepasst werden.
- Lighthouse 100 halten: Bilder als WebP in passenden Größen, keine schweren Assets.
- Ton therapeutisch, nicht beratend.
- Kontaktdaten, Zeiten oder FAQ geändert → strukturierte Daten (JSON-LD in
  `index.html`) mit anpassen. Bei Änderungen am Inhalt `lastmod` in
  `sitemap.xml` aktualisieren.
- Angaben müssen mit dem Google-Profil und den Verzeichnissen übereinstimmen.
  Bei Änderungen an Adresse, Telefon oder Zeiten daran erinnern.
- Rechtstexte (Impressum, Datenschutz) nicht frei umformulieren; inhaltliche
  Änderungen nur auf Anweisung und mit Hinweis auf rechtliche Prüfung.
