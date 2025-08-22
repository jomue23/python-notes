# Zusammenfassung: Intermediate Python

Diese Zusammenfassung baut auf den Grundlagen von Python auf und behandelt fortgeschrittene Themen, die für die Datenanalyse entscheidend sind. Dazu gehören die Visualisierung von Daten, die Arbeit mit komplexeren Datenstrukturen wie Dictionaries und Pandas DataFrames sowie die Anwendung von Logik und Schleifen zur Datenmanipulation.

---

## 1. Grundlagen der Datenvisualisierung mit Matplotlib (Kapitel 1)

[cite_start]Datenvisualisierung ist ein entscheidender Schritt in der Datenanalyse, um Daten zu explorieren und Erkenntnisse zu berichten[cite: 13, 14, 15]. Die wichtigste Bibliothek dafür ist **Matplotlib**.

[cite_start]Das Fundament für das Plotten ist das Modul `matplotlib.pyplot`, das üblicherweise mit dem Alias `plt` importiert wird[cite: 476].

```python
import matplotlib.pyplot as plt
```

### Grundlegende Diagrammtypen

* [cite_start]**Liniendiagramm (`plt.plot()`):** Ideal, um die Entwicklung von Werten über die Zeit darzustellen[cite: 476].
    ```python
    year = [1950, 1970, 1990, 2010]
    pop = [2.519, 3.692, 5.263, 6.972]
    plt.plot(year, pop)
    plt.show() # Zeigt das Diagramm an
    ```
    
* [cite_start]**Streudiagramm (`plt.scatter()`):** Wird verwendet, um die Beziehung zwischen zwei numerischen Variablen zu untersuchen[cite: 539]. Jeder Punkt repräsentiert eine Beobachtung.
    ```python
    plt.scatter(year, pop)
    plt.show()
    ```

* [cite_start]**Histogramm (`plt.hist()`):** Zeigt die Verteilung einer einzelnen numerischen Variable, indem die Werte in Intervalle ("bins") eingeteilt und deren Häufigkeit gezählt wird[cite: 559, 560, 665].
    ```python
    values = [0,0.6,1.4,1.6,2.2,2.5,2.6,3.2,3.5,3.9,4.2,6]
    plt.hist(values, bins=3)
    plt.show()
    ```
    
### Diagramme anpassen

Ein einfaches Diagramm ist selten aussagekräftig genug. [cite_start]Matplotlib bietet viele Funktionen, um Diagramme zu verbessern[cite: 801]:

* [cite_start]**Achsenbeschriftungen:** `plt.xlabel()` und `plt.ylabel()`[cite: 843, 844].
* [cite_start]**Titel:** `plt.title()`[cite: 884].
* **Achsen-Ticks:** `plt.yticks()` und `plt.xticks()` ermöglichen es, die Markierungen auf den Achsen anzupassen. [cite_start]Man kann sowohl die Positionen als auch die Beschriftungen ändern[cite: 944, 985, 986].

```python
# Vollständiges Beispiel mit Anpassungen
year = [1950, 1970, 1990, 2010]
pop = [2.519, 3.692, 5.263, 6.972]

plt.plot(year, pop)

# Anpassungen hinzufügen
plt.xlabel('Year')
plt.ylabel('Population (in Billions)')
plt.title('World Population Growth')
plt.yticks([2, 4, 6, 8], ['2B', '4B', '6B', '8B'])

plt.show()
```

---

## 2. Fortgeschrittene Datenstrukturen (Kapitel 2)

### Dictionaries: Schlüssel-Wert-Paare

[cite_start]Während Listen über einen numerischen Index auf ihre Elemente zugreifen, sind **Dictionaries** dafür optimiert, Werte über einen eindeutigen **Schlüssel** (Key) nachzuschlagen[cite: 1225]. [cite_start]Dies ist oft intuitiver als die Suche nach dem Index in einer separaten Liste[cite: 1127, 1128].

