# FontFixer

[English](../README.md) | [中文](README_zh.md) | [Español](README_es.md) | Deutsch | [日本語](README_ja.md) | [Français](README_fr.md)

Eine schlanke Browser-Erweiterung, die Webseiten-Schriften für komfortables Lesen optimiert. Schriftart, Größe und Textfarben mit einem Klick ändern.

> Chromium-basiert · Manifest V3 · Minimale Berechtigungen · Kein Tracking

---

## Warum FontFixer?

Viele Websites verwenden kleine, unscharfe oder schwer lesbare Schriften. FontFixer lässt dich Webseiten-Schriften mit deiner bevorzugten Schriftart anpassen, die Schriftgröße einstellen und Text-/Linkfarben anpassen — alles in Echtzeit, ohne Seiten-Neuladen.

| Vorteil | Details |
|---------|---------|
| 🔤 **Lokale Schriften** | Liest auf deinem Gerät installierte Schriften über die `queryLocalFonts` API |
| ⚡ **Echtzeit-Vorschau** | Alle Änderungen werden sofort beim Anpassen angewendet — kein Seiten-Neuladen |
| 💾 **Speicher pro Seite** | Speichert verschiedene Schrifteinstellungen für verschiedene Websites |
| ⚙️ **Auto-Anwenden** | Gespeicherte Einstellungen werden bei jedem Besuch einer konfigurierten Seite automatisch wieder angewendet |
| 🔒 **Berechtigungen** | `storage` + `scripting` + `activeTab`; `<all_urls>` Host-Zugriff nur zum Injizieren von Schriften auf konfigurierten Seiten |

---

## Funktionen

### 🆓 Kostenlos

| Funktion | Beschreibung |
|----------|--------------|
| 🔤 **Schriftauswahl** | Wähle aus 3 eingebauten Schriften (Noto Sans, Source Han Sans, Arial) oder jeder auf deinem Gerät installierten Schrift |
| 📏 **Schriftgröße skalieren** | Von 80% bis 160% per Schieberegler einstellen |
| 🎨 **Textfarbe** | Benutzerdefinierte Textfarbe mit Farbwähler |
| 🔗 **Linkfarbe** | Separate Linkfarbe für bessere Lesbarkeit |
| 🔄 **Auto-Anwenden** | Einstellungen werden bei jedem Besuch einer konfigurierten Seite automatisch wieder angewendet |
| 💾 **Auto-Speichern** | Einstellungen werden automatisch pro Seite gespeichert (bis zu 5 Seiten) |
| ↺ **Ein-Klick-Reset** | Ursprüngliche Seiten-Schriften sofort wiederherstellen |
| 🌍 **6 Sprachen** | Englisch, Chinesisch, Japanisch, Spanisch, Deutsch, Französisch |

### ⭐ Pro (Lizenz erforderlich)

| Funktion | Beschreibung |
|----------|--------------|
| ♾️ **Unbegrenzte Konfigurationen** | Schrifteinstellungen für unbegrenzt viele Websites speichern |
| 📤 **Import / Export** | Schriftkonfigurationen zwischen Geräten sichern und wiederherstellen |

---

## Vorschau

<p align="center">
  <img src="icons/icon128.png" alt="FontFixer Symbol" width="80">
</p>

---

## Unterstützte Browser

| Browser | Status |
|---------|--------|
| Google Chrome | ✅ Vollständig unterstützt |
| Microsoft Edge | ✅ Vollständig unterstützt |
| Andere Chromium-basierte Browser | ✅ Sollte funktionieren |

---

## Installation

1. Öffne die Erweiterungsseite deines Browsers:
   - **Chrome**: `chrome://extensions/`
   - **Edge**: `edge://extensions/`
2. Aktiviere den **Entwicklermodus** (Schalter oben rechts)
3. Klicke auf **Entpackte Erweiterung laden** und wähle den Ordner `font-fixer`
4. Klicke auf das 🔤 FontFixer-Symbol in deiner Toolbar zum Starten

---

## Verwendung

### Schriften ändern

1. Klicke auf das FontFixer-Symbol in deiner Toolbar
2. Wähle eine Schrift aus dem Dropdown — 3 eingebaute Schriften sind immer verfügbar; klicke auf **🔄**, um auf deinem Gerät installierte Schriften zu laden
3. Schriftgröße mit dem Schieberegler anpassen (80%–160%)
4. Optional **Textfarbe** / **Linkfarbe** ankreuzen, um Farben zu überschreiben (aus = Seitenfarben nie anfassen)
5. Klicke auf **Anwenden & Speichern** — Einstellungen werden sofort angewommen und für diese Seite gespeichert

### Auto-Anwenden

- Schalte den **Auto-Anwenden**-Schalter ein, um die gespeicherten Einstellungen dieser Seite bei jedem Besuch automatisch wieder anzuwenden
- Bei deaktiviertem Auto-Anwenden greifen Einstellungen nur, wenn du das Popup öffnest und auf **Anwenden & Speichern** klickst

