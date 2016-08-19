
********************
Einführung in Python
********************

Agenda
------

.. rst-class:: build
* Was ist Python?
* Warum Python?
* Wie funktioniert Python?

Was ist Python?
---------------

.. rst-class:: build
* interpretiert
* dynamisch typisiert
* Multiparadigmensprache

  .. rst-class:: build
  * imperativ
  * strukturiert/prozedural
  * Objekt-orientiert
  * funktional
  * Aspekt-orientiert

Geschichte
----------

.. rst-class:: build
* Entworfen 1991 von Guido van Rossum

  .. rst-class:: build
  * als Nachfolger von ABC
  * Monthy Python > Schlangen

* aktuell Version 3.5.2 / 2.7.12

  .. rst-class:: build
  * 3 > 2

Warum Python?
-------------

Sprache
-------

.. rst-class:: build
* Fokus auf Lesbarkeit
* einfach zu erlernen
* ausdrucksstark und mächtig

Batteries included
------------------

.. rst-class:: build
* Umfangreiche Standardbibliothek
* gigantisches Open Source Ökosystem

Gute Integrationsmöglichkeiten
------------------------------

.. rst-class:: build
* C
* Java
* .NET

Einsatzbereiche
---------------
.. rst-class:: build
* Skripte
* Systemadministration
* Kommandozeilentools
* GUI-Programme
* Web
* 3D
* Scientific Computing: SciPy
* Spiele
* Micro-Controller
* Bildung: OLPC, RaspberryPi
* ...


.. notes::
   * Fabric, Ansible, OpenStack, Portage/Gentoo
   * Django, Pyramid, Flask, Tornado
   * Blender
   * SciPy
   * OLPC, RaspberryPi

Firmen & Institutionen
----------------------
.. rst-class:: build
- Google, Instagram, Quora, Uber, Lieferheld...
- Mozilla, Canonical, RedHat, Gentoo…
- DLR, NASA, CERN...

Community
---------
.. rst-class:: build
- Mailinglisten
- Usergroups
- Konferenzen


Wie funktioniert Python?
------------------------


Interpreter
-----------

::

    $ python3
    Python 3.5.2 (v3.5.2:4def2a2901a5, Jun 26 2016, 10:47:25)
    [GCC 4.2.1 (Apple Inc. build 5666) (dot 3)] on darwin
    Type "help", "copyright", "credits" or "license" for more information.
    >>> print('Hello FrOSCon')
    Hello FrOSCon
    >>>


Skript
------

::

    $ echo "print('Hello FrOSCon')" > hello_froscon.py
    $ python hello_froscon.py
    Hello FrOSCon
    $


Zeichenketten (Strings)
-----------------------

.. rst-class:: build

    >>> 'spam eggs'
    'spam eggs'

    >>> 'doesn\'t'
    "doesn't"

    >>> "doesn't"
    "doesn't"

    >>> '"Ja,", hat er gesagt.'
    '"Ja,", hat er gesagt.'

    >>> "\"Ja,\", hat er gesagt."
    '"Ja,", hat er gesagt.'

    >>> '"Isses nich\',", sagte sie.'
    '"Isses nich\',", sagte sie.

Lange Zeichenketten
-------------------

.. rst-class:: build

    >>>  hello = "Dies ist eine ziemlich lange Zeichenkette,\n\
    .... die mehrere Zeilen Text enthält und wie man sie auch in C schreiben würde.\n\
    ....    Achtung: Leerzeichen am Anfang haben eine Bedeutung\
    .... für die Darstellung."
    .... print(hello)

.. rst-class:: build
.. code-block:: text

    Dies ist eine ziemlich lange Zeichenkette,
    die mehrere Zeilen Text enthält und wie man sie auch in C schreiben würde.
        Achtung: Leerzeichen am Anfang haben eine Bedeutung für die Darstellung.

.. rst-class:: build

    >>>  hello = """Alternativ kann man auch drei Anführungszeichen verwenden,
    ....            aber auch hier werden Leerzeichen beachtet."""



Unicode
-------

Seit Python 3.0 unterstützen durchgängig Unicode

    >>> print("Äpfel")
    Äpfel
    >>> ä = 3
    >>> "Äpfel".encode('utf-8')
    b'\xc3\x84pfel'

Zahlen & Arithmetik
-------------------
.. rst-class:: build

    >>> 2 + 2
    4
    >>> # Dies ist ein Kommentar
    ... 2 + 2
    4
    >>> 2 + 2  # und dies ist ein Kommentar in derselben Zeile wie Code
    4
    >>> (50 - 5 * 6) / 4
    5.0
    >>> 8 / 5 # Brüche gehen nicht verloren, wenn man Ganzzahlen teilt
    1.6

Ganzzahldivision
----------------
.. rst-class:: build

    >>> # Ganzzahldivision gibt ein abgerundetes Ergebnis zurück:
    ... 7 // 3
    2
    >>> 7 // -3
    -3

Fließkommazahlen
----------------
.. rst-class:: build

    >>> 3 * 3.75 / 1.5
    7.5
    >>> 7.0 / 2
    3.5