* [cite_start]**Syntax:** `{schlüssel1: wert1, schlüssel2: wert2}`[cite: 1150].
* [cite_start]**Werte abrufen:** `world['albania']`[cite: 1150].
* [cite_start]**Eintrag hinzufügen/ändern:** `world['sealand'] = 0.000027`[cite: 1181].
* [cite_start]**Eintrag löschen:** `del(world['sealand'])`[cite: 1193].
* [cite_start]**Schlüssel müssen "unveränderlich" (immutable) sein:** Strings, Zahlen oder Booleans sind erlaubt, Listen hingegen nicht[cite: 1169, 1172, 1173].

```python
# Definition eines Dictionaries
world = {"afghanistan": 30.55, "albania": 2.77, "algeria": 39.21}

# Wert abrufen
print(world["albania"]) # Gibt 2.77 aus

# Prüfen, ob ein Schlüssel existiert
print("sealand" in world) # Gibt False aus
```

### Pandas DataFrame: Arbeiten mit Tabellendaten

[cite_start]Für tabellarische Daten, bei denen Spalten unterschiedliche Datentypen haben können (z.B. Text und Zahlen), sind NumPy-Arrays ungeeignet[cite: 1251, 1252]. [cite_start]Hierfür wurde die Bibliothek **Pandas** entwickelt[cite: 1261]. [cite_start]Die zentrale Datenstruktur ist der **DataFrame**[cite: 1265].

Ein DataFrame kann auf verschiedene Weisen erstellt werden:

* [cite_start]**Aus einem Dictionary:** Die Schlüssel werden zu Spaltennamen und die Werte zu den Spaltendaten[cite: 1279, 1280, 1282].
* [cite_start]**Aus einer CSV-Datei:** Mit `pd.read_csv()`[cite: 1312]. [cite_start]Dabei kann man mit `index_col=0` die erste Spalte der CSV als Zeilen-Index festlegen[cite: 1318].

```python
import pandas as pd

# Daten für den DataFrame
dict = {
    "country": ["Brazil", "Russia", "India"],
    "capital": ["Brasilia", "Moscow", "New Delhi"],
    "population": [200.4, 143.5, 1252]
}

# DataFrame erstellen
brics = pd.DataFrame(dict)

# Zeilen-Labels (Index) setzen
brics.index = ["BR", "RU", "IN"]
print(brics)
```

### Datenzugriff in Pandas: loc und iloc

Pandas bietet mehrere Methoden, um auf Daten zuzugreifen. [cite_start]Die wichtigsten sind `loc` und `iloc`[cite: 1421, 1422].

* **Eckige Klammern `[]`:**
    * [cite_start]`brics['country']`: Wählt eine einzelne Spalte aus (als `Series`)[cite: 1342].
    * [cite_start]`brics[['country', 'capital']]`: Wählt mehrere Spalten aus (als `DataFrame`)[cite: 1386].
    * [cite_start]`brics[1:4]`: Wählt Zeilen basierend auf ihrer numerischen Position (Slicing)[cite: 1405].

* [cite_start]**`loc` (Label-basiert):** Wählt Daten anhand der Zeilen- und Spalten-**Labels** aus[cite: 1421].
    * [cite_start]`brics.loc['RU']`: Wählt die Zeile mit dem Label 'RU'[cite: 1427].
    * [cite_start]`brics.loc[['RU', 'IN'], ['country', 'capital']]`: Wählt bestimmte Zeilen und Spalten aus[cite: 1451].

* [cite_start]**`iloc` (Integer-basiert):** Wählt Daten anhand der numerischen **Position** aus, genau wie bei NumPy-Arrays[cite: 1422].
    * `brics.iloc[1]`: Wählt die zweite Zeile (Position 1).
    * [cite_start]`brics.iloc[[1, 2], [0, 1]]`: Wählt die zweite und dritte Zeile sowie die erste und zweite Spalte aus[cite: 1531].

---

## 3. Logik und Kontrollstrukturen (Kapitel 3 & 4)

### Vergleichs- und Boolesche Operatoren

[cite_start]Um Daten zu filtern, benötigen wir Vergleichs- (`>`, `==`, `!=`, etc.) und boolesche Operatoren (`and`, `or`, `not`)[cite: 1630, 1639, 1640, 1641]. [cite_start]Wenn diese auf NumPy-Arrays oder Pandas Series angewendet werden, müssen spezielle Funktionen wie `np.logical_and()` verwendet werden, da `and` und `or` keine Vektor-Operationen unterstützen[cite: 1686, 1687, 1691, 1692].

