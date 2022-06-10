Zahlen
======

Die vier Zahlentypen von Python sind ganze Zahlen, Gleitkommazahlen, komplexe
Zahlen und Boolesche Zahlen:

+-----------------------+-----------------------------------------------+
| Typ                   | Beispiele                                     |
+=======================+===============================================+
| Ganzzahlen            | ``-1``, ``42``, ``90000000``                  |
+-----------------------+-----------------------------------------------+
| Gleitkommazahlen      | ``90000000.0``, ``-0.005``, ``9e7``, ``-5e-3``|
+-----------------------+-----------------------------------------------+
| Komplexe Zahlen       | ``3 + 2j``, ``-4- 2j``, ``4.2 + 6.3j``        |
+-----------------------+-----------------------------------------------+
| Boolesche Zahlen      | ``True``, ``False``                           |
+-----------------------+-----------------------------------------------+

Sie können mit den arithmetischen Operatoren manipuliert werden:

+-----------------------+-----------------------------------------------+
| Operator              | Beschreibung                                  |
+=======================+===============================================+
| ``+``                 | Addition                                      |
+-----------------------+-----------------------------------------------+
| ``-``                 | Subtraktion                                   |
+-----------------------+-----------------------------------------------+
| ``*``                 | Multiplikation                                |
+-----------------------+-----------------------------------------------+
| ``/``, ``//``         | Division [#]_                                 |
+-----------------------+-----------------------------------------------+
| ``**``                | Potenzierung                                  |
+-----------------------+-----------------------------------------------+
| ``%``                 | Modulus                                       |
+-----------------------+-----------------------------------------------+

.. [#] Die Division ganzer Zahlen mit ``/`` führt zu einem Float, und die
       Division ganzer Zahlen mit ``//`` führt zu einer Ganzzahl, die
       abgeschnitten wird.

.. note::
   Ganzzahlen können unbegrenzt groß sein, begrenzt nur durch den verfügbaren
   Speicher.

Beispiele:

.. code-block:: python

    >>> 8 + 3 - 5 * 3
    -4
    >>> 8 / 3
    2.6666666666666665
    >>> 8 // 3
    2
    >>> x = 4.2 ** 3.4
    >>> x
    131.53689544409096
    >>> 9e7 * -5e-3
    -450000.0
    >>> -5e-3 ** 3
    -1.2500000000000002e-07

Die folgenden Beispiele verwenden komplexe Zahlen:

.. code-block:: python

    >>> (5+3j) ** (3+5j)
    (-7.04464115622119-11.276062812695923j)

.. code-block:: python

    >>> x = (5+3j) * (6+8j)
    >>> x
    (6+58j)
    >>> x.real
    6.0
    >>> x.imag
    58.0

Komplexe Zahlen bestehen aus einem Realteil und einem Imaginärteil mit dem
Suffix ``j``. Im vorangehenden Code ist die Variable ``x`` einer komplexen Zahl
zugeordnet. Ihr könnt ihren „realen“ Teil mit der Attributschreibweise
``x.real`` und den „imaginären“ Teil mit ``x.imag`` erhalten.

Mehrere eingebaute Funktionen können mit Zahlen arbeiten:

:func:`python3:abs`
    gibt den absoluten Wert einer Zahl zurück. Dabei kann as Argument kann eine
    Ganzzahl, eine Fließkommazahl oder ein Objekt sein, das ``__abs__()``
    implementiert. Bei komplexen Zahlen als Argument wird ihr Betrag
    zurückgegeben.
:func:`python3:divmod`
    nimmt zwei (nicht-komplexe) Zahlen als Argumente und gibt ein Zahlenpaar
    zurück, das aus ihrem Quotienten und dem Rest besteht, wenn eine ganzzahlige
    Division verwendet wird.
:class:`python3:float`
    Gibt eine Fließkommazahl zurück, die aus einer Zahl oder Zeichenkette ``x``
    gebildet wird.
:func:`python3:hex`
    konvertiert eine Integer-Zahl in eine klein geschriebene hexadezimale
    Zeichenkette mit dem Präfix ``0x``.
:class:`python3:int`
    gibt ein Integer-Objekt zurück, das aus einer Zahl oder Zeichenkette ``x``
    konstruiert wurde, oder ``0``, wenn keine Argumente angegeben werden.
:func:`python3:max`
    gibt das größte Element in einem :term:`python3:iterable` oder das größte
    von zwei oder mehr Argumenten zurück.
:func:`python3:min`
    gibt das kleinste Element in einem Iterable oder das kleinste von zwei oder
    mehr Argumenten zurück.
:func:`python3:oct`
    konvertiert eine Integer-Zahl in eine oktale Zeichenkette mit dem Präfix
    ``0o``. Das Ergebnis ist ein gültiger Python-Ausdruck. Wenn ``x`` kein
    Python :func:`int`-Objekt ist, muss es eine ``__index__()``-Methode
    definieren, die eine ganze Zahl zurückgibt.
:func:`python3:pow`
    gibt *base* als Potenz von *exp* zurück.
:func:`python3:round`
    gibt eine Zahl zurück, die auf *ndigits* nach dem Dezimalpunkt gerundet ist.
    Wird *ndigits* weggelassen oder ist *None*, wird die nächstgelegene Ganzzahl
    zur Eingabe zurückgegeben.

Außerdem gibt es das Bibliotheksmodul :doc:`cmath <python3:library/cmath>` (das
Funktionen für komplexe Zahlen enthält) und das Bibliotheksmodul :doc:`math
<python3:library/math>` (das Funktionen für die anderen drei Typen enthält):

.. code-block:: python

    >>> round(1.49)
    1

.. code-block:: python

    >>> import math
    >>> math.ceil(1.49)
    2

Eingebaute Funktionen sind immer verfügbar und werden mit einer Standard-Syntax
für Funktionsaufrufe aufgerufen. Im vorangegangenen Code wird ``round`` mit
einem Float als Eingangsargument aufgerufen.

Die Funktionen in Bibliotheksmodulen werden über die Anweisung ``import``
verfügbar gemacht. Im letzten Beispiel wird das Modul der Bliothek ``math``
importiert, und seine Funktion ``ceil`` wird mit der Attributschreibweise
aufgerufen: :samp:`MODUL.FUNKTION(ARGUMENT)`.

In den folgenden Beispielen werden Boolesche Werte verwendet:

.. code-block:: python

    >>> x = False
    >>> x
    False
    >>> not x
    True

.. code-block:: python

    >>> y = True * 2
    >>> y
    2

Abgesehen von ihrer Darstellung als ``True`` und ``False`` verhalten sich
Boolesche Werte wie die Zahlen ``1`` (``True``) und ``0`` (``False``).
