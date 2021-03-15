.. FrequencyOverlaps documentation master file, created by
   sphinx-quickstart on Sun Feb 12 17:11:03 2012.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to FrequencyOverlaps!
============================================

The goal of this plugin is to assist Spectrum Managers in searching for frequency resources especially when more and more services are put into use.  This plugin helps Spectrum Managers to search for overlapping frequencies as each service normally encompass a frequency with an associated bandwidth or a start and stop frequency for it to effectively operate.  It becomes difficult to visualise if frequency overlaps occurs when there are more and more services utilising similar frequency bands, and to ensure that these services are separated geographically far enough on the map.

The user must first load information about existing location of services into a layer on QGIS.  This can be imported from `Spreadsheet Layers <https://github.com/camptocamp/QGIS-SpreadSheetLayers>`_ , CSV, Esri Shapefiles, Mapinfo or any other formats supported by QGIS. The information within the file must contain at least information of the frequency resources utilised for the service either information about the center frequency and bandwidth or a start and stop frequency entered in separate columns.  The frequency and bandwidth may be in the range of Hz, kHz, MHz or GHz, and the layer should be a point or polygon layer in QGIS.  The frequencies or bandwidth should be numerical fields; that **SHOULD NOT** include the suffix of Hz, kHz, MHz or GHz behind the frequency or bandwidth number such as 1234 MHz.


Difference Between Frequency and Bandwidth
==========================================
.. index:: Difference Between Frequency and Bandwidth

Bandwidth and frequency are the terms commonly used in communications and networking.  The bandwidth affects the size of the information that can be transferred while the frequency is the carrier for the information to be transferred on.  More information can be read from `Difference Between Frequency and Bandwidth <https://circuitglobe.com/difference-between-frequency-and-bandwidth.html#:~:text=The%20frequency%20of%20a%20signal%20defines%20the%20total%20number%20of,is%20specified%20as%20cycles%2Fsecond.>`_ .

Frequency Overlaps Overview
===========================
.. index:: Functions of Frequency Overlaps

.. image:: images/FrequencyOverlaps.png

1) Select the QGIS layer from the drop down list which contains information about the location where the frequency is used.
2) Select the mode where the data is entered in the layer.  This can be either Center Frequency & Bandwidth or Start & Stop Frequency.
3) Select the field that contains the Center Frequency, if the Center Frequency mode is selected.
4) Select the units that this field is entered in.  Can be Hz, kHz, MHz or GHz.
5) Select the field that contains the Bandwidth, if the Center Frequency mode is selected.
6) Select the units that this field is entered in.  Can be Hz, kHz, MHz or GHz.
7) Limit the range to be displayed post analysis.  A 0 value will display maximum range.

There are 5 Search modes to check for frequency overlaps:
"""""""""""""""""""""""""""""""""""""""""""""""""""""""""
* Search within the layer
* Search within a range
* Search against another layer
* Search for frequency
* Search for frequency gaps

Search within the layer
-----------------------
.. index:: Search within the layer

This option searches for frequency overlaps between each feature in the layer.  The output may be overwhelming with a lot of frequency overlaps between each features.  Use the **Ignore Distance greater than** to limit overlaps that are within a distance away.

The output may show a single circle only, such as the figure shown below.  This represents there is a frequency overlaps within frequencies on the same location.
It may be noticed that the frequency of 1 channel is 8202.705 - 8203.295 MHz and the other channel is 8203.295 - 8204.217 MHz.  In a normal situation it seems like there is no overlaps.  The contention comes at the middle frequency 8203.295 MHz since it both belongs to the lower frequency channel and higher frequency channel and the algorithm treats such instance as an overlap.

.. image:: images/On-site_Overlaps.png

The output may also shows 2 circles with a dashed line linking them.  This represents frequency overlaps between the frequency of the 2 locations.  Open the attribute tables of "Overlap Locations" and "Overlap Joins" to get more information on which frequencies are overlapping.


.. image:: images/AlternateSite_Overlaps.png



Contents:

.. toctree::
   :maxdepth: 2

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