Komplexe Zahlen
---------------
.. rst-class:: build

    >>> 1j
    1j
    >>> 1j * 1J
    (-1+0j)
    >>> 1j * complex(0, 1)
    (-1+0j)
    >>> 3 + 1j * 3
    (3+3j)
    >>> (3 + 1j) * 3
    (9+3j)
    >>> (1 + 2j) / (1 + 1j)
    (1.5+0.5j)

Variablen
---------
.. rst-class:: build

    >>> width = 20
    >>> height = 5 * 9
    >>> width * height
    900

Unser erster Fehler
-------------------
.. rst-class:: build

    >>> # Versuche eine undefinierte Variable abzurufen
    ... n
    Traceback (most recent call last):
     File "<stdin>", line 1, in <module>
    NameError: name 'n' is not defined

Mehrfachzuweisung
-----------------
.. rst-class:: build

    >>> x = y = z = 0  # Null für x, y und z
    >>> x
    0
    >>> y
    0
    >>> z
    0


Addition und Multiplikation von Zeichenketten
---------------------------------------------
.. rst-class:: build

    >>> word = 'Help' + 'A'
    >>> word
    'HelpA'
    >>> '<' + word*5 + '>'
    '<HelpAHelpAHelpAHelpAHelpA>'


Indizierung
-----------
.. rst-class:: build

    >>> word
    'HelpA'
    >>> word[4]
    'A'
    >>> word[2]
    'r'

Slices
------
.. rst-class:: build

    >>> word[0:2]
    'He'
    >>> word[2:4]
    'lp'

    >>> word[:2]
    'He'
    >>> word[2:]
    'lpA'
    >>> word[:]

Zeichenketten ändern
--------------------

.. rst-class:: build

    >>> word[0] = 'x'
    Traceback (most recent call last):
     File "<stdin>", line 1, in ?
    TypeError: 'str' object does not support item assignment
    >>> word[:1] = 'Splat'
    Traceback (most recent call last):
     File "<stdin>", line 1, in ?
    TypeError: 'str' object does not support slice assignment


    >>> 'x' + word[1:]
    'xelpA'
    >>> 'Splat' + word[4]
    'SplatA'


Negative Indices
----------------

    >>> word[-1]     # Das letzte Zeichen
    'A'
    >>> word[-2]     # Das vorletzte Zeichen
    'p'
    >>> word[-2:]    # Die letzten zwei Zeichen
    'pA'
    >>> word[:-2]    # Alles außer den letzten beiden Zeichen
    'Hel'

Achtung: -0 ist dasselbe wie 0.

    >>> word[-0]     # (da -0 gleich 0)
    'H'

.. note::
    Indizes können auch negative Zahlen sein --- dann wird von rechts nach links
    gezählt. Zum Beispiel

Fehler beim Zugriff
-------------------

    >>> word[-100:]
    'HelpA'
    >>> word[-10]    # Fehler
    Traceback (most recent call last):
     File "<stdin>", line 1, in ?
    IndexError: string index out of range



Listen
------

    >>> a = ['spam', 'eggs', 100, 1234]
    >>> a
    ['spam', 'eggs', 100, 1234]


Listen
------

    >>> a[0]
    'spam'
    >>> a[3]
    1234

.. rst-class:: build

    >>> a[-2]
    100
    >>> a[1:-1]
    ['eggs', 100]
    >>> a[:2] + ['bacon', 2*2]
    ['spam', 'eggs', 'bacon', 4]
    >>> 3*a[:3] + ['Boo!']
    ['spam', 'eggs', 100, 'spam', 'eggs', 100, 'spam', 'eggs', 100, 'Boo!']

Listen
------

    >>> a
    ['spam', 'eggs', 100, 1234]
    >>> a[2] = a[2] + 23
    >>> a
    ['spam', 'eggs', 123, 1234]

Listen
------

    >>> # Ein paar Elemente ersetzen:
    ... a[0:2] = [1, 12]
    >>> a
    [1, 12, 123, 1234]
    >>> # Ein paar entfernen:
    ... a[0:2] = []
    >>> a
    [123, 1234]
    >>> # Ein paar einfügen:
    ... a[1:1] = ['bletch', 'xyzzy']
    >>> a
    [123, 'bletch', 'xyzzy', 1234]
    >>> # (Eine Kopie von) sich selbst am Anfang einfügen:
    >>> a[:0] = a
    >>> a
    [123, 'bletch', 'xyzzy', 1234, 123, 'bletch', 'xyzzy', 1234]
    >>> # Die Liste leeren: Alle Elemente durch eine leere Liste  ersetzen
    >>> a[:] = []
    >>> a
    []

Länge einer Liste
-----------------

    >>> a = ['a', 'b', 'c', 'd']
    >>> len(a)
    4

Listen verschachteln
--------------------


    >>> q = [2, 3]
    >>> p = [1, q, 4]
    >>> len(p)
    3
    >>> p[1]
    [2, 3]
    >>> p[1][0]
    2

.. rst-class:: build

    >>> p[1].append('xtra')
    >>> p
    [1, [2, 3, 'xtra'], 4]
    >>> q
    [2, 3, 'xtra']

