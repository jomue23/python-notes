# 00_Zusammenfassung: Python-Grundlagen für Anfänger

Diese Zusammenfassung basiert auf den bereitgestellten Dokumenten und führt dich schrittweise in die Grundlagen der Programmierung mit Python ein. Sie deckt die grundlegenden Konzepte, die Arbeit mit Listen sowie die Verwendung von Funktionen und Paketen ab und schließt mit einer Einführung in die leistungsstarke NumPy-Bibliothek.

---

## 1. Die Grundlagen (Kapitel 1)

### Python als Taschenrechner

Python kann direkt für grundlegende arithmetische Berechnungen verwendet werden. Du kannst Addition (`+`), Subtraktion (`-`), Multiplikation (`*`) und Division (`/`) durchführen. Die Funktion `print()` wird verwendet, um das Ergebnis auszugeben.

```python
# Addition und Subtraktion
print(4 + 5)
print(5 - 5)

# Multiplikation und Division
print(3 * 5)
print(10 / 2)
```

### Variablen und Datentypen

Um Werte zu speichern und später wiederzuverwenden, nutzt man **Variablen**. Dies ist ein zentrales Konzept in der Programmierung.

```python
# Speichern von Werten in Variablen
height = 1.79
weight = 68.7

# Berechnung des BMI mit den Variablen
bmi = weight / height ** 2
print(bmi)
```

Jede Variable hat einen **Datentyp**. Die wichtigsten grundlegenden Typen sind:
* **`int`**: Ganze Zahlen (z.B. `5`).
* **`float`**: Gleitkommazahlen, also Zahlen mit Nachkommastellen (z.B. `21.44`).
* **`str`**: Zeichenketten (Strings), also Text (z.B. `"Hallo Welt"`).
* **`bool`**: Boolesche Werte, die nur `True` (wahr) oder `False` (falsch) sein können.

Mit der Funktion `type()` kannst du den Datentyp einer Variable überprüfen.

```python
# Verschiedene Datentypen
day_of_week = 5
print(type(day_of_week))  # Gibt <class 'int'> aus

message = "Hallo Welt"
print(type(message))      # Gibt <class 'str'> aus

is_beginner = True
print(type(is_beginner))  # Gibt <class 'bool'> aus
```

---

## 2. Python-Listen (Kapitel 2)

### Listen: Sammlungen von Daten

Oft möchte man nicht nur einzelne Werte, sondern eine ganze Sammlung von Werten speichern. Dafür gibt es in Python **Listen**. [cite_start]Eine Liste wird mit eckigen Klammern `[]` erstellt und kann verschiedene Datentypen enthalten[cite: 1017].

```python
# Eine Liste mit den Körpergrößen der Familie
fam_heights = [1.73, 1.68, 1.71, 1.89]

# Eine Liste kann auch verschiedene Datentypen mischen
fam_data = ["liz", 1.73, "emma", 1.68, "mom", 1.71, "dad", 1.89]
print(fam_data)
```

### Auf Listenelemente zugreifen und sie bearbeiten

Du kannst auf einzelne Elemente einer Liste über ihren **Index** zugreifen. **Wichtig:** Die Zählung beginnt bei `0`!

* `fam_data[0]` greift auf das erste Element zu.
* `fam_data[-1]` greift auf das letzte Element zu.

Mit **Slicing** kannst du einen Teilbereich der Liste auswählen. `liste[start:ende]` wählt die Elemente vom `start`-Index bis zum `ende`-Index aus (wobei der `ende`-Index selbst nicht mehr enthalten ist).

```python
# Indexing (Zugriff auf ein Element)
print(fam_data[0])   # Gibt 'liz' aus
print(fam_data[-1])  # Gibt das letzte Element aus: 1.89

# Slicing (Zugriff auf einen Bereich)
# Gibt die Elemente von Index 1 bis (aber nicht einschließlich) 4 aus
print(fam_data[1:4]) # Gibt [1.73, 'emma', 1.68] aus
```

[cite_start]Du kannst Listenelemente auch verändern, hinzufügen oder löschen[cite: 1018].

```python
# Element ändern
fam_data[0] = "lisa"
print(fam_data)

# Elemente hinzufügen (erstellt eine neue Liste)
fam_extended = fam_data + ["me", 1.79]
print(fam_extended)

# Element löschen
del(fam_data[2]) # Löscht 'emma' an Index 2
print(fam_data)
```