### Zurücksetzen

- Klicke auf **Zurücksetzen**, um die Einstellungen der aktuellen Seite zu entfernen und die ursprünglichen Schriften wiederherzustellen

---

## So funktioniert es

```
Schrift auswählen & Einstellungen anpassen
       ↓
Auf Anwenden & Speichern klicken
       ↓
CSS wird via chrome.scripting.insertCSS injiziert
       ↓
Seitenschriften ändern sich sofort
       ↓
Einstellungen in chrome.storage.local gespeichert
       ↓
(Auto-Anwenden an) wird beim nächsten Besuch automatisch wieder angewendet
```

Alle Style-Verarbeitung passiert lokal in deinem Browser. Die einzige Netzwerkanfrage ist **optional** — bei Aktivierung eines Pro-Lizenzschlüssels kontaktiert FontFixer den Lizenzserver mit deinem Schlüssel und grundlegenden Browser-Metadaten (Browser, Sprache, Zeitzone). Es werden nie Webseiteninhalte gelesen oder hochgeladen.

**Hinweis zum lokalen Schriftzugriff:** Lokale Schriften verwenden die Local Font Access API — keine Manifest-Berechtigung nötig. Chrome zeigt eine Berechtigungsabfrage zur Laufzeit an, und die API läuft nur bei einem Nutzerklick, also öffne das Popup und klicke auf den **🔄 Aktualisieren-Button**, um deine lokalen Schriften zu laden. Es werden nur Schriftnamen gelesen — Quelldateien werden nicht extrahiert, kopiert oder hochgeladen. Du kannst die Berechtigung jederzeit in den Browsereinstellungen widerrufen.

**Auto-Anwenden-Regel:** Automatische Style-Injektion erfolgt pro Seite. Schalte den **Auto-Anwenden**-Schalter im Popup ein, um die Einstellungen dieser Seite bei jedem Besuch wieder anzuwenden; bei deaktiviert greifen Einstellungen nur bei Klick auf **Anwenden & Speichern**.

---

## Schrift-Urheberrechtshinweis

Drei eingebaute Schriften (Noto Sans, Source Han Sans, Arial) werden unter der SIL Open Font License vertrieben, die persönliche und kommerzielle Nutzung ohne zusätzliche Genehmigung erlaubt.

Die Erweiterung liest nur die Namensliste der auf deinem lokalen Gerät installierten Schriften über die Browser-Standard-API und wird keine lokalen Schriftdateien extrahieren, kopieren oder hochladen. Alle Rechte der Systemschriften gehören deren jeweiligen Rechteinhabern.

---

## Datenschutz

- `storage` — Speichert deine Schrifteinstellungen lokal. Es werden keine Webseiteninhalte gespeichert.
- `scripting` — Injiziert CSS zur Änderung der Seitenschriften. Liest keinen Seitentext oder Daten.
- `activeTab` — Greift nur auf den aktuellen Tab zu, wenn du mit der Erweiterung interagierst.
- `<all_urls>` — Ermöglicht der Erweiterung, gespeicherte Schrift-Styles automatisch auf konfigurierten Seiten wieder anzuwenden. Es werden nie Seiteninhalte gelesen oder hochgeladen.
- **Lokaler Schriftzugriff** — Keine Manifest-Berechtigung; Zugriff wird zur Laufzeit über eine Browser-Abfrage gewährt. Liest nur Anzeigenamen, nie Schriftdateien. Kann jederzeit widerrufen werden.
- Kein Tracking, keine Analytik. Die einzige Netzwerkanfrage ist die Lizenzaktivierung/-validierung bei Verwendung eines Pro-Lizenzschlüssels.

---

## Urheberrechtshinweis

Diese Erweiterung passt nur lokal die visuelle Darstellung von Webseiten für ein komfortables Leseerlebnis an. Alle Text-, Bild- und Inhaltsrechte der Website gehören dem jeweiligen Herausgeber. Das Ändern von Seitenanzeige-Styles gewährt Nutzern keine Urheberrechtslizenz an Website-Inhalten. Nutzer haben beim Browsen von Webseiten die lokalen Gesetze zum geistigen Eigentum einzuhalten.

---

## Lizenz

Copyright © 2026 FontFixer. Alle Rechte vorbehalten.

---

## ❤️ Support

Wenn dir FontFixer hilft, unterstütze das Projekt gerne!

**[👉 Lizenzschlüssel erhalten](https://www.annmax1983.com/checkout.html?plugin=fontfixer)**

---

> **Hinweis:** Dieses Repository dient ausschließlich der **Projektpräsentation**. Es enthält nicht den vollständigen Quellcode, das Manifest, Icons oder Build-Skripte. Der vollständige Quellcode wird hier **nicht** veröffentlicht.