.. note::

   Beachte, dass im letzten Beispiel ``p[1]`` und ``q`` wirklich auf dasselbe
   Objekt zeigen!


   Dictionaries
   ------------

   .. rst-class:: build
   * Schüssel => Wert
   * auch bekannt als

       * "assoziativer Speicher"
       * "assoziative Arrays"
       * Hash
       * Map

   * jedes nicht veränderbares Objekt kann ein Schlüssel sein

   .. note::
      Keine Listen

   Dictionaries
   ------------

       >>> tel = {'jack': 4098, 'sape': 4139}
       >>> tel['guido'] = 4127
       >>> tel
       {'sape': 4139, 'guido': 4127, 'jack': 4098}
       >>> tel['jack']
       4098
       >>> del tel['sape']
       >>> tel['irv'] = 4127
       >>> tel
       {'guido': 4127, 'irv': 4127, 'jack': 4098}
       >>> list(tel.keys())
       ['irv', 'guido', 'jack']
       >>> sorted(tel.keys())
       ['guido', 'irv', 'jack']
       >>> 'guido' in tel
       True
       >>> 'jack' not in tel
       False

   Dictionaries: dict()
   --------------------


   Dictionaries direkt aus Sequenzen erstellen...

       >>> dict([('sape', 4139), ('guido', 4127), ('jack', 4098)])
       {'sape': 4139, 'jack': 4098, 'guido': 4127}

   .. rst-class:: build

   ...oder aus Keyword-Argumenten

      >>> dict(sape=4139, guido=4127, jack=4098)
      {'sape': 4139, 'jack': 4098, 'guido': 4127}


Erste Schritte zur Programmierung
---------------------------------

    >>> # Fibonacci-Folge:
    ... # Die Summe der letzten beiden Elemente ergibt das nächste
    ... a, b = 0, 1
    >>> while b < 10:
    ...     print(b)
    ...     a, b = b, a+b
    ...
    1
    1
    2
    3
    5
    8

.. note:

    Dieses Beispiel stellt ein paar neue Eigenschaften vor.

    * Die erste Zeile enthält eine *Mehrfachzuweisung* (*multiple assignment*): Die
      Variablen ``a`` und ``b`` bekommen gleichzeitig die neuen Werte 0 und 1. In der
      letzten Zeile wird sie erneut eingesetzt, um zu zeigen, dass zuerst alle
      Ausdrücke auf der rechten Seite ausgewertet werden, bevor irgendeine Zuweisung
      vorgenommen wird! Die Ausdrücke auf der rechten Seite werden von links nach
      rechts ausgewertet.

    * Die :keyword:`while` Schleife wird solange ausgeführt, wie die Bedingung
      (hier: ``b < 10``) wahr ist. In Python wie in C ist jede von Null verschiedene
      Zahl wahr (*True*), Null ist unwahr (*False*). Die Bedingung kann auch ein
      String- oder Listenwert sein, eigentlich sogar jede Sequenz. Alles mit einer
      von Null verschiedenen Länge ist wahr, leere Sequenzen sind unwahr. Die
      Bedingung im Beispiel ist ein einfacher Vergleich. Die normalen
      Vergleichsoperatoren werden wie in C geschrieben: ``<`` (kleiner als), ``>``
      (größer als), ``==`` (gleich), ``<=`` (kleiner oder gleich), ``>=`` (größer
      oder gleich) und ``!=`` (ungleich).

    * Der *Schleifenrumpf* ist *eingerückt* (*indented*): Durch Einrückung wird in
      Python eine Gruppierung vorgenommen. In der interaktiven Eingabeaufforderung
      muss man Tabs oder Leerzeichen für jede eingerückte Zeile eingeben. In der
      Praxis wird man kompliziertere Codestücke mit einem Texteditor vorbereiten und
      alle vernünftigen Editoren haben eine Möglichkeit, um automatisch einzurücken.
      Wenn eine zusammengesetzte Anweisung (*compound statement*) interaktiv
      eingegeben wird, muss eine Leerzeile darauf folgen, um anzuzeigen, dass sie
      komplett ist, da der Parser nicht erahnen kann, wenn man die letzte Zeile
      eingegeben hat. Beachte, dass jede Zeile in einem zusammengehörigen Block
      gleich eingerückt sein muss.

    * Die Funktion :func:`print` gibt den Wert des Ausdrucks aus, der ihr übergeben
      wurde. Die Ausgabe unterscheidet sich bei Mehrfachausdrücken, Fließkommazahlen
      und Zeichenketten von der Ausgabe, die man erhält, wenn man die Ausdrücke
      einfach so eingibt (wie wir es vorher in den Taschenrechnerbeispielen gemacht
      haben). Zeichenketten werden ohne Anführungszeichen ausgegeben, und bei Angabe
      mehrere Argumente wird zwischen je zwei Argumenten ein Leerzeichen eingefügt.
      So lassen sich einfache Formatierungen vornehmen, wie das Beispiel zeigt

        >>> i = 256 * 256
        >>> print('Der Wert von i ist', i)
        Der Wert von i ist 65536



:keyword:`if`-Anweisungen
-------------------------

Ein Beispiel zur :keyword:`if`-Anweisung ::

    >>> x = int(input("Please enter an integer: "))
    Please enter an integer: 42
    >>> if x < 0:
    ...      x = 0
    ...      print('Negative changed to zero')
    ... elif x == 0:
    ...      print('Zero')
    ... elif x == 1:
    ...      print('Single')
    ... else:
    ...      print('More')
    ...
    More


