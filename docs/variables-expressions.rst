Variablen und Ausdrücke
=======================

Variablen
---------

Der am häufigsten verwendete Befehl in Python ist die Zuweisung. Der Python-Code
um eine Vairiable namens ``x`` zu erstellen, die den Wert ``π`` erhalten soll,
lautet:

.. code-block:: python

    >>> x = 3.14159

In Python ist, anders als in vielen anderen Programmiersprachen, weder eine
Variablendeklaration noch ein Zeilenendebegrenzer notwendig. Die Zeile wird
durch das Ende der Zeile abgeschlossen. Variablen werden automatisch erstellt,
wenn sie zum ersten Mal zugewiesen werden.

.. note::
   In Python sind Variablen Label, die auf Objekte verweisen. Eine beliebige
   Anzahl von Label können sich auf dasselbe Objekt beziehen, und wenn sich
   dieses Objekt ändert, ändert sich auch der Wert, auf den sich all diese
   Variablen beziehen. Um besser zu verstehen, was das bedeutet, seht euch das
   folgende Beispiel an:

   .. code-block:: python

      >>> x = [1, 2, 3]
      >>> y = x
      >>> y[0] = 4
      >>> print(x)
      [4, 2, 3]

   Variablen können sich jedoch auch auf Konstanten beziehen:

   .. code-block:: python

      >>> x = 1
      >>> y = x
      >>> z = y
      >>> y = 4
      >>> print(x,y,z)
      1 4 1

   In diesem Fall verweisen nach der dritten Zeile ``x``, ``y`` und ``z`` alle
   auf dasselbe unveränderlichee Integer-Objekt mit dem Wert ``1``. Die nächste
   Zeile, ``y = 4``, bewirkt, dass ``y`` auf das Integer-Objekt ``4`` verweist,
   dies ändert jedoch nicht die Referenzen von ``x`` oder ``z``.

Python-Variablen können auf jedes beliebige Objekt gesetzt werden, während in
vielen anderen Sprachen Variablen nur im deklarierten Typ gespeichert werden
können.

Variablennamen unterscheiden Groß- und Kleinschreibung und können jedes
alphanumerische Zeichen sowie Unterstriche enthalten, müssen aber mit einem
Buchstaben oder Unterstrich beginnen.

Ausdrücke
---------

Python unterstützt arithmetische und ähnliche Ausdrücke. Der folgende Code
berechnet den Durchschnitt von ``x`` und ``y`` und speichert das Ergebnis in der
Variablen ``z``:

.. code-block:: python

    >>> x = 1
    >>> y = 2
    >>> z = (x + y) / 2

.. note::
   Arithmetische Operatoren, die nur ganze Zahlen verwenden, geben nicht immer
   eine ganze Zahl zurück. Ab Python 3 gibt die Division eine Fließkommazahl
   zurück. Wenn die traditionelle Ganzzahldivision mit einer Ganzzahl
   zurückgegeben werden soll, könnt ihr stattdessen ``//`` verwenden.
