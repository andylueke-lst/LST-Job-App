# LST Job-App · Testversion 0.3.0

Eigenständige, offlinefähige Web-App für mehrtägige Baustellenjobs und den elektronischen Lieferscheinabschluss.

**Status:** Testbetrieb. Kein produktiver Notion-Abgleich und keine automatische Übertragung zum Mac mini. Alle eingegebenen Daten liegen im Browser des jeweiligen Geräts. Die GitHub-Seite bietet keine gemeinsame Jobdatenbank und keinen Zugangsschutz für die Programmoberfläche. Auf GitHub liegen nur Programmdateien und fiktive Testdaten.

## Auf dem iPad beginnen

1. Die veröffentlichte GitHub-Pages-Adresse in Safari öffnen.
2. Teilen → Zum Home-Bildschirm, dann die App über dieses Symbol öffnen.
3. „Offline-Programm installiert“ abwarten.
4. „Beispieljob laden (Testdaten)“ antippen. Dieser enthält einen ausdrücklich fiktiven Lieferschein.
5. Vorbereitung, Durchführung und Abschluss ausprobieren. Für den Offline-Test zuvor alle benötigten Dateien lokal laden.

## Enthalten

- Startseite mit Anstehend, In Arbeit und Abgeschlossen.
- Vorbereitung: Auftraggeber getrennt vom Betrieb vor Ort, Einsatzadresse, Kontakt/Telefon, Arbeitsauftrag, Packliste und Besonderheiten. Fehlende Angaben sichtbar.
- Mehrere Arbeitstage pro Job, eigene Berichte und Mitarbeiter-/Materialangaben pro Tag. Tagesberichte werden automatisch lokal gespeichert; explizites Speichern bleibt möglich.
- Vorher-/Nachher-Fotos per Kamera oder Dateiauswahl, mit Datum und Jobzuordnung. Für die lokale Dokumentation werden sie als JPEG auf maximal 2048 Pixel Kantenlänge verkleinert; Kameraoriginale sind separat aufzubewahren, falls sie benötigt werden.
- Zeiteingabe über rollbare Stunden-/Minutenfelder. Minuten ausschließlich 00/15/30/45. Tagesarbeitszeit je Person/Datum einmal; Auftragsabschnitte separat je Job. Überlappungsprüfung und getrennte Pausen.
- Atlas Copco XAHS 186 DD vorausgewählt; benannte Mietkompressoren separat. Anfang/Ende mit einer Nachkommastelle, bestätigter Anfangsstand und jobübergreifender Vorschlag. Laufzeit- und Reihenfolgeprüfung.
- Tankvorgänge mit Datum, Gerät, Betriebsstunden und Literzahl. Übersichten je Job und über alle lokalen Jobs.
- Matthias und Faro vorbelegt; weitere Namen werden als Auswahl gespeichert.
- Alle datierten Berichte ab Seite 3; bei Platzbedarf Fortsetzungsseiten. Eine gemeinsame Abschlussbestätigung und eine Unterschrift am Ende aller Berichte.
- Lieferschein und Fotodokumentation als getrennte PDFs, ohne interne Stunden oder Tankdaten. PDF-Seitenvorschau mit Zurück-Button und Seitenwechsel.
- Unterzeichner, Betrieb vor Ort und Auftraggeber bleiben getrennt. Keine Kopie an den Unterzeichner ist voreingestellt. Optional Lieferschein oder Lieferschein mit Fotos als Kopie.
- Unabhängige Büroübergabe: unterschriebene PDF und interne Jobakte. Die vorgesehene Adresse `jobs@lueke-strahlt.de` muss vor einem Testversand geprüft werden; ihre Einrichtung wurde noch nicht bestätigt.
- Vollständige lokale JSON-Sicherung und Wiederherstellung auf einem leeren Browser. Abweichende vorhandene Datensätze werden nicht still überschrieben.

## Abschluss und Versand

„Abschluss vorbereiten“ prüft alle Tage. Ein Tag mit Fotos oder Protokollen braucht einen Arbeitsbericht oder eine ausdrücklich begründete Markierung „kein Kundenbericht nötig“, beispielsweise für reine Anreise.

