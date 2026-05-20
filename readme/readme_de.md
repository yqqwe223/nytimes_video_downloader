# 🗽 NYTimes Video-Analyse-Tool

> Ein leichtes, schnelles und vielseitiges Werkzeug zum Extrahieren von Videoinhalten von The New York Times (Lern- & Forschungsversion)

[🌐 Online-Demo](https://twittervideodownloaderx.com/nytimes_downloader_ge) • [📝 Bedienungsanleitung](#-bedienungsanleitung) • [❓ Häufig gestellte Fragen](#-häufig-gestellte-fragen)

---

## 📋 Projektübersicht

Dieses Projekt ist ein webbasiertes Video-Analyse-Tool, das darauf ausgelegt ist, Metadaten von Medienressourcen aus öffentlich zugänglichen Artikeln auf der Website von The New York Times sicher zu extrahieren und Optionen für Formatkonvertierung sowie lokales Speichern bereitzustellen. Keine Installation von Client-Software oder Konto-Registrierung erforderlich – nutzen Sie das Tool direkt über Ihren Browser.

> ⚠️ **Wichtiger Hinweis**: Dieses Tool dient ausschließlich persönlichen Lernzwecken, technischer Forschung und der Nutzung im Rahmen einer angemessenen Verwendung. Bitte halten Sie sich an die [NYTimes Nutzungsbedingungen](https://www.nytimes.com/content/help/rights/sale/terms-of-service.html), das 《US-Urheberrechtsgesetz》 sowie andere geltende Vorschriften. Respektieren Sie die Arbeit von Nachrichtenorganisationen und Kreativschaffenden; verwenden Sie heruntergeladene Inhalte nicht für kommerzielle Zwecke oder zur Verletzung von Rechten Dritter. **Dieses Tool unterstützt ausschließlich öffentlich zugängliche Videoinhalte und umgeht keine Paywalls, Abonnement-Beschränkungen oder login-pflichtige Inhalte.**

---

## ✨ Hauptfunktionen

- 🔗 **Link-Analyse**: Unterstützt standardmäßige NYTimes-Artikel/Video-URLs; automatische Erkennung öffentlich verfügbarer Videoressourcen
- 📥 **Export in mehreren Formaten**:
  - Öffentliche Video-Streams (unterstützt öffentlich verfügbare Auflösungs-Optionen der Plattform)
  - Audio-Extraktion → MP3-Format (praktisch für das Offline-Hören von Nachrichtenberichten/Podcasts)
  - Videoclip → Konvertierung zu animiertem GIF (ideal für Lehrmaterialien/Inhaltszusammenfassungen)
- 🌍 **Mehrsprachige Oberfläche**: Unterstützung für Deutsch, Englisch, Chinesisch, Japanisch, Koreanisch und weitere Sprachen
- 📱 **Plattformübergreifende Kompatibilität**: Funktioniert einwandfrei auf Chrome / Firefox / Safari / Edge; optimierte Erfahrung für Mobilgeräte und Tablets
- 🔒 **Datenschutz priorisiert**: Keine NYTimes-Konto-Anmeldung erforderlich, keine Erfassung personenbezogener Daten; Analyseprozess vollständig anonym
- ⚡ **Schnelle Verarbeitung**: Analyse im Durchschnitt in 5-10 Sekunden abgeschlossen; Unterstützung für parallele Anfragen

---

## 🚀 Schnellstart

### Online-Nutzung (empfohlen)
1. Besuchen Sie [https://twittervideodownloaderx.com/nytimes_downloader_ge](https://twittervideodownloaderx.com/nytimes_downloader_ge)
2. Kopieren Sie den Link der Ziel-Video-Seite (Beispiel: `https://www.nytimes.com//01/01/world/example-video.html`)
3. Fügen Sie den Link in das Eingabefeld ein → Klicken Sie auf die Schaltfläche 「Analysieren」
4. Wählen Sie das gewünschte Format → Speichern Sie die Datei gemäß den Anweisungen Ihres Browsers

### Lokale Bereitstellung (für Entwickler)
```bash
# Repository klonen
git clone https://github.com/your-repo/nytimes-video-parser.git

# Abhängigkeiten installieren
cd nytimes-video-parser && npm install

# Umgebungsvariablen konfigurieren (optional)
cp .env.example .env

# Entwicklungsserver starten
npm run dev
```

> 💡 Hinweis: Dieses Projekt verwendet eine Architektur basierend auf Node.js + Express. Detaillierte Bereitstellungsinformationen finden Sie in `/docs/DEPLOY.md`

---

## 🛠 Technologie-Stack

| Modul | Eingesetzte Technologien |
|-------|--------------------------|
| Frontend | Vue 3 + TypeScript + Vite |
| Backend | Node.js + Express + Axios |
| Videoverarbeitung | ffmpeg.wasm (leichtgewichtige Client-seitige Konvertierung) |
| Proxy-Weiterleitung | Cloudflare Workers / Benutzerdefinierte Middleware |
| Internationalisierung | vue-i18n + JSON-Sprachpakete |

---

## 📚 Bedienungsanleitung

### Grundlegender Arbeitsablauf
```
1. Video-Link erhalten
   └─ Öffnen Sie den Ziel-Artikel/die Ziel-Video-Seite auf NYTimes → Kopieren Sie die URL aus der Adressleiste des Browsers

2. Analyse-Anfrage senden
   └─ Fügen Sie den Link in das Eingabefeld des Tools ein → Klicken Sie auf 「Analyse starten」

3. Ausgabe-Konfiguration auswählen
   ├─ 🎬 Video herunterladen: Verfügbare Auflösung wählen (nur öffentliche Inhalte)
   ├─ 🎵 Audio extrahieren: MP3-Datei generieren (ideal für Offline-Hören von Nachrichten/Podcasts)
   └─ 🎞 GIF generieren: Animation aus angegebenem Zeitbereich erstellen (empfohlen: ≤15 Sekunden)

4. Datei speichern
   └─ Die Ressource wird in einem neuen Tab geöffnet → Rechtsklick/Menü → 「Speichern unter」
```

### Tipps für die Nutzung auf Mobilgeräten
- iOS Safari: Schaltfläche „Teilen" → 「In Dateien speichern」
- Android Chrome: Video-Vorschau lange drücken → 「Video herunterladen」
- Bei automatischer Wiedergabe: Klicken Sie auf `⋮` oben rechts im Player → Wählen Sie 「Herunterladen」

---

## ❓ Häufig gestellte Fragen

**F: Wo werden heruntergeladene Dateien gespeichert?**  
A: Dateien werden im im Browser konfigurierten Download-Ordner gespeichert. Sie können diesen Pfad in den Browsereinstellungen überprüfen oder ändern.

**F: Kann ich Inhalte hinter Paywalls, für Abonnenten oder login-pflichtige Inhalte analysieren?**  
A: Nein. Dieses Tool funktioniert nur mit öffentlich zugänglichen Videoinhalten und respektiert die Zugriffseinstellungen des Originalinhalts. Inhalte hinter Paywalls, Abonnement-Beschränkungen oder die eine Anmeldung erfordern, werden nicht unterstützt.

**F: Wird die Bild-/Tonqualität nach der Konvertierung reduziert?**  
A: Video-Downloads behalten die originale Bitrate der ausgewählten Auflösung bei. Das MP3-Format verwendet eine Standardkodierung mit 128 kbps. Das GIF-Format optimiert die Bildrate entsprechend der Dauer, um ein Gleichgewicht zwischen Dateigröße und Flüssigkeit zu erreichen.

**F: Wird der Download-Verlauf oder Cache gespeichert?**  
A: Nein. Alle Ressourcen werden direkt über einen temporären Proxy an das Gerät des Nutzers übertragen; der Server speichert keine Anfragen oder Mediendateien.

**F: Was tun, wenn die Analyse fehlschlägt?**  
A: Bitte überprüfen Sie: ① Ob der Link zu einer gültigen öffentlichen Video-Seite führt ② Ob Ihre Internetverbindung stabil ist ③ Versuchen Sie es mit einem anderen Browser. Bei fortbestehenden Problemen melden Sie dies bitte über ein Issue.

---

## ⚖️ Einhaltung von Vorschriften und Haftungsausschluss

- Dieses Tool **umgeht oder verletzt keine technischen Schutzmaßnahmen, Paywalls oder Zugriffskontrollen** der Plattform; es ruft lediglich Metadaten über öffentlich verfügbare Schnittstellen ab
- Der Nutzer ist selbst dafür verantwortlich, sicherzustellen, dass seine Nutzung den örtlichen Gesetzen und den Nutzungsbedingungen der Plattform entspricht
- Empfohlene Anwendungsfälle: Persönliche Lernarchivierung, Nachrichten-Recherche, Vorbereitung von Lehrmaterialien... stets im Rahmen der zulässigen Nutzung (Fair Use)
- Wenn Sie Inhalte entdecken, die möglicherweise Rechte verletzen, oder Fragen zum Urheberrecht haben, wenden Sie sich bitte über die [NYTimes Urheberrechts-Kontaktseite](https://www.nytimes.com/content/help/rights/copyright/copyright-contact.html) an den offiziellen Kanal
- Dieses Tool steht in keiner Zugehörigkeits-, Unterstützungs- oder Genehmigungsbeziehung zu The New York Times Company. Alle Marken und Inhalts-Urheberrechte gehören ihren jeweiligen Inhabern

---

## 🤝 Leitfaden für Beiträge

Wir freuen uns über Ihre Pull Requests und Issue-Meldungen! Vor dem Beitragen bitten wir Sie, Folgendes zu lesen:
- [Code-Standards](/CONTRIBUTING.md)
- [Mehrsprachiger Übersetzungsleitfaden](/locales/README.md)
- [Sicherheits- und Compliance-Anforderungen](/SECURITY.md)

---

## 📄 Lizenz

Dieses Projekt wird unter der [MIT-Lizenz](/LICENSE) veröffentlicht. Es kann kostenlos für Bildungs- und Forschungszwecke genutzt werden. Bei kommerzieller Nutzung prüfen Sie bitte sorgfältig die Einhaltung der geltenden rechtlichen Vorschriften.

---

> 🌟 Wenn Ihnen dieses Tool hilfreich war, würden wir uns sehr über ✨einen Stern (Star) freuen! Ihre Unterstützung ist die größte Motivation für uns, dieses Projekt weiterhin zu pflegen und zu verbessern~

*Zuletzt aktualisiert: Mai  | Version: v1.0.0*