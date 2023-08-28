.. _field_site:

Field Site
==========


ARM SGP
-------

The AWAKEN field campaign is taking place in northern Oklahoma, in proximity to the `DOE Atmospheric Radiation Measurement (ARM) Program's Southern Great Plains (SGP) facility <https://www.arm.gov/capabilities/observatories/sgp>`_. The SGP covers 55,000 acres and includes more than 30 instrument clusters. 


Wind Plants
-----------

Five wind plants south of the central SGP facility comprise the AWAKEN field campaign area. Details about each plant are located in the table below.

+-----------------+-------------------------+--------------------+--------------------------------------------+--------------------------+
| Wind plant      | Year of first operation | Number of turbines | Turbine model (rotor diameter, hub height) | Net capacity factor [#]_ |
+=================+=========================+====================+============================================+==========================+
| Chisholm View   | 2012                    | 167                | | 140 x GE 1.68 MW (82.5 m, 80 m)          | 0.35                     |
|                 |                         |                    | | 27 x GE 2.4 MW (107 m, 80 m)             |                          |
+-----------------+-------------------------+--------------------+--------------------------------------------+--------------------------+
| Thunder Ranch   | 2017                    | 120                | | 109 x GE 2.5 MW (116 m, 90 m)            | 0.41                     |
|                 |                         |                    | | 11 x GE 2.3 MW (116 m, 90 m)             |                          |
+-----------------+-------------------------+--------------------+--------------------------------------------+--------------------------+
| Breckenridge    | 2015                    | 57                 | GE 1.7 MW (103 m, 80 m)                    | 0.49                     |
+-----------------+-------------------------+--------------------+--------------------------------------------+--------------------------+
| Armadillo Flats | 2018                    | 126                | | 59 x GE 1.79 MW (100 m, 80 m)            | 0.43                     |
|                 |                         |                    | | 21 x GE 1.715 MW (103 m, 80 m)           |                          |
|                 |                         |                    | | 46 x GE 2.3 MW (116 m, 90 m)             |                          |
+-----------------+-------------------------+--------------------+--------------------------------------------+--------------------------+
| King Plains     | 2020                    | 88                 | GE 2.82 MW (127 m, 90 m)                   | 0.37                     |
+-----------------+-------------------------+--------------------+--------------------------------------------+--------------------------+

.. [#] Net capacity factors are calculated as an average from the annual net generation values reported by the U.S. EIA. (“Electricity plan level data for oklahoma,” https://www.eia.gov/opendata/v1/qb.php?category=902967, Last accessed on 2022-12-30.) Data for the first year reported by the EIA are not considered in the calculation.


Instrumentation
---------------

.. figure:: images/instrument_sites.png

*Figure: Map of the AWAKEN field sites (yellow stars) and the four instrumented turbines (yellow circles).*

Instruments were placed within the AWAKEN field domain based on the :ref:`prioritized set of testable hypotheses<testable_hypotheses>`. There are a total of 13 remote ground-based field sites hosting a variety of intstruments. The King Plains wind plant was chosen for detialed study as it is the most modern plant in the area, and is therefore the most heavily instrumented. In addition to the ground-based sites around the plant, five King Plains turbines also host instruments. The table below lists the deployed instrumentation at each site, along with the testable hypotheses they are intended to address. Note that not all instruments remained deployed for the entire duration of the campaign.

+-------------+----------------------------------------------------+-------------+-------------------------------------------------+
| Site name   | Instrumentation                                    | Flow region | :ref:`Testable hypotheses<testable_hypotheses>` |
+=============+====================================================+=============+=================================================+
| A1          | SL, PL, TP, Ceil, Flux, Met, Rad, Prec             | Inflow      | 2, 3, 5, 7                                      |
+-------------+----------------------------------------------------+-------------+-------------------------------------------------+
| A2          | SL, PL, Flux, Met                                  | Inflow      | 3, 5, 7                                         |
+-------------+----------------------------------------------------+-------------+-------------------------------------------------+
| A5          | SL, Flux, Met                                      | Inflow      | 3                                               |
+-------------+----------------------------------------------------+-------------+-------------------------------------------------+
| A7          | SL, Met                                            | Inflow      | 3                                               |
+-------------+----------------------------------------------------+-------------+-------------------------------------------------+
| B           | PL, TP, Met                                        | Inflow      | 5, 7                                            |
+-------------+----------------------------------------------------+-------------+-------------------------------------------------+
| C1a         | SL, PL, TP, Flux, Met                              | Inter-farm  | 1, 5, 7                                         |
+-------------+----------------------------------------------------+-------------+-------------------------------------------------+
| D           | PL                                                 | Inter-farm  | 1                                               |
+-------------+----------------------------------------------------+-------------+-------------------------------------------------+
| E36         | PL, CLAMPS                                         | Inflow      | 5, 7                                            |
+-------------+----------------------------------------------------+-------------+-------------------------------------------------+
| G           | TP, Flux, Met, Tethersonde                         | Intra-farm  | 2                                               |
+-------------+----------------------------------------------------+-------------+-------------------------------------------------+
| Golf Course | CLAMPS                                             | Inter-farm  | 1                                               |
+-------------+----------------------------------------------------+-------------+-------------------------------------------------+
| H           | SL, PL, TP, Ceil, Flux, Met, Rad, Prec, Radiosonde | Downwind    | 1, 5, 7                                         |
+-------------+----------------------------------------------------+-------------+-------------------------------------------------+
| Radar 1     | X-band radar                                       | All         | 1, 3, 6                                         |
+-------------+----------------------------------------------------+-------------+-------------------------------------------------+
| Radar 2     | X-band radar                                       | All         | 1, 3, 6                                         |
+-------------+----------------------------------------------------+-------------+-------------------------------------------------+
| Turbine H05 | SL, Nacelle lidar, Loads, Prec                     | Inflow      | 2, 4, 6, 7                                      |
+-------------+----------------------------------------------------+-------------+-------------------------------------------------+
| Turbine G02 | SL, Loads                                          | Intra-farm  | 2, 4, 6, 7                                      |
+-------------+----------------------------------------------------+-------------+-------------------------------------------------+
| Turbine F04 | SL                                                 | Intra-farm  | 3, 4, 6                                         |
+-------------+----------------------------------------------------+-------------+-------------------------------------------------+
| Turbine E06 | SL, Loads                                          | Downwind    | 2, 4, 6, 7                                      |
+-------------+----------------------------------------------------+-------------+-------------------------------------------------+
| Turbine G06 | SL                                                 | Intra-farm  | 3, 4, 6                                         |
+-------------+----------------------------------------------------+-------------+-------------------------------------------------+

Legend:

- SL - Scanning lidar
- PL - Profiling lidar
- TP - Thermodynamic profiler
- Ceil - Ceilometer
- Flux - Surface flux station
- Met - Meteorological station
- Rad - Radiation measurement
- Prec - Precipitation sensor
