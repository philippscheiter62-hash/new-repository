# Website psychotherapie-bessler.de – Gesamtüberblick

Übernommen aus dem ursprünglichen Claude-Chat, in dem die Website entstanden ist
(Stand Oktober 2026). Offene Punkte hier abhaken bzw. aktualisieren.

## Technik und Stand

- Statischer Onepager (reines HTML/CSS), live bei STRATO, mit SSL.
- Lighthouse: 100 Punkte.
- `.htaccess`: HTTPS erzwungen, `www` → ohne `www`, alte WordPress-Adressen per
  301 (`/impressum/`, `/57-2/`, `/datenschutz/`, `wp-*`).
- Kein Tracking: keine Cookies, keine Analyse-Werkzeuge. Schriften lokal,
  Google Maps nur verlinkt.
- Es gab eine ungenutzte Variante B („Himmel & Pastell“). Live ist Variante A.

## Design (Variante A „Ruhig & klar“)

- Farben: Papierweiß `#FAFCFB`, Tannengrün `#2C6755`, Hellgrün `#E9F2EF`,
  Sonnengelb `#F2C443` als einziger Akzent.
- Schriften: Fraunces für Überschriften und Telefonnummern (Null ohne Querstrich),
  Atkinson Hyperlegible für Text.
- Erkennungsmerkmale: handgezeichneter gelber Kreis um das Porträt; Logo mit zwei
  Köpfen in dunkler Textfarbe im Header.
- Übergänge: weiche Farbverläufe zwischen Abschnitten, keine Kanten, keine Wellen.
- Header deckend, Farbe passt sich beim Scrollen dem Abschnitt an; mobil Sprungleiste.
- Mobil zentriert: Hero, Überschriften, Themen, Footer. Linksbündig: Fließtexte,
  Karten, Ablauf, FAQ.
- Footer dezent, klein, grau, ohne Logo.
- Tonalität: therapeutisch, nicht beratend.

## Inhalte und Struktur

1. Hero: Überschrift, Einleitung mit „Psychologin und Kinder- und
   Jugendlichenpsychotherapeutin“, Buttons Telefon und E-Mail.
2. Mein Angebot: sechs Karten mit eigenen Linien-Icons, Kasten mit
   Störungsbereichen als Pillen (u. a. Depressionen, Essstörungen, ADHS).
3. So beginnt die Therapie: vier Schritte. Erstgespräch i. d. R. mit den Eltern,
   bei Jugendlichen auch ohne Eltern möglich.
4. Über mich: Text und drei Eckdaten. „Selbstständig seit“ nur im Text.
5. Häufige Fragen: acht Fragen, u. a. „Kinderpsychologin vs.
   Kinderpsychotherapeutin“. Überweisung: nur „Nein, nicht nötig.“ Einzugsgebiet
   inkl. Stadt und Landkreis Osnabrück.
6. Kontakt: drei Kacheln, Adresse verlinkt auf Lenas Google-Unternehmensprofil.

Bewusst entfernt: Lenas Zitat und der Hinweis „Falls ich gerade in einer Sitzung bin …“.

## SEO

- Titel: „Kinder- & Jugendpsychotherapie Ibbenbüren | Lena Beßler“.
- Beschreibung (146 Zeichen): Psychotherapeutin, Psychologin,
  Ibbenbüren-Laggenbeck, Verhaltenstherapie, privat, Beihilfe.
- Strukturierte Daten: Praxis, Person, Porträt, FAQ, Geo-Koordinaten,
  Verknüpfung zum Google-Profil, Einzugsgebiet.
- Sitemap mit Bild-Eintrag, `robots.txt`, 404-Seite.
- Search Console per DNS-TXT bestätigt, Sitemap eingereicht, Indexierung beantragt.
- Nach ca. zwei Wochen: 26 Klicks, 550 Impressionen, CTR 4,7 %, Ø Position 7,5.
  „psychotherapie ibbenbüren“ auf Position 10,5.

## Rechtstexte

- Impressum nach § 5 DDG. PTK NRW als Kammer und Aufsicht, kein KV-Eintrag
  (Privatpraxis). Berufsordnung „in der jeweils geltenden Fassung“.
- Datenschutz: Hoster STRATO (AV-Vertrag abgeschlossen), Server-Logs,
  Gesundheitsdaten nach Art. 9 DSGVO mit Hinweis auf unverschlüsselte E-Mails,
  LDI NRW als Aufsichtsbehörde, Google-Maps-Link, keine Cookies.

## Google-Unternehmensprofil

- Kategorien: primär „Kinderpsychotherapeut“, dazu Psychotherapeut/in,
  Kinderpsychologe, Psychologe/Psychologin.
- Beschreibung neu (663 Zeichen), Website-URL ohne `www`.
- Fotos: Porträt als Titelbild, Praxisschild. Porträt evtl. noch in Prüfung.
- Bewertungen: 5,0 Sterne bei 3 Bewertungen.
- Dr. Bohn hat dieselbe Adresse → abweichende Hauptkategorie und eigenes
  Praxisschild wichtig.

## Offene Punkte

- [ ] Randlose Fotos hochladen (gegen Vorschaubild mit weißem Rand), danach
      Indexierung erneut beantragen.
- [ ] Alte Adressen `/impressum/` und `/57-2/` in der Search Console entfernen
      („Nur diese URL“).
- [ ] Berufshaftpflicht im Impressum: Versicherer, Anschrift, räumlicher
      Geltungsbereich fehlen.
- [ ] Alte Profilseite bei Praxis Ewering: um Deaktivierung bitten, dann über
      Googles Tool für veraltete Inhalte entfernen.
- [ ] Verzeichnisse mit identischen Angaben pflegen: PTK-NRW-Suche, PTN Münster,
      therapie.de, jameda, Apple Business Connect, Bing Places.
- [ ] Google-Profil: Telefonzeiten, Logo, nach und nach Bewertungen
      (Schweigepflicht und Berufsrecht beachten).
- [ ] Search Console in 4–6 Wochen erneut auswerten.

## Inhalte, die noch fehlen

- Fotos der Praxisräume und des Eingangs mit gut sichtbarer Hausnummer (Website
  und Google-Profil). Größter verbleibender Hebel für Vertrauen.
- ADHS-Diagnostik: offen. Falls angeboten, eigene FAQ und Stichwort im Angebot
  („adhs diagnostik kinder“ wird gesucht).
- Telefonzeiten auf Website und im Profil, dann auch in den strukturierten Daten.
- Optional: FAQ zu Selbstzahler:innen bzw. gesetzlich Versicherten, falls Lena
  diese behandelt.
