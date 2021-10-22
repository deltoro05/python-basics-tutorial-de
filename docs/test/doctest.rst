Doctest
=======

Das Python-Modul  :doc:`doctest <python3:library/doctest>` prüft, ob die in
einem Docstring angegebenen Tests erfüllt sind.

#. In :download:`arithmetic.py` könnt ihr folgenden Docstring hinzufügen:

   .. literalinclude:: arithmetic.py
      :language: python
      :lines: 2-5
      :lineno-start: 2

#. Anschließend könnt ihr in testen mit:

   .. code-block:: console

    $ python -m doctest arithmetic.py -v
    Trying:
        add(7,6)
    Expecting:
        13
    ok
    1 items had no tests:
        arithmetic
    1 items passed all tests:
       1 tests in arithmetic.add
    1 tests in 2 items.
    1 passed and 0 failed.
    Test passed.
    
#. Wenn ihr einen Doctest innerhalb eines Moduls durchführen wollt, solltet ihr
   die folgenden Zeilen hinzufügen:

   .. literalinclude:: arithmetic.py
      :language: python
      :lines: 29-31
      :lineno-start: 29
