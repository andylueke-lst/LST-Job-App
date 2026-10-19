# Testvertrag für Projektpakete · Schema 1

Dies ist die vorbereitete Datenschnittstelle für den späteren Dienst auf dem Mac mini. Der Notion-API-Client und ein Server sind noch nicht implementiert. Für die Tests kann eine JSON-Datei unter „Vorbereitung“ importiert werden.

```json
{
  "kind": "lst-project",
  "schemaVersion": 1,
  "released": true,
  "externalId": "eindeutige-notion-seitenkennung",
  "revision": 1,
  "title": "Jobbezeichnung",
  "deliveryNumber": "LS260067",
  "fields": {
    "client": "Auftraggeber / Rechnungsempfänger",
    "siteName": "Betrieb vor Ort",
    "location": "Einsatzadresse",
    "contact": "Ansprechpartner vor Ort",
    "phone": "Telefonnummer",
    "tasks": "Arbeitsanweisung",
    "packing": "Packliste",
    "conditions": "Besonderheiten und ausdrücklich offene Punkte"
  },
  "sourcePdf": {
    "name": "Lieferschein.pdf",
    "data": "BASE64_DER_ORIGINAL_PDF",
    "originalPages": 2,
    "renumberOriginal": true
  }
}
```

`sourcePdf` ist für den Import optional; ohne Anlage muss der Lieferschein vor dem Abschluss separat eingelesen werden. Alle Werte in `fields` sind Texte. `released` muss wahr sein, `revision` eine positive ganze Zahl. Gleiche externe Kennung und höhere Revision aktualisieren Einsatzinformationen desselben offenen Jobs. Tagesberichte und Protokolle bleiben erhalten. Der aktuelle Lieferschein wird bei einer Aktualisierung nicht still ersetzt. Gleiche/ältere Revisionen und Updates abgeschlossener Jobs werden abgewiesen.

Leere Felder werden in der App als offen gezeigt. Der spätere Server muss davor die in Notion festgelegten Pflichtfelder und Freigaben prüfen, Anlagen herunterladen und erst ein vollständiges Paket veröffentlichen. Die aktuelle Testversion erzwingt diese noch nicht mit einer Notion-Feldkonfiguration.

## Interne Büroakte

`kind: office-job` ist eine historische JSON-Fassung eines einzelnen abgeschlossenen Jobs: Tagesberichte, Original-PDF, Unterschrift, zugeordnete Mitarbeiter-/Kompressor-/Tankprotokolle und Fotos. Die unterschriebene Lieferschein-PDF wird zusätzlich als eigenständiger Anhang übergeben. Die interne Akte ist nicht für den Unterzeichner bestimmt und kein Importpaket für neue Projekte.

## Vollständige Sicherung

`kind: full-backup`, `schemaVersion: 2` enthält alle lokalen Datensammlungen: drafts, archives, photos, shifts, assignments, meters, fuels und settings. Die Wiederherstellung ergänzt Datensätze atomar. Abweichende vorhandene IDs führen zum Abbruch statt zum Überschreiben. Alte Sicherungen mit drafts/archives aus 0.1/0.2 werden ebenfalls gelesen.
