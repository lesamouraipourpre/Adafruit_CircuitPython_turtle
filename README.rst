Introduction
============

.. image:: https://readthedocs.org/projects/adafruit-circuitpython-turtle/badge/?version=latest
    :target: https://circuitpython.readthedocs.io/projects/turtle/en/latest/
    :alt: Documentation Status

.. image:: https://img.shields.io/discord/327254708534116352.svg
    :target: https://adafru.it/discord
    :alt: Discord

.. image:: https://github.com/adafruit/Adafruit_CircuitPython_turtle/workflows/Build%20CI/badge.svg
    :target: https://github.com/adafruit/Adafruit_CircuitPython_turtle/actions/
    :alt: Build Status

Turtle graphics library for CircuitPython and displayio


Dependencies
=============
This driver depends on:

* `Adafruit CircuitPython <https://github.com/adafruit/circuitpython>`_
* `Bus Device <https://github.com/adafruit/Adafruit_CircuitPython_BusDevice>`_

Please ensure all dependencies are available on the CircuitPython filesystem.
This is easily achieved by downloading
`the Adafruit library and driver bundle <https://github.com/adafruit/Adafruit_CircuitPython_Bundle>`_.

Installing from PyPI
=====================

On supported GNU/Linux systems like the Raspberry Pi, you can install the driver locally `from
PyPI <https://pypi.org/project/adafruit-circuitpython-turtle/>`_. To install for current user:

.. code-block:: shell

    pip3 install adafruit-circuitpython-turtle

To install system-wide (this may be required in some cases):

.. code-block:: shell

    sudo pip3 install adafruit-circuitpython-turtle

To install in a virtual environment in your current project:

.. code-block:: shell

    mkdir project-name && cd project-name
    python3 -m venv .env
    source .env/bin/activate
    pip3 install adafruit-circuitpython-turtle

Usage Example
=============

.. code-block:: python

    import board
    from adafruit_turtle import Color, turtle

    turtle = turtle(board.DISPLAY)
    starsize = min(board.DISPLAY.width, board.DISPLAY.height) * 0.9  # 90% of screensize

    print("Turtle time! Lets draw a star")

    turtle.pencolor(Color.BLUE)

    turtle.penup()
    turtle.goto(-starsize/2, 0)
    turtle.pendown()

    start = turtle.pos()
    while True:
        turtle.forward(starsize)
        turtle.left(170)
        if abs(turtle.pos() - start) < 1:
            break

    while True:
        pass

Contributing
============

Contributions are welcome! Please read our `Code of Conduct
<https://github.com/adafruit/Adafruit_CircuitPython_turtle/blob/main/CODE_OF_CONDUCT.md>`_
before contributing to help this project stay welcoming.

Documentation
=============

For information on building library documentation, please check out `this guide <https://learn.adafruit.com/creating-and-sharing-a-circuitpython-library/sharing-our-docs-on-readthedocs#sphinx-5-1>`_.
