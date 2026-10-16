Quickstart
==========

After completing :doc:`install`, follow the example below to load the bundled
CSV data, summarise each measurement column, and write a report.

Load, summarise, and report
---------------------------

Save this code as ``example.py`` in the repository directory:

.. code-block:: python

   import ci_course

   # With no path supplied, load the sample data bundled with the package.
   measurements = ci_course.load_measurements()
   print("Columns:", ", ".join(measurements))

   # Calculate statistics for every measurement column.
   summaries = ci_course.summarise_all(measurements)
   print("Temperature measurements:", summaries["temperature_c"]["n"])

   # Write a plain-text report and display its contents.
   report_path = ci_course.write_report(summaries, "report.txt")
   print(report_path.read_text(encoding="utf-8"))

Run it with your virtual environment activated:

.. code-block:: bash

   python example.py

The sample contains ``temperature_c`` and ``mass_g`` columns. Each has eight
rows, including one missing value, so each summary counts seven measurements.
The ``sample_id`` column contains labels and is not included in the measurements.

The summaries contain the count (``n``), mean, sample standard deviation (``sd``),
minimum, and maximum. Missing values are ignored when calculating these
statistics.

The report is saved as ``report.txt`` in your current working directory. It starts
with ``Measurement summary`` and contains a line of statistics for each column.
Running the example again replaces that report.

Use your own data
-----------------

Pass a CSV path to load another dataset:

.. code-block:: python

   measurements = ci_course.load_measurements("measurements.csv")
   summaries = ci_course.summarise_all(measurements)
   ci_course.write_report(summaries, "report.txt")

Use a header row with measurement column names. An optional ``sample_id`` column
is treated as a label; measurement columns should contain numbers, with blank
cells for missing values.

See :doc:`reference` for function parameters and return values.
