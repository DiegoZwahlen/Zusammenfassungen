# Java-Zusammenfassung

## Inhaltsverzeichnis

1. [if/else-Anweisungen](#1-ifelse-anweisungen)
2. [switch-Anweisung](#2-switch-anweisung)
3. [Schleifen](#3-schleifen)
   - [for-Schleife](#31-for-schleife)
   - [while-Schleife](#32-while-schleife)
   - [do-while-Schleife](#33-do-while-schleife)
4. [Arrays](#4-arrays)
5. [Methoden (Funktionen)](#5-methoden-funktionen)
6. [Objektorientierte Programmierung](#6-einf%C3%BChrung-in-die-objektorientierte-programmierung-oop)
7. [Kapselung](#7-kapselung-gettersetter-und-die-tostring-methode)

---

## 1. if/else-Anweisungen

Mit `if`-, `else-if`- und `else`-Anweisungen können Entscheidungen im Programm getroffen werden.

### if

Der Code wird nur ausgeführt, wenn die Bedingung wahr (`true`) ist.

```java
int alter = 18;

if (alter >= 18) {
    System.out.println("Volljährig");
}
```

### if-else

Wenn die Bedingung wahr ist, wird der erste Block ausgeführt. Andernfalls wird der `else`-Block ausgeführt.

```java
int zahl = 7;

if (zahl % 2 == 0) {
    System.out.println("Gerade Zahl");
} else {
    System.out.println("Ungerade Zahl");
}
```

### if-else if-else

Mit mehreren Bedingungen können verschiedene Fälle unterschieden werden.

```java
int note = 2;

if (note == 1) {
    System.out.println("Sehr gut");
} else if (note == 2) {
    System.out.println("Gut");
} else if (note == 3) {
    System.out.println("Befriedigend");
} else {
    System.out.println("Andere Note");
}
```

### Vergleichsoperatoren

| Operator | Bedeutung              |
|----------|------------------------|
| `==`     | gleich                 |
| `!=`     | ungleich               |
| `>`      | größer als             |
| `<`      | kleiner als            |
| `>=`     | größer oder gleich     |
| `<=`     | kleiner oder gleich    |

### Logische Operatoren

| Operator | Bedeutung |
|----------|-----------|
| `&&`     | UND       |
| `\|\|` | ODER      |
| `!`      | NICHT     |

**Beispiel:**

```java
if (alter >= 18 && alter < 66) {
    System.out.println("Erwerbstätig");
}
```

---

## 2. switch-Anweisung

Die `switch`-Anweisung ist eine Alternative zu vielen `if-else`-Abfragen.

### Syntax

```java
switch (variable) {
    case wert1:
        // Anweisungen
        break;
    case wert2:
        // Anweisungen
        break;
    default:
        // Standardfall
}
```

### Beispiel

```java
int tag = 3;

switch (tag) {
    case 1:
        System.out.println("Montag");
        break;
    case 2:
        System.out.println("Dienstag");
        break;
    case 3:
        System.out.println("Mittwoch");
        break;
    default:
        System.out.println("Ungültiger Tag");
}
```

### Bedeutung von `break`

Das Schlüsselwort `break` beendet den aktuellen Fall.

Ohne `break` werden die folgenden Fälle ebenfalls ausgeführt.

```java
int zahl = 1;

switch (zahl) {
    case 1:
        System.out.println("Eins");
    case 2:
        System.out.println("Zwei");
}
```

**Ausgabe:**

```text
Eins
Zwei
```

---

## 3. Schleifen

Schleifen dienen dazu, Anweisungen mehrfach auszuführen.

### 3.1 for-Schleife

Die `for`-Schleife wird verwendet, wenn die Anzahl der Wiederholungen bekannt ist.

#### Aufbau

```java
for (Initialisierung; Bedingung; Veränderung) {
    // Code
}
```

#### Beispiel

```java
for (int i = 1; i <= 5; i++) {
    System.out.println(i);
}
```

**Ausgabe:**

```text
1
2
3
4
5
```

#### Rückwärts zählen

```java
for (int i = 10; i >= 1; i--) {
    System.out.println(i);
}
```

### 3.2 while-Schleife

Die `while`-Schleife wird verwendet, wenn die Anzahl der Wiederholungen nicht bekannt ist.

#### Aufbau

```java
while (Bedingung) {
    // Code
}
```

#### Beispiel

```java
int i = 1;

while (i <= 5) {
    System.out.println(i);
    i++;
}
```

#### Endlosschleife

```java
while (true) {
    System.out.println("Endlos");
}
```

Die Bedingung wird niemals falsch.

### 3.3 do-while-Schleife

Die `do-while`-Schleife wird mindestens einmal ausgeführt.

#### Aufbau

```java
do {
    // Code
} while (Bedingung);
```

#### Beispiel

```java
int i = 1;

do {
    System.out.println(i);
    i++;
} while (i <= 5);
```

#### Unterschied zur while-Schleife

```java
int i = 10;

while (i < 5) {
    System.out.println("Hallo");
}
```

**Ausgabe:**

```text
Keine Ausgabe
```

```java
int i = 10;

do {
    System.out.println("Hallo");
} while (i < 5);
```

**Ausgabe:**

```text
Hallo
```

### Vergleich der Schleifen

| Schleife   | Verwendung                         |
|------------|------------------------------------|
| `for`      | Anzahl der Durchläufe bekannt      |
| `while`    | bedingungsgesteuert                |
| `do-while` | mindestens ein Durchlauf           |

---

## 4. Arrays

Ein Array speichert mehrere Werte desselben Datentyps.

### Deklaration

```java
int[] zahlen;
```

### Initialisierung mit Größe

```java
int[] zahlen = new int[5];
```

Das Array besitzt 5 Speicherplätze.

**Indexe:**

```text
0 1 2 3 4
```

### Initialisierung mit Werten

```java
int[] zahlen = {10, 20, 30, 40, 50};
```

### Zugriff auf Elemente

```java
System.out.println(zahlen[0]);
```

**Ausgabe:**

```text
10
```

### Wert ändern

```java
zahlen[1] = 100;
```

### Länge eines Arrays

```java
System.out.println(zahlen.length);
```

**Ausgabe:**

```text
5
```

### Array mit for-Schleife durchlaufen

```java
for (int i = 0; i < zahlen.length; i++) {
    System.out.println(zahlen[i]);
}
```

### Array mit foreach-Schleife durchlaufen

```java
for (int zahl : zahlen) {
    System.out.println(zahl);
}
```

### Zweidimensionale Arrays

```java
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6}
};
```

**Zugriff:**

```java
System.out.println(matrix[1][2]);
```

**Ausgabe:**

```text
6
```

---

## 5. Methoden (Funktionen)

Methoden fassen Programmcode zusammen und machen Programme übersichtlicher.

### Allgemeiner Aufbau

```java
Rückgabetyp Methodenname(Parameter) {
    // Anweisungen
    return Wert;
}
```

### Methode ohne Parameter

```java
public static void begruessung() {
    System.out.println("Hallo");
}
```

**Aufruf:**

```java
begruessung();
```

### Methode mit Parametern

```java
public static void begruessung(String name) {
    System.out.println("Hallo " + name);
}
```

**Aufruf:**

```java
begruessung("Max");
```

**Ausgabe:**

```text
Hallo Max
```

### Methode mit Rückgabewert

```java
public static int addiere(int a, int b) {
    return a + b;
}
```

**Aufruf:**

```java
int summe = addiere(3, 4);
System.out.println(summe);
```

**Ausgabe:**

```text
7
```

### Mehrere Parameter

```java
public static double berechneFlaeche(double breite, double hoehe) {
    return breite * hoehe;
}
```

### Bedeutung von `void`

`void` bedeutet, dass die Methode keinen Wert zurückgibt.

```java
public static void ausgabe() {
    System.out.println("Hallo");
}
```

### Bedeutung von `return`

`return` beendet die Methode und gibt einen Wert zurück.

```java
public static int quadrat(int x) {
    return x * x;
}
```

### Komplettes Beispiel

```java
public class Main {
    public static int addiere(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        int ergebnis = addiere(5, 7);
        System.out.println(ergebnis);
    }
}
```

**Ausgabe:**

```text
12
```

## 6. Einführung in die Objektorientierte Programmierung (OOP)

### Inhaltsverzeichnis

1. [Klasse vs. Objekt](#1-klasse-vs-objekt)
2. [Klassen erstellen](#2-klassen-erstellen)
3. [Attribute](#3-attribute)
4. [Konstruktoren](#4-konstruktoren)
5. [Das Schlüsselwort `this`](#5-das-schl%C3%BCsselwort-this)
6. [Objekte erzeugen](#6-objekte-erzeugen)
7. [Beispielklasse](#7-komplettes-beispiel)
8. [Zusammenfassung](#8-zusammenfassung)

---

## 1. Klasse vs. Objekt

### Klasse

Eine Klasse ist ein Bauplan für Objekte.

Sie beschreibt:

- Welche Eigenschaften (Attribute) ein Objekt besitzt.
- Welche Fähigkeiten (Methoden) ein Objekt besitzt.

#### Beispiel

Klasse:

```java
class Auto {
    String marke;
    int baujahr;
}
```

Die Klasse beschreibt lediglich, wie ein Auto aussehen soll.

---

### Objekt

Ein Objekt ist eine konkrete Instanz einer Klasse.

#### Beispiel

```java
Auto auto1 = new Auto();
```

`auto1` ist ein Objekt der Klasse `Auto`.

---

### Klasse vs. Objekt

| Klasse | Objekt |
|----------|----------|
| Bauplan | Konkretes Exemplar |
| Beschreibt Eigenschaften | Besitzt tatsächliche Werte |
| `Auto` | `auto1` |
| `Student` | `max` |

Beispiel:

```java
Auto auto1 = new Auto();
Auto auto2 = new Auto();
```

Hier existieren zwei verschiedene Objekte derselben Klasse.

---

## 2. Klassen erstellen

### Aufbau einer Klasse

```java
class Klassenname {

    // Attribute

    // Konstruktor

    // Methoden
}
```

#### Beispiel

```java
class Student {

    String name;
    int alter;

}
```

---

## 3. Attribute

Attribute beschreiben die Eigenschaften eines Objekts.

#### Beispiel

```java
class Student {

    String name;
    int alter;
    double note;

}
```

Jedes Objekt besitzt seine eigenen Werte.

---

### Zugriff auf Attribute

```java
Student s = new Student();

s.name = "Max";
s.alter = 20;

System.out.println(s.name);
```

Ausgabe:

```
Max
```

---

## 4. Konstruktoren

Ein Konstruktor wird automatisch aufgerufen, wenn ein Objekt erzeugt wird.

Er dient dazu, Attribute zu initialisieren.

---

### Konstruktor ohne Parameter

```java
class Student {

    String name;

    public Student() {
        name = "Unbekannt";
    }
}
```

Objekt erzeugen:

```java
Student s = new Student();
```

---

### Konstruktor mit Parametern

```java
class Student {

    String name;
    int alter;

    public Student(String n, int a) {
        name = n;
        alter = a;
    }
}
```

Objekt erzeugen:

```java
Student s = new Student("Max", 20);
```

---

## 5. Das Schlüsselwort this

`this` verweist auf das aktuelle Objekt.

---

### Problem ohne this

```java
class Student {

    String name;

    public Student(String name) {
        name = name;
    }
}
```

Hier wird der Parameter sich selbst zugewiesen.

Das Attribut bleibt leer.

---

### Lösung mit this

```java
class Student {

    String name;

    public Student(String name) {
        this.name = name;
    }
}
```

Bedeutung:

```java
this.name
```

= Attribut des Objekts

```java
name
```

= Parameter des Konstruktors

---

### Mehrere Attribute

```java
class Student {

    String name;
    int alter;

    public Student(String name, int alter) {

        this.name = name;
        this.alter = alter;
    }
}
```

---

## 6. Objekte erzeugen

### Allgemeine Syntax

```java
Klassenname objektname = new Klassenname(...);
```

#### Beispiel

```java
Student max = new Student("Max", 20);
```

---

### Auf Attribute zugreifen

```java
System.out.println(max.name);
System.out.println(max.alter);
```

Ausgabe:

```
Max
20
```

---

## 7. Komplettes Beispiel

```java
public class Student {

    String name;
    int alter;

    public Student(String name, int alter) {

        this.name = name;
        this.alter = alter;
    }
}
```

```java
public class Main {

    public static void main(String[] args) {

        Student max = new Student("Max", 20);

        System.out.println(max.name);
        System.out.println(max.alter);
    }
}
```

Ausgabe:

```
Max
20
```

---

## Beispiel mit zwei Objekten

```java
public class Student {

    String name;
    int alter;

    public Student(String name, int alter) {

        this.name = name;
        this.alter = alter;
    }
}
```

```java
public class Main {

    public static void main(String[] args) {

        Student max = new Student("Max", 20);
        Student anna = new Student("Anna", 22);

        System.out.println(max.name);
        System.out.println(anna.name);
    }
}
```

Ausgabe:

```
Max
Anna
```

Jedes Objekt besitzt eigene Attributwerte.

---

## 8. Zusammenfassung

### Klasse

- Bauplan für Objekte
- Enthält Attribute und Methoden

### Objekt

- Konkrete Instanz einer Klasse
- Wird mit `new` erzeugt

### Attribute

- Speichern Eigenschaften eines Objekts

Beispiel:

```java
String name;
int alter;
```

### Konstruktor

- Hat denselben Namen wie die Klasse
- Besitzt keinen Rückgabetyp
- Wird beim Erzeugen eines Objekts automatisch aufgerufen

Beispiel:

```java
public Student(String name) {
    this.name = name;
}
```

### this

- Verweist auf das aktuelle Objekt
- Wird häufig zur Unterscheidung von Attributen und Parametern verwendet

Beispiel:

```java
this.name = name;
```

### Objekterzeugung

```java
Student max = new Student("Max", 20);
```

## 7. Kapselung, Getter/Setter und die `toString()`-Methode

### 7.1 Kapselung (Encapsulation)

Kapselung ist ein grundlegendes Prinzip der objektorientierten Programmierung (OOP). Dabei werden die Daten (Attribute) eines Objekts vor direktem Zugriff von außen geschützt.

Das Ziel ist, dass Änderungen an den Daten nur über festgelegte Methoden erfolgen können.

### Der `private`-Zugriffsmodifikator

Mit dem Schlüsselwort `private` können Attribute so deklariert werden, dass sie nur innerhalb derselben Klasse zugänglich sind.

```java
public class Person {
    private String name;
    private int alter;
}
```

Ein direkter Zugriff von außen ist dann nicht mehr möglich:

```java
Person p = new Person();

// Fehler:
p.name = "Max";
```

### Vorteile der Kapselung

- Schutz der Daten vor unerlaubten Änderungen
- Kontrolle über den Zugriff auf Attribute
- Vermeidung von fehlerhaften Werten
- Bessere Wartbarkeit und Erweiterbarkeit des Codes

### Beispiel

Ohne Kapselung:

```java
public class Person {
    public int alter;
}
```

```java
Person p = new Person();
p.alter = -10; // Ungültiger Wert möglich
```

Mit Kapselung:

```java
public class Person {
    private int alter;
}
```

Nun kann der Zugriff kontrolliert werden.

---

### 7.2 Getter und Setter

Da auf `private` Attribute nicht direkt zugegriffen werden kann, werden sogenannte Getter und Setter verwendet.

#### Getter

Getter lesen den Wert eines Attributs aus.

```java
public int getAlter() {
    return alter;
}
```

Verwendung:

```java
int aktuellesAlter = person.getAlter();
```

#### Setter

Setter verändern den Wert eines Attributs.

```java
public void setAlter(int neuesAlter) {
    alter = neuesAlter;
}
```

Verwendung:

```java
person.setAlter(20);
```

### Vollständiges Beispiel

```java
public class Person {

    private String name;

    public String getName() {
        return name;
    }

    public void setName(String neuerName) {
        name = neuerName;
    }
}
```

Verwendung:

```java
Person p = new Person();

p.setName("Max");

System.out.println(p.getName());
```

Ausgabe:

```text
Max
```

### Datenvalidierung mit Settern

Ein großer Vorteil von Settern ist die Möglichkeit, Eingaben zu überprüfen.

```java
public void setAlter(int neuesAlter) {
    if (neuesAlter >= 0) {
        alter = neuesAlter;
    }
}
```

Dadurch werden ungültige Werte verhindert:

```java
person.setAlter(-5); // Wird nicht übernommen
```

### Das Schlüsselwort `this`

Oft haben Parameter und Attribute denselben Namen.

```java
private String name;

public void setName(String name) {
    this.name = name;
}
```

`this.name` bezeichnet das Attribut des aktuellen Objekts.

`name` bezeichnet den übergebenen Parameter.

---

### 7.3 Die `toString()`-Methode

Jedes Objekt in Java besitzt eine Methode namens `toString()`. Sie wird von der Klasse `Object` geerbt.

Die Methode liefert eine Textdarstellung eines Objekts zurück.

### Standardverhalten

Ohne eigene Implementierung:

```java
Person p = new Person();

System.out.println(p);
```

Ausgabe:

```text
Person@4e25154f
```

Diese Ausgabe ist meist wenig hilfreich.

### Eigene `toString()`-Methode erstellen

Die Methode kann überschrieben werden, um sinnvolle Informationen auszugeben.

```java
public class Person {

    private String name;
    private int alter;

    @Override
    public String toString() {
        return "Name: " + name + ", Alter: " + alter;
    }
}
```

### Verwendung

```java
Person p = new Person();

p.setName("Max");
p.setAlter(20);

System.out.println(p);
```

Ausgabe:

```text
Name: Max, Alter: 20
```

### Die Annotation `@Override`

```java
@Override
public String toString() {
    return "Beispiel";
}
```

`@Override` zeigt an, dass eine geerbte Methode überschrieben wird.

Vorteile:

- Schreibfehler werden erkannt
- Der Compiler überprüft die Methode
- Der Code wird leichter verständlich

### Komplettes Beispiel

```java
public class Person {

    private String name;
    private int alter;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAlter() {
        return alter;
    }

    public void setAlter(int alter) {
        if (alter >= 0) {
            this.alter = alter;
        }
    }

    @Override
    public String toString() {
        return "Person{name='" + name + "', alter=" + alter + "}";
    }
}
```

Verwendung:

```java
Person p = new Person();

p.setName("Max");
p.setAlter(20);

System.out.println(p);
```

Ausgabe:

```text
Person{name='Max', alter=20}
```

---

### Zusammenfassung

| Konzept | Beschreibung |
|----------|-------------|
| `private` | Verhindert direkten Zugriff auf Attribute von außen |
| Getter | Liest den Wert eines Attributs aus |
| Setter | Verändert den Wert eines Attributs |
| `this` | Verweist auf das aktuelle Objekt |
| `toString()` | Liefert eine Textdarstellung eines Objekts |
| `@Override` | Kennzeichnet das Überschreiben einer geerbten Methode |

### Merksatz

> Attribute sollten in der Regel `private` sein.
>
> Auf sie wird über Getter und Setter zugegriffen.
>
> Die `toString()`-Methode dient dazu, Objekte lesbar als Text darzustellen.