.. note::
    :keyword:`else`-Zweig oder :keyword:`elif`-Zweige sind optional. Im Unterschied
    zum :keyword:`else`-Zweig, der nur einmal vorkommen kann, ist eine Abfolge von
    mehreren :keyword:`elif`-Zweigen möglich; dadurch lassen sich verschachtelte
    Einrückungen vermeiden.  Eine Abfolge von :keyword:`if` ... :keyword:`elif` ...
    :keyword:`elif`-Zweigen ersetzt die ``switch``- oder ``case``-Konstrukte anderer
    Programmiersprachen.


:keyword:`for`-Anweisungen
--------------------------


    >>> # Die Längen einiger Zeichenketten ermitteln:
    ... a = ['Katze', 'Fenster', 'rauswerfen']
    >>> for x in a:
    ...     print(x, len(x))
    ...
    Katze 5
    Fenster 7
    rauswerfen 10

.. note::
    Die :keyword:`for`-Anweisung in Python unterscheidet sich ein wenig von der, die
    man von C oder Pascal her kennt. Man kann nicht nur über eine Zahlenfolge
    iterieren (wie in Pascal) oder lediglich Schrittweite und Abbruchbedingung
    festlegen (wie in C), sondern über eine beliebige Sequenz (also z. B. eine Liste
    oder Zeichenkette), und zwar in der Reihenfolge, in der die Elemente in der
    Sequenz vorkommen. Zum Beispiel: ::

Die Funktion :func:`range`
--------------------------

    >>> for i in range(5):
    ...     print(i)
    ...
    0
    1
    2
    3
    4

.. rst-class:: build

    >>> print(range(10))
    range(0, 10)

    >>> list(range(5))
    [0, 1, 2, 3, 4]


