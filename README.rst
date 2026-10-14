.. image:: https://img.shields.io/coveralls/github/timcera/tsgettoolbox_daymet
    :alt: Test Coverage
    :target: https://coveralls.io/r/timcera/tsgettoolbox_daymet?branch=master
    :height: 20

.. image:: https://img.shields.io/pypi/v/tsgettoolbox_daymet
    :alt: Latest release
    :target: https://pypi.python.org/pypi/tsgettoolbox_daymet/
    :height: 20

.. image:: https://img.shields.io/pypi/l/tsgettoolbox_daymet
    :alt: BSD-3 clause license
    :target: https://pypi.python.org/pypi/tsgettoolbox_daymet/
    :height: 20

.. image:: https://img.shields.io/pypi/pyversions/tsgettoolbox_daymet
    :alt: PyPI - Python Version
    :target: https://pypi.org/project/tsgettoolbox_daymet/
    :height: 20

tsgettoolbox_daymet - Quick Guide
=================================
The 'tsgettoolbox_daymet' is a plugin-in for 'tsgettoolbox' that supplies
a command line interface and Python library to get time-series data from the
Daymet dataset.  The Daymet dataset is a gridded dataset of daily weather
parameters for North America, including temperature, precipitation, humidity,
and solar radiation.  The tsgettoolbox_daymet plugin allows users to easily
access and retrieve time-series data from the Daymet dataset using either the
command line or Python library.  The tsgettoolbox_daymet will work with
Python 3.10+.

Documentation
-------------
Reference documentation is at `tsgettoolbox DAYMET API`_.

Installation
------------
At the command line::

    $ pip install tsgettoolbox_daymet

    OR

    $ conda install -c conda-forge tsgettoolbox_daymet

Usage Summary - Command Line
----------------------------
Just run 'tsgettoolbox --help' to get a list of subcommands.  To get detailed
help for a particular sub-command, for instance 'daymet', type 'tsgettoolbox
daymet --help'.

+-------------+----------+--------+----------+----------+----------------------------+
| Sub-command | Spatial  | Time   | Type     | Time     | Description                |
|             | Extent   | Extent |          | Interval |                            |
+=============+==========+========+==========+==========+============================+
| daymet      | NAmerica | 1980-  | grid 1km | D,M      | daily meteorology by the   |
|             |          |        |          |          | Oak Ridge National         |
|             |          |        |          |          | Laboratory                 |
+-------------+----------+--------+----------+----------+----------------------------+

+-------------------+-------------+
| Time Interval     | Description |
| Code              |             |
+===================+=============+
| D                 | Daily       |
+-------------------+-------------+
| M                 | Monthly     |
+-------------------+-------------+

Usage Summary - Python Library
------------------------------
To use the tsgettoolbox in a project::

    from tsgettoolbox import tsgettoolbox
    df = tsgettoolbox.daymet(
        lat=43.1,
        lon=-85.2,
        start_date="2000-04",
    )
    print(df.head())

Refer to the API Documentation at `tsgettoolbox DAYMET API`_.

Usage Summary - Command Line
----------------------------

    tsgettoolbox daymet \
        --lat=43.1 \
        --lon=-85.2 \
        --start_date="2000-04" > output.csv

Refer to the command line documentation at `tsgettoolbox DAYMET CLI`_.

Development
~~~~~~~~~~~
Development is managed on bitbucket or github.
https://bitbucket.org/timcera/tsgettoolbox_daymet/overview.
https://github.com/timcera/tsgettoolbox_daymet

.. _tsgettoolbox_documentation: https://timcera.bitbucket.io/linked_pkg_dirs/tsgettoolbox/docs/index.html
.. _tsgettoolbox DAYMET API: https://timcera.bitbucket.io/linked_pkg_dirs/tsgettoolbox/docs/_function_autosummary/tsgettoolbox.daymet.html
.. _tsgettoolbox DAYMET CLI: https://timcera.bitbucket.io/linked_pkg_dirs/tsgettoolbox/docs/command_line.html#daymet
