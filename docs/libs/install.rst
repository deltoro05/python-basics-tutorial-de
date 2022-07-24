Hinzufügen weiterer Python-Bibliotheken
=======================================

Obwohl Pythons :doc:`batteries`-Philosophie bedeutet, dass ihr mit der
Standardinstallation von Python bereits eine Menge machen könnt, wird
unweigerlich die Situation kommen, in der ihr eine Funktionalität benötigt,
die nicht in Python enthalten ist. Dieser Abschnitt gibt einen Überblick über
die euch dann zur Verfügung stehenden Möglichkeiten.

Wenn ihr Glück habt, findet ihr die zusätzlich benötigte Funktionalität in einem
Paket für euer Betriebssystem – mit einem ausführbaren Windows- oder
macOS-Installationsprogramm oder einem Paket für eure Linux-Distribution.

Dies ist eine der einfachsten Möglichkeiten, eine Bibliothek zu eurer
Python-Installation hinzuzufügen, da sich das Installationsprogramm oder euer
Paketmanager um alle Details kümmert, um das Modul korrekt zu eurem System
hinzuzufügen. Im Allgemeinen sind solche vorgefertigten Pakete jedoch nicht die
Regel für Python-Software.

Installation von Python-Bibliotheken mit ``pip`` und ``venv``
-------------------------------------------------------------

Wenn ihr ein Modul eines Drittanbieters benötigt, das nicht für eure Plattform
vorgefertigt ist, müsst ihr euch an dessen Quelldistribution wenden. Dies bringt
jedoch zwei Probleme mit sich:

#. Um die Quelldistribution zu installieren, müsst ihr sie finden und
   herunterladen.
#. Es werden bestimmte Python-Pfade und Berechtigungen eures Systems erwartet.

Python bietet :term:`pip` als aktuelle Lösung für beide Probleme an. ``pip``
versucht, das Modul im :term:`Python Package Index (PyPI)` zu finden, lädt es
und alle Abhängigkeiten herunter und kümmert sich um die Installation. Die
grundlegende Syntax von ``pip`` ist recht einfach: um :abbr:`z.B. (zum
Beispiel)` die beliebte ``requests``-Bibliothek von der Kommandozeile aus zu
installieren, müsst ihr nur Folgendes tun:

.. code-block:: console

    $ python3.8 -m pip install requests

Wenn ihr eine bestimmte Version eines Pakets angeben wollt, könnt ihr die
Versionsnummern einfach anhängen:

.. code-block:: console

    $ python3.8 -m pip install requests==2.28.1

oder

.. code-block:: console

    $ python3.8 -m pip install requests>=2.28.0

Installieren mit der ``--user``-Option 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Häufig werdet ihr ein Python-Paket jedoch nicht in der Hauptinstanz von Python
installieren können oder wollen. Vielleicht benötigt ihr eine aktuellere Version
einer Bibliothek, aber eine andere Anwendung benötigt noch eine ältere Version.
Oder vielleicht habt ihr keine ausreichenden Administratorrechte, um das
Standard-Python des Systems zu ändern. In solchen Fällen besteht eine
Möglichkeit darin, die Bibliothek mit dem ``--user``-Flag zu installieren:
dieses installiert die Bibliothek in das Home-Verzeichnis, wo es dann allerdings
auch nur für euch selbst nutzbar ist:

.. code-block:: console

    $ python3.8 -m pip install --user requests

.. seealso::

   * :doc:`python3:installing/index`

Virtuelle Umgebungen
~~~~~~~~~~~~~~~~~~~~

Es gibt jedoch noch eine bessere Möglichkeit, wenn ihr die Installation von
Bibliotheken im Python-System vermeiden wollt. Diese Option wird als *virtuelle
Umgebung* (``virtualenv``) bezeichnet. Sie ist eine in sich geschlossene
Verzeichnisstruktur, die sowohl eine Installation von Python als auch die
zusätzlichen Pakete enthält. Da die gesamte Python-Umgebung in der virtuellen
Umgebung enthalten ist, können die dort installierten Bibliotheken und Module
nicht mit denen im Hauptsystem oder in anderen virtuellen Umgebungen
kollidieren, so dass verschiedene Anwendungen unterschiedliche Versionen von
Python und seinen Paketen verwenden können. Das Erstellen und Verwenden einer
virtuellen Umgebung erfolgt in zwei Schritten:

#. Zuerst erstellen wir die Umgebung:

   .. code-block:: console

      $ python3.8 -m venv myenv

   Hiermit wird die Umgebung mit Python und ``pip`` in einem Verzeichnis namens
   ``myenv`` erstellt.

#. Anschließend könnt ihr Python-Pakete nur für diese virtuelle Umgebung
   installieren:

   .. tab:: Linux/macOS

      .. code-block:: console

         $ cd myenv
         $ bin/python3.8 -m pip install requests

   .. tab:: Windows

      .. code-block:: console

         > cd myenv
         > Scripts\python.exe -m pip install requests

   .. note::
      Die Python-Version, die ihr zum Erstellen der Umgebung verwendet habt, ist
      die Standard-Python-Version für diese Umgebung, so dass ihr statt
      ``python3`` oder ``python3.8`` einfach ``python`` verwenden könnt.

Virtuelle Umgebungen sind sehr nützlich und gängige Praxis für die Verwaltung
von Projekten und deren Abhängigkeiten, insbesondere zum Arbeiten an mehreren
Projekten. Dies ist auch der Grund, weswegen ich nicht empfehle, eine virtuelle
Umgebung zu aktivieren: ihr könnt dann leicht den Überblick verlieren, welche
virtuelle Umgebung momentan aktiv ist.

.. seealso::
   * :doc:`python3:tutorial/venv`

PyPI
~~~~

Der :term:`Python Package Index (PyPI)` ist der Standard-Paket-Index, jedoch
keineswegs das einzige Repository für Python-Code. Ihr könnt ihn direkt unter
https://pypi.python.org aufrufen und nach Paketen suchen oder die Pakete nach
Kategorien filtern.
