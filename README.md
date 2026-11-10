# kids-python

Python-Aufgaben für Kinder von 10 bis 12 Jahren mit Scratch-Erfahrung.
Die Lektion dauert etwa eine Stunde.

## Struktur

| Pfad | Inhalt |
|---|---|
| `aufgaben/` | Dateien für die Kinder, zum Ergänzen |
| `aufgaben/SPICKZETTEL.txt` | Übersicht Scratch → Python und typische Fehler |
| `CHEAT-SHEET.pdf` | Spickzettel zum Ausdrucken, zwei A4-Seiten, beidseitig |
| `CHEAT-SHEET.md` | Derselbe Spickzettel als Markdown |
| `CHEAT-SHEET.html` | Quelle des PDF |
| `loesungen/` | Lösungen für die Leitung |

## Aufgaben

| Datei | Thema | Entsprechung in Scratch |
|---|---|---|
| `01_hallo.py` | `print` | «sage» |
| `02_rechnen.py` | Operatoren `+ - * /` | Operator-Blöcke |
| `03_variablen.py` | Variablen | «setze ... auf» |
| `04_fragen.py` | `input()`, `int()` | «frage ... und warte» |
| `05_entscheiden.py` | `if` / `else` | «falls ... dann ... sonst» |
| `06_quiz.py` | Quiz mit Punkten, Schlussaufgabe | Kombination der vorherigen Blöcke |
| `07_bonus_zahlenraten.py` | `random`, `while`; Bonus für schnelle Gruppen | «Zufallszahl», «wiederhole bis» |
| `08_fehlersuche.py` | Debugging: sechs absichtliche Fehler korrigieren | — |

## Vorbereitung der PCs

1. Installiere Python:
   ```
   winget install Python.Python.3.13
   ```
2. Öffne ein neues Terminal und prüfe die Installation mit `python --version` und `py --version`.
3. Installiere die Python-Erweiterung von Microsoft für VS Code:
   ```
   code --install-extension ms-python.python
   ```
4. Kopiere den Ordner `aufgaben/` auf den Desktop jedes PCs.
   Kopiere den Ordner `loesungen/` nicht.
5. Öffne in VS Code den Ordner `aufgaben/` mit «File → Open Folder…».
6. Öffne `01_hallo.py` und starte es mit dem Knopf ▶ oben rechts als Test.

## Programme starten in VS Code

- Der Knopf ▶ «Run Python File» oben rechts führt die Datei aus, die im Editor offen ist.
  Die Python-Erweiterung startet Python dafür direkt im Terminal, ohne Debugger.
- Alternativ startet der Befehl `py` ein Programm im Terminal:
  - Ist der Ordner `aufgaben/` geöffnet: `py 01_hallo.py`
  - Ist das ganze Projekt geöffnet: `py aufgaben\01_hallo.py`
  - `py` ist der Python Launcher, die Python-Installation enthält ihn.
  - Die Tab-Taste ergänzt den Dateinamen, zum Beispiel nach `py 01`.
- Das Programm läuft im Terminal unten, dort funktioniert auch `input()`.
- Ctrl+C im Terminal stoppt ein laufendes Programm.
- F5 startet den Debugger von VS Code.
  Der Projektordner enthält keine Debug-Konfiguration, deshalb fragt VS Code dann nach einem Debugger.
  Weise die Kinder auf den Knopf ▶ hin.

## Ablauf

| Minuten | Aktivität |
|---|---|
| 0–10 | Einführung: Was macht ein Entwickler? Vergleich Scratch → Python mit dem `SPICKZETTEL` |
| 10–50 | Aufgaben in Gruppen, im eigenen Tempo, von `01` bis `06` |
| 50–60 | Jede Gruppe lässt eine andere Gruppe ihr Quiz spielen |

## Hinweise für die Leitung

- Jede Gruppe soll mindestens `06_quiz.py` erreichen, weil die Schlusspräsentation diese Datei verwendet.
- Wird die Zeit knapp, überspringe `02_rechnen.py` und `03_variablen.py`.
  `04_fragen.py` führt Variablen nochmals ein.
- `07_bonus_zahlenraten.py` ist für Gruppen, die früher fertig sind.
- `08_fehlersuche.py` enthält sechs Fehler.
  Python meldet zuerst die vier Syntaxfehler, weil es die ganze Datei vor dem Ausführen liest.
  Danach meldet Python `NameError` und `TypeError`, wenn es die betroffenen Zeilen ausführt.
  Die Reihenfolge der Meldungen steht in `loesungen/08_fehlersuche.py`.
- Setze `08_fehlersuche.py` als Alternative zu `07_bonus_zahlenraten.py` ein, oder gemeinsam nach der Einführung, um die Fehlermeldungen zu zeigen.
- `int(input(...))` erzeugt einen `ValueError`, wenn jemand Text statt einer Zahl eingibt.
  Zeige den Fehler den Kindern: Eine Fehlermeldung lesen gehört zur Arbeit eines Entwicklers.
- `06_quiz.py` vergleicht Textantworten mit `.lower()`.
  Deshalb muss die erwartete Antwort im Code kleingeschrieben sein.

## Spickzettel ändern

`CHEAT-SHEET.html` ist die Quelle von `CHEAT-SHEET.pdf`.
`CHEAT-SHEET.md` enthält denselben Text und wird nicht automatisch angepasst.

1. Ändere `CHEAT-SHEET.html` und `CHEAT-SHEET.md`.
2. Erzeuge das PDF neu, im Projektordner unter Linux oder WSL mit Google Chrome:
   ```
   google-chrome --headless=new --no-pdf-header-footer --virtual-time-budget=15000 --print-to-pdf=CHEAT-SHEET.pdf CHEAT-SHEET.html
   ```
   Chrome braucht dafür Internet, weil die Schriften von Google Fonts kommen.
   Ohne Internet nimmt Chrome Ersatzschriften.
3. Öffne das PDF und prüfe, dass es genau zwei Seiten hat.
   Jede Seite ist fix A4 gross.
   Zu viel Inhalt überlappt die Fusszeile oder wird unten abgeschnitten, ohne Warnung.