Nach Vorschau, Namen, Datum und Unterschrift erzeugt „Fertig“ unveränderliche Archivfassungen. Eine Berichtkorrektur erfordert einen neuen Abschluss und eine neue Unterschrift. Frühere PDFs bleiben erhalten; interne Stunden lassen sich ohne neue Kundenunterschrift korrigieren. Eine neue interne Korrektur gehört in eine aktuelle Sicherung; das bereits archivierte Büro-Paket bleibt eine historische Fassung.

Das Programm sendet keine E-Mail selbst. Für jede Mail Adresse kopieren, Anhänge an Mail übergeben, Empfänger einsetzen, prüfen und selbst senden. Eine App-Übergabe ist keine bestätigte Zustellung. Die Büroübergabe bleibt unabhängig von der optionalen Kopie vor Ort.

## Vorbereitung der Notion-Anbindung

Der spätere reguläre Weg ist Notion → Dienst auf dem Mac mini → strukturierte Jobdaten, Projekt-PDF und Anlagen → iPad. Notion-Zugangsdaten gehören ausschließlich auf den Server.

Für diese Testversion existiert ein versioniertes Importformat (`PROJEKTPAKET.md`). Es ist ein lokaler Testvertrag, noch keine implementierte Notion-API. Bei einer neuen Revision werden Einsatzinformationen aktualisiert, aber vorhandene Berichte, Zeiten, Fotos und der bestehende Lieferschein nicht still ersetzt. Abgeschlossene Jobs werden nicht automatisch umgeschrieben.

## Speicherung und Grenzen

Browserdaten überstehen normales Schließen/Öffnen und Offline-Betrieb. Sie sind trotzdem kein verlässliches Langzeitarchiv: Website-Daten können gelöscht oder vom Betriebssystem entfernt werden. Regelmäßig vollständige Sicherungen und PDFs separat speichern. Verschiedene Geräte/Browser sehen unterschiedliche Daten. Ein Domainwechsel übernimmt bestehende lokale Daten nicht automatisch.

Die Original-PDF bleibt vollständig im Entwurf erhalten. Die für den Kunden zu übernehmenden Originalseiten werden gewählt; die bekannte dreiseitige LST-Vorlage wird erkannt und mit ihren ersten beiden Seiten vorgeschlagen. Die Option zur neuen Seitennummerierung überdeckt gezielt das untere rechte Nummernfeld. Bei fremden Vorlagen vorher prüfen oder deaktivieren. Der Inhalt anderer Bereiche wird nicht verändert.

Echter iPadOS-, Apple-Pencil-, Kamera- und Mail-Test steht noch aus. Benutzerrolle/Zugangsschutz, automatischer Abgleich, zentrale Speicherung, Konfliktbehandlung zwischen mehreren iPads und Rechnungsversand gehören in die nächste Serverausbaustufe.

## Versionspflege

Die aktuelle Version steht in `VERSION`, in der App und in `CHANGELOG.md`. Veröffentlichungen erhalten einen Tag wie `v0.3.0`. Programmänderungen werden als nachvollziehbare Git-Commits gespeichert. Kundendaten, Sicherungen, echte PDFs und Zugangsdaten gehören nie ins Repository.

Die frühere Entwicklung liegt separat unter https://github.com/andylueke-lst/LST-Baustellen-App- .

## Bibliotheken

PDF-Erstellung: pdf-lib (MIT). PDF-Vorschau: Mozilla PDF.js 5.6.205 (Apache-2.0) mit den zugehörigen Schriftlizenzen. Die Lizenzdateien werden mitgeliefert. Kein externes CDN wird zum Betrieb benötigt.

## Entwicklertest

`npm install`, danach `npx playwright install chromium` und `npm test`. Optional kann `BROWSER_PATH` auf einen vorhandenen Chrome zeigen. Der Test nutzt ausschließlich synthetische PDFs und einen lokalen Server. Testausgaben liegen im temporären Systemordner.