### Bedingte Anweisungen: if, elif, else

Diese Anweisungen steuern den Programmfluss basierend auf Bedingungen. [cite_start]Der Code-Block unter `if` wird ausgeführt, wenn die Bedingung `True` ist[cite: 1721, 1722]. [cite_start]Falls nicht, wird die `elif`-Bedingung geprüft[cite: 1786]. [cite_start]Wenn keine der Bedingungen zutrifft, wird der `else`-Block ausgeführt[cite: 1772, 1773].

```python
z = 6
if z % 2 == 0:
    print("z ist durch 2 teilbar") # Wird ausgeführt und der Block beendet
elif z % 3 == 0:
    print("z ist durch 3 teilbar")
else:
    print("z ist weder durch 2 noch 3 teilbar")
```

### Das Filtern von DataFrames

Eine der häufigsten Aufgaben ist das Filtern von DataFrames basierend auf Bedingungen. [cite_start]Dies geschieht in drei Schritten[cite: 1836]:

1.  [cite_start]**Spalte auswählen:** `brics['area']`[cite: 1837].
2.  **Vergleich anwenden:** `brics['area'] > 8`. [cite_start]Dies erzeugt eine boolesche Pandas Series[cite: 1838, 1875].
3.  [cite_start]**DataFrame filtern:** Diese boolesche Series wird verwendet, um die Zeilen des ursprünglichen DataFrames auszuwählen, für die der Wert `True` ist[cite: 1839].

```python
# Ein-Schritt-Filterung
# Wähle alle Länder mit einer Fläche über 8 Mio. km²
is_huge = brics['area'] > 8
print(brics[is_huge])

# Kombination mit logischen Operatoren
import numpy as np
condition = np.logical_and(brics["area"] > 8, brics["area"] < 10)
print(brics[condition])
```

### Wiederholungen mit Schleifen: `while` und `for`

* [cite_start]**`while`-Schleife:** Führt einen Code-Block so lange aus, wie eine Bedingung `True` ist[cite: 2394, 2395]. [cite_start]Sie ist quasi eine wiederholte `if`-Anweisung[cite: 2390].
    ```python
    error = 50.0
    while error > 1:
        error = error / 4
        print(error)
    ```

* [cite_start]**`for`-Schleife:** Iteriert über jedes Element in einer Sequenz (z.B. einer Liste oder einem String)[cite: 2503, 2505].
    ```python
    fam = [1.73, 1.68, 1.71, 1.89]
    for height in fam:
        print(height)
    ```

### Iterieren über Datenstrukturen

* [cite_start]**Dictionaries:** Mit der `.items()`-Methode, um auf Schlüssel und Werte zuzugreifen[cite: 2635].
    ```python
    for key, value in world.items():
        print(key + " -- " + str(value))
    ```
* [cite_start]**NumPy Arrays:** Um über jedes einzelne Element in einem 2D-Array zu iterieren, verwendet man `np.nditer()`[cite: 2704, 2718].
* [cite_start]**Pandas DataFrames:** Der Standardweg ist die `.iterrows()`-Methode, die bei jeder Iteration das Zeilen-Label und die Zeile als Series-Objekt zurückgibt[cite: 2749].
    ```python
    for lab, row in brics.iterrows():
        print(lab + ": " + row["capital"])
    ```

### Effiziente Alternative zu Schleifen: `.apply()`

[cite_start]Das Iterieren über große DataFrames mit `.iterrows()` kann langsam sein[cite: 2785]. [cite_start]Wenn du eine Funktion auf eine ganze Spalte anwenden möchtest (z.B. um eine neue Spalte zu erstellen), ist die `.apply()`-Methode wesentlich effizienter[cite: 2790, 2794].

```python
# Ineffizienter Weg mit Schleife
for lab, row in brics.iterrows():
    brics.loc[lab, "name_length"] = len(row["country"])

# Effizienter Weg mit .apply()
brics["name_length"] = brics["country"].apply(len)
print(brics)
```

---