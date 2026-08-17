# Möbelübersicht bei GitHub Pages veröffentlichen

## Inhalt des Pakets

| Datei | Zweck |
|---|---|
| `index.html` | Die Seite. 8 Produkte, Suche, Kategoriefilter, Mengen, Summe, CSV, Mail-Export. |
| `robots.txt` | Hält Suchmaschinen fern. |
| `.nojekyll` | Sagt GitHub Pages, dass es die Dateien unverändert ausliefern soll. |
| `_headers` | Wird von GitHub **ignoriert** (nur Cloudflare versteht das). Kann bleiben oder weg. |

Die Seite lädt nichts von Google — keine Schriften, keine Skripte, kein Analytics.
Der einzige externe Aufruf sind die Produktbilder direkt von IKEA.

---

## Schritte

1. **Repository anlegen.** Auf GitHub → *New repository*. Name z. B. `moebeluebersicht`.
   Sichtbarkeit **Public** — bei kostenlosen Konten funktioniert GitHub Pages nur so.
2. **Dateien hochladen.** Im leeren Repository *uploading an existing file* wählen und
   die vier Dateien aus diesem Paket hineinziehen. Wichtig: die Dateien selbst,
   **nicht** den Ordner.
3. **Pages einschalten.** *Settings* → links *Pages* → unter *Build and deployment*
   Source auf **Deploy from a branch**, Branch **main**, Ordner **/ (root)** → *Save*.
4. **Warten.** Nach ein bis zwei Minuten steht dort „Your site is live at
   `https://<deinname>.github.io/moebeluebersicht/`".
5. **Prüfen.** Seite öffnen. Bilder müssen sichtbar sein, die Kategoriefilter müssen
   reagieren, und „Zur Wunschliste" muss unten die blaue Leiste einblenden.

---

## Aus 4juh verlinken

```html
<p>
  <a href="https://<deinname>.github.io/moebeluebersicht/" target="_blank" rel="noopener"
     style="display:inline-block;background:#DEFF00;border:3px solid #EB003C;
            color:#000548;font-size:16px;font-weight:bold;
            text-decoration:none;padding:12px 24px;">
    Bestellassistent öffnen
  </a>
</p>
```

Der gelbe Hintergrund ist Absicht: Die Haiilo-App überschreibt bei Links die Textfarbe
mit eurem Theme-Rot — auf rotem Grund wäre die Beschriftung unsichtbar.

---

## Aktualisieren

Datei im Repository anklicken → Stiftsymbol → ändern → *Commit changes*. Oder die
neue `index.html` per *Add file → Upload files* über die alte legen. Nach etwa einer
Minute ist die Änderung live.

## Wieder offline nehmen

*Settings* → *Pages* → neben „Your site is live at" das Menü → **Unpublish site**.
Achtung: Die Dateien bleiben im öffentlichen Repository lesbar. Sollen auch die weg,
Repository auf *Private* stellen oder löschen.

---

## Zur Kenntnis

**Empfängeradresse:** `pr.bergstrasse-pfalz@johanniter.de` ist eingetragen. Sie steht
in der `index.html` an genau einer Stelle — als Vorbelegung des Feldes „Empfänger der
Anfrage" im Wunschlisten-Dialog. Wer bestellt, kann sie dort im Einzelfall überschreiben.

**Spam:** Da das Repository öffentlich ist, ist die Adresse maschinell auslesbar.
Falls dort irgendwann Werbemüll ankommt, liegt es daran — dann lohnt sich ein Blick
in den Spamfilter des Postfachs.

---

## Wenn etwas nicht klappt

| Symptom | Ursache | Lösung |
|---|---|---|
| 404 statt Seite | Dateien liegen in einem Unterordner | Inhalt hochladen, nicht den Ordner |
| Seite lädt, aber ohne Gestaltung | `index.html` unvollständig übertragen | Datei erneut hochladen |
| Produktbilder fehlen | IKEA-Bild-URL veraltet | Auf der Produktseite Bildadresse neu kopieren |
| „Als E-Mail senden" tut nichts | kein Standard-Mailprogramm gesetzt | „Liste kopieren" nutzen |
