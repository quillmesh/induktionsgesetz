# Induktionsgesetz – Simulation

Interaktive 3D-Simulation zur **Induktion durch Bewegen eines Leiters** (Generatorprinzip).

Ein Kupferstab bewegt sich sinusförmig hin und her durch das homogene Magnetfeld zwischen Nord- und Südpol. Die induzierte Spannung

    u_i(t) = N · B · ℓ · v(t),   v(t) = v̂ · sin(ω·t)   →   u_i(t) = û · sin(ω·t)

wird als Zahl, auf einem Messgerät in der 3D-Ansicht und als Plot über der Zeit angezeigt.

## Bedienung

- **B** (magnetische Flussdichte), **v̂** (Spitzengeschwindigkeit) und **T** (Periodendauer) über die Schieberegler oder per Klick auf Magnet bzw. Leiter einstellen.
- **Advanced** blendet zusätzlich **N** (Windungszahl) und **ℓ** (wirksame Leiterlänge) ein.
- 3D-Ansicht: ziehen = drehen, rechte Maustaste / zwei Finger = verschieben, Mausrad = zoomen, Doppelklick = Ansicht zurücksetzen.
- Pause/Start, Zeit zurücksetzen, Dark/Light.

## Aufbau

```
index.html            Seite mit HTML, CSS und JavaScript (Plot, Gleichungen, 3D-Szene)
lib/                  Three.js r160 (lokal, keine CDN-Abhängigkeit)
  three.module.min.js
  addons/controls/OrbitControls.js
  addons/geometries/RoundedBoxGeometry.js
  addons/environments/RoomEnvironment.js
  addons/renderers/CSS2DRenderer.js
  LICENSE             MIT-Lizenz von Three.js
```

Die Dateien in `lib/` stammen unverändert aus dem offiziellen Three.js-Repository, Tag `r160` (Version 0.160.0). Gesamtgrösse ca. 0.7 MB.

## Abweichung von der Design-Spezifikation

Design, Farben (Solarized), Typografie und Bedienkonzept folgen `DESIGN.md` der Elektrotechnik-Simulationen (Kirchhoff, Spannungsteiler). Einzige Ausnahme: Für die 3D-Ansicht wird **Three.js** verwendet. Die Bibliothek liegt lokal im Repo, die Seite braucht also keine Internetverbindung.

Plot und Gleichungen kommen ohne Bibliothek aus. Lädt die 3D-Ansicht nicht (z.B. kein WebGL), erscheint eine Meldung und Plot und Gleichungen funktionieren weiter.

## Lokal starten

Die 3D-Ansicht nutzt JavaScript-Module. Diese laden Browser nicht über `file://`. Deshalb lokal einen kleinen Webserver starten:

```
python3 -m http.server
```

und `http://localhost:8000` öffnen. Auf GitHub Pages funktioniert die Seite direkt.

## Hosting

GitHub Pages: Branch `main`, Ordner `/ (root)`.
