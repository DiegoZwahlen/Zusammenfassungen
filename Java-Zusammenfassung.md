Java-Zusammenfassung

1. if/else-Anweisungen
Mit if-, else-if- und else-Anweisungen können Entscheidungen im Programm getroffen werden.
if
Der Code wird nur ausgeführt, wenn die Bedingung wahr (true) ist.

int alter = 18;

if (alter >= 18) {
    System.out.println("Volljährig");
}
if-else
Wenn die Bedingung wahr ist, wird der erste Block ausgeführt. Andernfalls wird der else-Block ausgeführt.
int zahl = 7;

if (zahl % 2 == 0) {
    System.out.println("Gerade Zahl");
} else {
    System.out.println("Ungerade Zahl");
}
if-else if-else
Mit mehreren Bedingungen können verschiedene Fälle unterschieden werden.
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
Vergleichsoperatoren
Operator	Bedeutung
==	gleich
!=	ungleich
>	grösser als
<	kleiner als
>=	grösser oder gleich
<=	kleiner oder gleich
Logische Operatoren
Operator	Bedeutung
&&	UND
||	ODER
!	NICHT
Beispiel:
if (alter >= 18 && alter < 66) {
    System.out.println("Erwerbstätig");
}
________________________________________

2. switch-Anweisung
Die switch-Anweisung ist eine Alternative zu vielen if-else-Abfragen.

Syntax
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

Beispiel
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

Bedeutung von break
Das Schlüsselwort break beendet den aktuellen Fall.
Ohne break werden die folgenden Fälle ebenfalls ausgeführt.
int zahl = 1;

switch (zahl) {
    case 1:
        System.out.println("Eins");

    case 2:
        System.out.println("Zwei");
}

Ausgabe:
Eins
Zwei
________________________________________

3. Schleifen
Schleifen dienen dazu, Anweisungen mehrfach auszuführen.

3.1 for-Schleife
Die for-Schleife wird verwendet, wenn die Anzahl der Wiederholungen bekannt ist.
Aufbau
for (Initialisierung; Bedingung; Veränderung) {
    // Code
}

Beispiel
for (int i = 1; i <= 5; i++) {
    System.out.println(i);
}

Ausgabe:
1
2
3
4
5

Rückwärts zählen
for (int i = 10; i >= 1; i--) {
    System.out.println(i);
}
________________________________________

3.2 while-Schleife
Die while-Schleife wird verwendet, wenn die Anzahl der Wiederholungen nicht bekannt ist.
Aufbau
while (Bedingung) {
    // Code
}

Beispiel
int i = 1;

while (i <= 5) {
    System.out.println(i);
    i++;
}

Endlosschleife
while (true) {
    System.out.println("Endlos");
}

Die Bedingung wird niemals falsch.
________________________________________

3.3 do-while-Schleife
Die do-while-Schleife wird mindestens einmal ausgeführt.

Aufbau
do {
    // Code
}
while (Bedingung);
Beispiel
int i = 1;

do {
    System.out.println(i);
    i++;
}
while (i <= 5);
Unterschied zur while-Schleife
int i = 10;

while (i < 5) {
    System.out.println("Hallo");
}

Ausgabe:
Keine Ausgabe
int i = 10;

do {
    System.out.println("Hallo");
}
while (i < 5);

Ausgabe:
Hallo
Vergleich der Schleifen
Schleife	Verwendung
for	Anzahl der Durchläufe bekannt
while	Bedingungsgesteuert
do-while	Mindestens ein Durchlauf
________________________________________

4. Arrays
Ein Array speichert mehrere Werte desselben Datentyps.
Deklaration
int[] zahlen;
Initialisierung mit Grösse
int[] zahlen = new int[5];
Das Array besitzt 5 Speicherplätze.

Indexe:
0 1 2 3 4
Initialisierung mit Werten
int[] zahlen = {10, 20, 30, 40, 50};
Zugriff auf Elemente
System.out.println(zahlen[0]);

Ausgabe:
10
Wert ändern
zahlen[1] = 100;
Länge eines Arrays
System.out.println(zahlen.length);

Ausgabe:
5
________________________________________

Array mit for-Schleife durchlaufen
for (int i = 0; i < zahlen.length; i++) {
    System.out.println(zahlen[i]);
}
________________________________________

Array mit foreach-Schleife durchlaufen
for (int zahl : zahlen) {
    System.out.println(zahl);
}
________________________________________

Zweidimensionale Arrays
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6}
};

Zugriff:
System.out.println(matrix[1][2]);

Ausgabe:
6
________________________________________

5. Methoden (Funktionen)
Methoden fassen Programmcode zusammen und machen Programme übersichtlicher.
Allgemeiner Aufbau
Rückgabetyp Methodenname(Parameter) {
    // Anweisungen
    return Wert;
}
________________________________________

Methode ohne Parameter
public static void begruessung() {
    System.out.println("Hallo");
}

Aufruf:
begruessung();
________________________________________

Methode mit Parametern
public static void begruessung(String name) {
    System.out.println("Hallo " + name);
}

Aufruf:
begruessung("Max");

Ausgabe:
Hallo Max
________________________________________

Methode mit Rückgabewert
public static int addiere(int a, int b) {
    return a + b;
}

Aufruf:
int summe = addiere(3, 4);
System.out.println(summe);

Ausgabe:
7
________________________________________

Mehrere Parameter
public static double berechneFlaeche(double breite, double hoehe) {
    return breite * hoehe;
}
________________________________________

Bedeutung von void
void bedeutet, dass die Methode keinen Wert zurückgibt.
public static void ausgabe() {
    System.out.println("Hallo");
}
________________________________________

Bedeutung von return
return beendet die Methode und gibt einen Wert zurück.
public static int quadrat(int x) {
    return x * x;
}
________________________________________

Komplettes Beispiel
public class Main {

    public static int addiere(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {

        int ergebnis = addiere(5, 7);

        System.out.println(ergebnis);
    }
}

Ausgabe:
12

