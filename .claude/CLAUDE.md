# TileVisu Watches

Symcon-Kachel (HTML-SDK), die selbst eingefügte CodePen-Projekte (HTML, CSS, JavaScript) als Kachel zeigt, gedacht für Uhren. Öffentliches Repo `da8ter/TileVisu-Watches`. Bedienung: `TileVisuWatches/README.md`.

Betriebsdaten dieses Rechners (Stand der Arbeitskopie) stehen in `CLAUDE.local.md` (nicht eingecheckt).

## Aufbau

- **`TileVisuWatches/`**: einziges Modul, Klasse `TileVisuWatches`, Präfix `TVWA`, `IPSModule` (nicht Module Strict), ab Symcon 7.1.
- Im letzten Commit ist das Modul noch ein leeres Gerüst (Create/ApplyChanges/Destroy, leeres Formular); die Kachel-Funktion ist in Arbeit. Vor Änderungen `git status` und `git diff` ansehen.
- Geplanter Aufbau laut Arbeitsstand: Pens als Listen-Eigenschaft (Titel, HTML, CSS, JS), Auswahl eines Pens, `GetVisualizationTile` baut daraus das Kacheldokument. Der JavaScript-Teil eines Pens läuft dann ungeprüft in der Kachel: wer die Instanz konfigurieren darf, bestimmt Code im Visu-Browser.
- Keine Tests im Repo.

## Prüfen

```bash
php -l TileVisuWatches/module.php
python3 -m json.tool TileVisuWatches/form.json >/dev/null
```

Weicht das README vom Code ab, gilt der Code.

## Regeln

- **Commits:** deutsche Botschaft, ein Thema je Commit, **ohne** Co-Authored-By-Zeile; Prüfungen vorher.
- **Nie** `git checkout`/`git restore` auf Dateien: die Arbeitskopie kann nicht committete Arbeit enthalten.
- **Push und Release nur auf Zuruf.** Release: `version`, `build` und `date` in `library.json` hochsetzen (`date` ist ein Unix-Zeitstempel).
- **Öffentliches Repo:** keine IP-Adressen, Ports, Instanz-IDs, Token, Pfade unter `/Users/`, keine Personendaten – auch nicht in Tests und Kommentaren.
- **Symcon-Standards** für neuen Code: `strict_types`, bei einer Umstellung `IPSModuleStrict` mit vollen Typen (dann Mindestversion 8.1), Darstellungen statt Variablenprofilen, Texte über `locale.json`, Nutzertexte sagen „Symcon“. Solange die Klasse `IPSModule` erweitert, Overrides ohne Parametertypen lassen.

## Wissen

Gemeinsames Symcon-Plattformwissen: https://github.com/da8ter/SymDo-Family-Organizer/tree/SymDo-Beta/.claude/docs/plattform – lokal `../List/.claude/docs/plattform/`. Symcon-Fragen am offiziellen Handbuch prüfen.