**Achtung bei Kopien:** Wenn du eine Liste mit `y = x` einer neuen Variable zuweist, erstellst du keine Kopie. Beide Variablen zeigen auf dieselbe Liste im Speicher. Eine echte Kopie erstellst du mit `y = list(x)` oder `y = x[:]`.

```python
# Um eine echte Kopie zu erstellen:
x = ["a", "b", "c"]
y = list(x) # oder y = x[:]
y[1] = "z"

print(x) # x bleibt unverändert. Gibt ['a', 'b', 'c'] aus
print(y) # y wurde geändert. Gibt ['a', 'z', 'c'] aus
```

---

## 3. Funktionen, Methoden und Pakete (Kapitel 3)

### Funktionen: Wiederverwendbarer Code

**Funktionen** sind wiederverwendbare Code-Blöcke, die eine bestimmte Aufgabe erledigen. Du hast bereits `print()` und `type()` kennengelernt. Weitere nützliche eingebaute Funktionen sind:
* `max()`: Findet den größten Wert in einer Liste.
* `round()`: Rundet eine Zahl. Kann ein zweites Argument für die Anzahl der Nachkommastellen annehmen.
* `help()`: Zeigt die Dokumentation zu einer Funktion an.

```python
fam_heights = [1.73, 1.68, 1.71, 1.89]

# max() findet den größten Wert
print(max(fam_heights))

# round() rundet eine Zahl
print(round(1.68, 1)) # Rundet auf eine Nachkommastelle -> 1.7
print(round(1.68))    # Rundet zur nächsten ganzen Zahl -> 2

# Hilfe zu einer Funktion erhalten
help(round)
```

### Methoden: Funktionen, die zu Objekten gehören

**Methoden** sind spezielle Funktionen, die zu einem bestimmten Datentyp (Objekt) gehören. Man ruft sie mit der "Punkt-Notation" auf: `objekt.methode()`.

Jeder Datentyp hat seine eigenen Methoden. Zum Beispiel haben Strings andere Methoden als Listen.

```python
# String-Methoden
sister = "liz"
print(sister.capitalize()) # Macht den ersten Buchstaben groß -> 'Liz'
print(sister.replace("z", "sa")) # Ersetzt Zeichen -> 'lisa'

# Listen-Methoden
fam_data = ["liz", 1.73, "emma", 1.68]
print(fam_data.index("emma")) # Findet den Index eines Elements -> 2
fam_data.append("me") # Fügt ein Element am Ende hinzu
print(fam_data)
```

### Pakete (Packages): Python erweitern

Niemand kann alle denkbaren Funktionen von Anfang an in Python einbauen. Deshalb gibt es **Pakete** (auch Bibliotheken genannt), die zusätzliche Funktionalitäten für spezielle Bereiche wie Datenwissenschaft, Webentwicklung oder Grafik bereitstellen.

Bekannte Pakete für die Datenanalyse sind **NumPy**, **Matplotlib** und **scikit-learn**.

Um ein Paket zu verwenden, musst du es zuerst **importieren**. Der gängigste und beste Weg ist, dem Paket beim Import einen kurzen Alias (Spitznamen) zu geben.

```python
# Der beste Weg, ein Paket zu importieren
import numpy as np

# Eine Liste in ein spezielles NumPy-Array umwandeln
np_fam = np.array([1.73, 1.68, 1.71, 1.89])

print(np_fam)
print(type(np_fam))
```

---

## 4. NumPy: Numerisches Rechnen in Python (Kapitel 4)

[cite_start]Während Python-Listen sehr flexibel sind, stoßen sie an ihre Grenzen, wenn man mathematische Operationen auf ganze Daten-Sammlungen anwenden möchte[cite: 1020]. [cite_start]Genau hier setzt **NumPy** (Numeric Python) an[cite: 1034].

### Der NumPy-Array: Schnell und Effizient

Die zentrale Datenstruktur in NumPy ist der **Array**. [cite_start]Er ist eine Alternative zur Python-Liste und ermöglicht sehr schnelle Berechnungen über ganze Arrays hinweg[cite: 1035, 1036, 1037].