:keyword:`break`, :keyword:`continue` und :keyword:`else` bei Schleifen
-----------------------------------------------------------------------


    >>> for n in range(2, 10):
    ...     for x in range(2, n):
    ...         if n % x == 0:
    ...             print(n, 'equals', x, '*', n//x)
    ...             break
    ...     else:
    ...         # Schleife wurde durchlaufen, ohne dass ein Faktor gefunden wurde
    ...         print(n, 'is a prime number')
    ...
    2 is a prime number
    3 is a prime number
    4 equals 2 * 2
    5 is a prime number
    6 equals 2 * 3
    7 is a prime number
    8 equals 2 * 4
    9 equals 3 * 3

.. notes::
    Eine  :keyword:`break`-Anweisung in einem Schleifenrumpf bewirkt --- wie in C
    --- dass an dieser Stelle mit sofortiger Wirkung die sie unmittelbar umgebende
    Schleife verlassen wird.

    Entsprechend bewirkt die :keyword:`continue`-Anweisung --- ebenso von C
    entliehen --- , dass an dieser Stelle wieder in den Schleifenkopf "gesprungen"
    und die nächste Iteration ausgeführt wird.  Der noch folgende Teil des
    Schleifenrumpfs wird nicht mehr ausgeführt.

    Auch Schleifen-Anweisungen können einen :keyword:`else`-Zweig haben. Dieser wird
    genau dann ausgeführt, wenn die Schleife *nicht* durch eine
    :keyword:`break`-Anweisung abgebrochen wurde. Das folgende Beispiel zur
    Berechnung von Primzahlen veranschaulicht das.

:keyword:`pass`-Anweisungen
---------------------------

.. rst-class:: build

    >>> while True:
    ...     pass  # geschäftiges Warten auf den Tastatur-Interrupt (Strg+C)
    ...

    >>> class MyEmptyClass:
    ...     pass
    ...


    >>> def initlog(*args):
    ...     pass   # Implementieren nicht vergessen!
    ...


Funktionen definieren
---------------------

.. rst-class:: build

    >>> def fib(n):    # die Fibonacci-Folge bis n ausgeben
    ...     """Print the Fibonacci series up to n."""
    ...     a, b = 0, 1
    ...     while a < n:
    ...         print(a, end=' ')
    ...         a, b = b, a+b
    ...     print()
    ...

    >>> fib(2000)
    0 1 1 2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597

.. note::

  Das Schlüsselwort :keyword:`def` leitet die *Definition* einer Funktion ein.
  Darauf folgt der Funktionsname und eine Auflistung der formalen Parameter, die
  allerdings auch leer sein kann. Die Anweisungen, die den Funktionskörper bilden,
  beginnen in der nächsten Zeile und müssen eingerückt sein.

  Die erste Anweisung des Funktionskörpers kann auch ein Zeichenkettenliteral
  sein, ein so genannter Dokumentationsstring der Funktion, auch :dfn:`Docstring`
  genannt. (Mehr zu Docstrings kann im Abschnitt :ref:`tut-docstrings`
  nachgelesen werden.) Es gibt Werkzeuge, die Docstrings verwenden, um automatisch
  Online-Dokumentation oder gedruckte Dokumentation zu erzeugen oder es dem
  Anwender ermöglichen, interaktiv den Code zu durchsuchen. Die Verwendung von
  Docstrings ist eine gute Konvention, an die man sich bei der Programmierung nach
  Möglichkeit halten sollte.

  Beim *Aufruf* einer Funktion kommt es zur Bildung eines lokalen Namensraums, der
  sich auf alle Bezeichner erstreckt, die im Funktionsrumpf (durch Zuweisung oder
  als Elemente der Parameterliste) neu definiert werden. Diese Bezeichner werden
  mit den ihnen zugeordneten Objekten in einer lokalen Symboltabelle abgelegt.

  Wenn im Funktionsrumpf ein Bezeichner vorkommt, wird der Name zunächst in der
  lokalen Symboltabelle gesucht, danach in den lokalen Symboltabellen der
  umgebenden Funktionen, dann in der globalen Symboltabelle und schließlich in der
  Symboltabelle der eingebauten Namen. Darum ist es ohne weiteres nicht möglich,
  einer globalen Variablen innerhalb des lokalen Namensraums einer Funktion einen
  Wert zuzuweisen.  Dadurch würde stattdessen eine neue, namensgleiche lokale
  Variable definiert, die die namensgleiche globale Variable überdeckt und dadurch
  auch den lesenden Zugriff auf diese globale Variable verhindert. Ein lesender
  Zugriff auf globale Variablen ist ansonsten immer möglich, ein schreibender
  Zugriff nur unter Verwendung der :keyword:`global`-Anweisung.

  Die konkreten Parameter (Argumente), die beim Funktionsaufruf übergeben werden,
  werden den formalen Parametern der Parameterliste zugeordnet und gehören damit
  zur lokalen Symboltabelle der Funktion. Das heißt, Argumente werden über *call
  by value* übergeben (wobei der *Wert* allerdings immer eine *Referenz* auf ein
  Objekt ist, nicht der Wert des Objektes selbst) [#]_. Wenn eine Funktion eine
  andere Funktion aufruft, wird eine neue lokale Symboltabelle für diesen Aufruf
  erzeugt.

  Eine Funktionsdefinition fügt den Funktionsnamen in die lokale Symboltabelle
  ein. Der Wert des Funktionsnamens hat einen Typ, der vom Interpreter als
  benutzerdefinierte Funktion erkannt wird. Dieser Wert kann einem anderen Namen
  zugewiesen werden, der dann ebenfalls als Funktion genutzt werden kann und so
  als Möglichkeit zur Umbenennung dient. ::

      >>> fib
      <function fib at 10042ed0>
      >>> f = fib
      >>> f(100)
      0 2 1 2 3 5 8 13 21 34 55 89

  Wer Erfahrung mit anderen Programmiersprachen hat, wird vielleicht einwenden,
  dass ``fib`` gar keine Funktion, sondern eine Prozedur ist, da sie keinen Wert
  zurückgibt.  Tatsächlich geben aber auch Funktionen *ohne* eine
  :keyword:`return`-Anweisung einen Wert zurück, wenn auch einen eher
  langweiligen, nämlich den eingebauten Namen ``None`` ("nichts").  Die Ausgabe
  des Wertes ``None`` wird normalerweise vom Interpreter unterdrückt, wenn es der
  einzige Wert wäre, der ausgegeben wird. Möchte man ihn sehen, kann man ihn
  mittels :func:`print` sichtbar machen.::

Prozeduren vs. Funktionen
-------------------------

    >>> fib(0)
    >>> print(fib(0))
    None

Funktionen
----------

    >>> def fib2(n):
    ...     """Return a list containing the Fibonacci series up to n."""
    ...     result = list()
    ...     a, b = 0, 1
    ...     while a < n:
    ...         result.append(a)
    ...         a, b = b, a + b
    ...     return result
    ...
    >>> f100 = fib2(100)
    >>> f100
    [0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89]

.. note::

  Dieses Beispiel zeigt einige neue Eigenschaften von Python:

  *   Die :keyword:`return`-Anweisung gibt einen Wert von einer Funktion
      zurück. Ohne einen Ausdruck als Argument gibt :keyword:`return` ``None``
      zurück; das gleiche gilt, wenn eine :keyword:`return`-Anweisung fehlt.

  *   Die Anweisung ``result.append(a)`` ruft eine *Methode* des Listenobjektes in
      ``result`` auf. Eine Methode ist eine Funktion, die zu einem Objekt 'gehört'
      und wird mittels Punktnotation (``obj.methodname``) dargestellt. Dabei ist
      ``obj`` irgendein Objekt (es kann auch ein Ausdruck sein) und ``methodname``
      der Name einer Methode, die vom Typ des Objektes definiert wird.
      Unterschiedliche Typen definieren verschiedene Methoden. Methoden
      verschiedener Typen können denselben Namen haben ohne doppeldeutig zu sein.
      (Es ist auch möglich, eigene Objekttypen zu erstellen, indem man *Klassen*
      benutzt, siehe :ref:`tut-classes`.) Die Methode :meth:`append`, die im
      Beispiel gezeigt wird, ist für Listenobjekte definiert. Sie hängt ein neues
      Element an das Ende der Liste an. Im Beispiel ist es äquivalent zu ``result
      = result + [a]``, aber effizienter.

.. _tut-defaultargs:

Standardwerte für Argumente
---------------------------

.. code:: python

    def ask_ok(prompt, retries=4, complaint='Bitte Ja oder Nein!'):
       while True:
           ok = input(prompt)
           if ok in ('j', 'J', 'ja', 'Ja'): return True
           if ok in ('n', 'N', 'ne', 'Ne', 'Nein'): return False
           retries = retries - 1
           if retries < 0:
               raise IOError('Benutzer abgelehnt!')
           print(complaint)

.. rst-class:: build

* ``ask_ok("Willst du wirklich aufhören?")``

* ``ask_ok("Willst du die Datei überschreiben?", 2)``

* ``ask_ok("Willst du die Datei überschreiben?", 2, "Komm schon, nur Ja oder
  Nein")``


Keyword-Argumente
-----------------

.. code:: python

    def ask_ok(prompt, retries=4, complaint='Bitte Ja oder Nein!'):
       while True:
           ok = input(prompt)
           if ok in ('j', 'J', 'ja', 'Ja'): return True
           if ok in ('n', 'N', 'ne', 'Ne', 'Nein'): return False
           retries = retries - 1
           if retries < 0:
               raise IOError('Benutzer abgelehnt!')
           print(complaint)

.. rst-class:: build

* ``ask_ok("Datei überschreiben", retries=2)``

* ``ask_ok("Datei überschreiben", complaint="Komm schon, nur Ja oder Nein")``


Beliebig lange Argumentlisten
-----------------------------

    >>> def concat(*args, sep="/"):
    ...    return sep.join(args)
    ...
    >>> concat("Erde", "Mars", "Venus")
    'Erde/Mars/Venus'
    >>> concat("Erde", "Mars", "Venus", sep=".")
    'Erde.Mars.Venus'


Argumentlisten auspacken
------------------------

    >>> list(range(3, 6))   # normaler Aufruf mit getrennten Argumenten
    [3, 4, 5]
    >>> args = [3, 6]
    >>> list(range(*args))  # Aufruf mit Argumenten, die aus einer Liste ausgepackt werden
    [3, 4, 5]


Lambda-Form - anonyme Funktion
------------------------------

    >>> def make_incrementor(n):
    ...     return lambda x: x + n
    ...
    >>> add42 = make_incrementor(42)
    >>> add42(0)
    42
    >>> add42(1)
    43


Dokumentationsstrings
---------------------


    >>> def my_function():
    ...     """Do nothing, but document it.
    ...     No, really, it doesn't do anything.
    ...     """
    ...     pass
    ...
    >>> print(my_function.__doc__)
    Do nothing, but document it.
       No, really, it doesn't do anything.



:pep:`8`
--------

.. rst-class:: build

* 4 Leerzeichen, keine Tabs

* maximale Zeilenlänge: 79 Zeichen

* Leerzeilen

* eigene Zeile für Kommentare, sofern möglich

* Docstrings

* Leerzeichen um Operatoren herum und nach Kommas, jedoch nicht direkt
  innerhalb von Klammerkonstrukten: ``a = f(1, 2) + g(3, 4)``

* ``CamelCase`` für Klassen

* ``klein_geschrieben_mit_unterstrichen`` für Funktionen und Methoden

* UTF-8 -- oder sogar einfaches ASCII

* möglichst keine nicht-ASCII-Zeichen in Bezeichnern


Datenstrukturen
---------------

Mehr zu Listen
--------------


.. rst-class:: build

    >>> a = [66.25, 333, 333, 1, 1234.5]
    >>> print(a.count(333), a.count(66.25), a.count('x'))
    2 1 0

    >>> a.insert(2, -1)
    >>> a.append(333)
    >>> a
    [66.25, 333, -1, 333, 1, 1234.5, 333]

    >>> a.index(333)
    1

    >>> a.remove(333)
    >>> a
    [66.25, -1, 333, 1, 1234.5, 333]

Mehr zu Listen
--------------

.. rst-class:: build

    >>> a.reverse()
    >>> a
    [333, 1234.5, 1, 333, -1, 66.25]

    >>> a.sort()
    >>> a
    [-1, 1, 66.25, 333, 333, 1234.5]

List Comprehensions
-------------------

Listen aus Listen erzeugen

    >>> vec = [2, 4, 7]
    >>> vec3 = []
    >>> for x in vec:
    ...     vec3.append(3*x)
    >>> vec3
    [6, 12, 21]


List Comprehensions
-------------------

    >>> vec = [2, 4, 7]
    >>> [3*x for x in vec]
    [6, 12, 21]


Jetzt wird's ein wenig ausgefallener::

    >>> [[x, x**2] for x in vec]
    [[2, 4], [4, 16], [7, 49]]


List Comprehensions (2)
-----------------------
Hier wenden wir einen Methodenaufruf auf jedes Objekt in der Sequenz an::


    >>> freshfruits = ['  banana', '  loganberry ', 'passion fruit  ']
    >>> [fruit.strip() for fruit in freshfruits]
    ['banana', 'loganberry', 'passion fruit']

List Comprehensions mit if
--------------------------
Indem wir eine :keyword:`if`-Klausel anwenden, können wir die Elemente filtern::

   >>> [3*x for x in vec if x > 3]
   [12, 18]
   >>> [3*x for x in vec if x < 2]
   []


Verschachtelte List Comprehensions
----------------------------------

Lese von rechts nach links

    >>> mat = [
    ...        [1, 2, 3],
    ...        [4, 5, 6],
    ...        [7, 8, 9],
    ...       ]

    >>> print([[row[i] for row in mat] for i in [0, 1, 2]])
    [[1, 4, 7], [2, 5, 8], [3, 6, 9]]


.. note::

    Beispiel: 3x3 Matrix invertieren

    Eine ausführlichere Version dieses Schnipsels zeigt den Ablauf deutlich::

        for i in [0, 1, 2]:
            for row in mat:
                print(row[i], end="")
            print()

    Im echten Leben sollte man aber eingebaute Funktionen komplexen Anweisungen
    vorziehen. Die Funktion :func:`zip` würde in diesem Fall gute Dienste leisten

        >>> list(zip(*mat))
        [(1, 4, 7), (2, 5, 8), (3, 6, 9)]

List comprehensions
-------------------
Hier sind ein paar verschachtelte :keyword:`for`-Schleifen und anderes
ausgefallenes Verhalten::

   >>> vec1 = [2, 4, 6]
   >>> vec2 = [4, 3, -9]
   >>> [x*y for x in vec1 for y in vec2]
   [8, 6, -18, 16, 12, -36, 24, 18, -54]
   >>> [x+y for x in vec1 for y in vec2]
   [6, 5, -7, 8, 7, -5, 10, 9, -3]
   >>> [vec1[i]*vec2[i] for i in range(len(vec1))]
   [8, 12, -54]

List Comprehensions können auf komplexe Ausdrücke und verschachtelte Funktionen
angewendet werden::

   >>> [str(round(355/113, i)) for i in range(1, 6)]
   ['3.1', '3.14', '3.142', '3.1416', '3.14159']

Dict Comprehensions
-------------------

  >>> {x: x**2 for x in (2, 4, 6)}
  {2: 4, 4: 16, 6: 36}
  >>> {w: len(w) for w in ['Linux', 'Windows', 'Mac OS X']}
  {'Windows': 7, 'Mac OS X': 8, 'Linux': 5}


Die :keyword:`del`-Anweisung
----------------------------

Löschen von Listenelement nach index::

    >>> a = [-1, 1, 66.25, 333, 333, 1234.5]
    >>> del a[0]
    >>> a
    [1, 66.25, 333, 333, 1234.5]
    >>> del a[2:4]
    >>> a
    [1, 66.25, 1234.5]
    >>> del a[:]
    >>> a
    []

Die :keyword:`del`-Anweisung (2)
--------------------------------
Löschen von ganzen Variablen::

   >>> del a
   >>> a
   Traceback (most recent call last):
     File "<stdin>", line 1, in <module>
   NameError: name 'a' is not defined


Tupel
-----


Ein Tupel besteht aus mehreren Werten, die durch Kommas von einander getrennt
sind, beispielsweise::


    >>> t = 12345, 54321, 'Hallo!'
    >>> t[0]
    12345
    >>> t
    (12345, 54321, 'Hallo!')
    >>> # Tupel können verschachtelt werden:
    ... u = t, (1, 2, 3, 4, 5)
    >>> u
    ((12345, 54321, 'Hallo!'), (1, 2, 3, 4, 5))

.. note::

   * Listen und Zeichenketten sind Sequenztypen, Tupel auch

Tupel (2)
---------

Vorsicht bei Tupeln der Länge 0 und 1

    >>> empty = ()
    >>> singleton = 'Hallo',    # <-- das angehängte Komma nicht vergessen
    >>> x = (0)
    >>> len(empty)
    0
    >>> len(singleton)
    1
    >>> singleton
    ('Hallo',)
    >>> len(x)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: object of type 'int' has no len()

Tupel packen und entpacken
--------------------------

   >>> t = 12345, 54321, 'Hallo!'
   >>> x, y, z = t

Mengen (Sets)
-------------

* ungeordnete Sammlung ohne doppelte Elemente
* unterstützen mathematische Operationen

  * Vereinigungsmenge
  * Schnittmenge
  * Differenz
  * symmetrische Differenz.

Mengen (Sets)
-------------

   >>> basket = {'Apfel', 'Orange', 'Apfel', 'Birne', 'Orange', 'Banane'}
   >>> print(fruit)                       # zeigt, dass die Duplikate entfernt wurden
   {'Orange', 'Birne', 'Apfel', 'Banane'}
   >>> 'Orange' in basket                 # schnelles Testen auf Mitgliedschaft
   True
   >>> 'Fingerhirse' in basket
   False

Mengen (Sets)
-------------

   >>> a = set('abracadabra')
   >>> b = set('alacazam')
   >>> a                                  # einzelne Buchstaben in a
   {'a', 'r', 'b', 'c', 'd'}
   >>> a - b                              # in a aber nicht in b
   {'r', 'd', 'b'}
   >>> a | b                              # in a oder b
   {'a', 'c', 'r', 'd', 'b', 'm', 'z', 'l'}
   >>> a & b                              # sowohl in a, als auch in b
   {'a', 'c'}
   >>> a ^ b                              # entweder in a oder b
   {'r', 'd', 'b', 'm', 'z', 'l'}

Set Comprehension
-----------------

   >>> a = {x for x in 'abracadabra' if x not in 'abc'}
   >>> a
   {'r', 'd'}

Schleifentechniken für Dictionaries
-----------------------------------

    >>> knights = {'Gallahad': 'der Reine', 'Robin': 'der Mutige'}

    >>> for k in knights:
    >>>     print (k, knights[k])
    ...
    Gallahad der Reine
    Robin der Mutige

    >>> for k, v in knights.items():
    ...     print(k, v)
    ...
    Gallahad der Reine
    Robin der Mutige

Schleifentechniken für Sequenzen
--------------------------------

    >>> i = 0
    >>> for v in ['tic', 'tac', 'toe']:
    ...     print(i, v)
    ...     i += 1
    ...
    0 tic
    1 tac
    2 toe


    >>> for i, v in enumerate(['tic', 'tac', 'toe']):
    ...     print(i, v)
    ...
    0 tic
    1 tac
    2 toe

Module
------

Datei, die Python-Definitionen und -Anweisungen beinhaltet

Module
------

.. code-block:: python

    # fibo.py
    # Fibonacci-Zahlen-Modul

    def fib(n):    # schreibe Fibonacci-Folge bis n
        a, b = 0, 1
        while b < n:
            print(b, end=' ')
            a, b = b, a+b
        print()

    def fib2(n): # gib die Fibonacci-Folge zurück bis n
        result = []
        a, b = 0, 1
        while b < n:
            result.append(b)
            a, b = b, a+b
        return result

Module
------

.. rst-class:: build

    >>> import fibo

    >>> fibo.fib(1000)
    1 1 2 3 5 8 13 21 34 55 89 144 233 377 610 987
    >>> fibo.fib2(100)
    [1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89]
    >>> fibo.__name__
    'fibo'

    >>> from fibo import fib, fib2
    >>> fib(500)
    1 1 2 3 5 8 13 21 34 55 89 144 233 377

    >>> from fibo import *

Module als Skript aufrufen
--------------------------

.. code-block:: python

    if __name__ == "__main__":
        import sys
        fib(int(sys.argv[1]))

In der Kommandozeile::

    $ python fibo.py 50
    1 1 2 3 5 8 13 21 34

Beim Import::

    >>> import fibo
    >>>

Pakete
------

.. code::

    sound/                             Top-level package
             __init__.py               Initialize the sound package
             formats/                  Subpackage for file format conversions
                     __init__.py
                     wavread.py
                     wavwrite.py
                     aiffread.py
                     aiffwrite.py
                     auread.py
                     auwrite.py
                     ...
             effects/                  Subpackage for sound effects
                     __init__.py
                     echo.py
                     surround.py
                     reverse.py
                     ...
             filters/                  Subpackage for filters
                     __init__.py
                     equalizer.py
                     vocoder.py
                     karaoke.py
                     ...

Pakete
------

.. rst-class:: build

    >>> import sound.effects.echo
    >>> sound.effects.echo.echofilter(input, output, delay=0.7, atten=4)

    >>> from sound.effects import echo
    >>> echo.echofilter(input, output, delay=0.7, atten=4)

    >>> from sound.effects.echo import echofilter
    >>> echofilter(input, output, delay=0.7, atten=4)

Referenzen innerhalb des Paketes
--------------------------------

.. code-block:: python

    from . import echo
    from .. import formats
    from ..filters import equalizer


Fehler und Ausnahmen
--------------------

Syntaxfehler

   >>> while True print('Hallo Welt')
     File "<stdin>", line 1, in ?
       while True print('Hallo Welt')
                      ^
   SyntaxError: invalid syntax


Fehler und Ausnahmen
--------------------

Ausnahmen

   >>> 10 * (1/0)
   Traceback (most recent call last):
     File "<stdin>", line 1, in ?
   ZeroDivisionError: int division or modulo by zero
   >>> 4 + spam*3
   Traceback (most recent call last):
     File "<stdin>", line 1, in ?
   NameError: name 'spam' is not defined
   >>> '2' + 2
   Traceback (most recent call last):
     File "<stdin>", line 1, in ?
   TypeError: Can't convert 'int' object to str implicitly

Klassen
-------

::

   class Host:
       id = 42
       def __init__(self, mac)
           self.mac = mac

       def get_dhcp_lease():
           pass


Vererbung
---------

::

    class Host:
        id = 42
        def __init__(self, mac)
            self.mac = mac

        def get_dhcp_lease():
            pass

    class Workstation(Host):
        def install_updates():
            pass


Mehrfachvererbung
---------

::

   class Host:
       id = 42
       def __init__(self, mac)
           self.mac = mac

       def get_dhcp_lease():
           pass

   class Workstation(Host):
       def install_updates():
           pass

   class Appliance:
       def turn_off():
           pass

   class SmartFridge(Appliance, Host):
       pass


<EOF>
-----

* @danielhepper
* https://github.com/dhepper/froscon2016-python-intro
* Basierend auf http://py-tutorial-de.readthedocs.io/de/python-3.3/
* Lizenz: Apache License, Version 2.0