Das folgende Beispiel zeigt, warum das so wichtig ist: Die Berechnung des BMI für alle Personen gleichzeitig ist mit Listen nicht möglich, mit NumPy-Arrays aber schon.

```python
import numpy as np

height = [1.73, 1.68, 1.71, 1.89, 1.79]
weight = [65.4, 59.2, 63.6, 88.4, 68.7]

# [cite_start]Mit Listen führt das zu einem Fehler (TypeError) [cite: 1029, 1057]
# bmi = weight / height ** 2

# [cite_start]Mit NumPy funktioniert es problemlos [cite: 1050]
np_height = np.array(height)
np_weight = np.array(weight)
bmi = np_weight / np_height ** 2
print(bmi)
```

### Wichtige Unterschiede zur Python-Liste

* [cite_start]**Nur ein Datentyp**: Ein NumPy-Array kann im Gegensatz zu einer Liste nur Elemente des gleichen Datentyps enthalten[cite: 1067]. [cite_start]Wenn du versuchst, Typen zu mischen, wandelt NumPy alle Elemente in einen gemeinsamen Typ um (meistens String)[cite: 1065, 1066]. [cite_start]Diese Einschränkung ist der Grund für die hohe Geschwindigkeit von NumPy[cite: 1196].
* [cite_start]**Mathematisches Verhalten**: Der `+`-Operator addiert bei NumPy-Arrays die Elemente an der jeweiligen Position, während er bei Listen die beiden Listen aneinander hängt[cite: 1073, 1075].

```python
python_list = [1, 2, 3]
numpy_array = np.array([1, 2, 3])

[cite_start]print(python_list + python_list)     # Ergibt [1, 2, 3, 1, 2, 3] [cite: 1073]
[cite_start]print(numpy_array + numpy_array) # Ergibt [2, 4, 6] [cite: 1075]
```

### Auf NumPy-Arrays zugreifen (Subsetting)

[cite_start]Der Zugriff auf einzelne Elemente funktioniert wie bei Listen[cite: 1082]. Eine besondere Stärke von NumPy ist jedoch das **Filtern mit booleschen Arrays**. Du kannst eine Bedingung auf den gesamten Array anwenden und ihn dann nutzen, um nur die zutreffenden Werte auszuwählen.

```python
# bmi ist der Array aus dem Beispiel oben
[cite_start]print(bmi > 23)  # Gibt [False, False, False, True, False] zurück [cite: 1085]

# Wähle nur die BMI-Werte aus, die größer als 23 sind
[cite_start]print(bmi[bmi > 23]) # Gibt [24.7473475] zurück [cite: 1087]
```

### 2D-NumPy-Arrays

Für tabellarische Daten kannst du 2D-Arrays verwenden. [cite_start]Du erstellst sie aus einer Liste von Listen[cite: 1112]. [cite_start]Mit dem Attribut `.shape` kannst du die Dimensionen (Zeilen, Spalten) abfragen[cite: 1116].

Für den Zugriff auf Elemente in einem 2D-Array verwendet man die Notation `[zeile, spalte]`.

```python
np_2d = np.array([[1.73, 1.68, 1.71, 1.89, 1.79],
                  [65.4, 59.2, 63.6, 88.4, 68.7]])

# [cite_start]Element in Zeile 0, Spalte 2 (1.71) [cite: 1133, 1135]
print(np_2d[0, 2])

# [cite_start]Alle Zeilen, aber nur Spalten 1 und 2 [cite: 1140]
print(np_2d[:, 1:3])

# [cite_start]Nur die komplette zweite Zeile (Index 1) [cite: 1145]
print(np_2d[1, :])
```

### Grundlegende Statistik mit NumPy

NumPy ist das Fundament der Datenanalyse in Python und bietet viele eingebaute statistische Funktionen, um Daten schnell zu verstehen.

* [cite_start]`np.mean()`: Berechnet den Mittelwert[cite: 1180].
* [cite_start]`np.median()`: Findet den Median[cite: 1182].
* [cite_start]`np.std()`: Berechnet die Standardabweichung[cite: 1192].
* [cite_start]`np.corrcoef()`: Berechnet die Korrelation zwischen zwei Arrays[cite: 1187].

---


Ich hoffe, diese erweiterte Zusammenfassung gibt dir einen soliden Überblick für deinen Start in Python und die Datenanalyse!
