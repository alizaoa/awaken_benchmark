.. _measurements:

AWAKEN Measurements
====================

Overview
---------------

.. figure:: images/instrument_sites.png

*Figure: Map of the AWAKEN field sites (yellow stars) and the five instrumented turbines (yellow circles). The blue triangle is the pre-existing King Plains meteorological tower.*

Instruments were placed within the AWAKEN field domain based on the :ref:`prioritized set of testable hypotheses<testable_hypotheses>`. There are a total of 13 remote ground-based field sites hosting a variety of instruments. The King Plains wind plant was chosen for detailed study as it is the most modern plant in the area, and is therefore the most heavily instrumented. In addition to the ground-based sites around the plant, five King Plains turbines also host instruments. The table below lists the deployed instrumentation at each site, along with the testable hypotheses they are intended to address. Note that not all instruments remained deployed for the entire duration of the campaign.

`This <https://a2e.energy.gov/api/content/awaken/files/AWAKEN_map.kmz>`_ .kmz file includes the locations of all the AWAKEN instrumented sites.


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


In the next sections, details about the instruments used for the benchmark validation are given.


Atmospheric inflow measurements (sites A1, A2, A5, B, E36)
------------------------------------------------------------

- **Site A1** (GPS coordinates: 36°21'43.6"N 97°24'16.4"W)
    - **Scanning lidar**: a Halo Photonics Streamline XR scanning lidar is deployed at this site. The lidar operates on a 30-min scanning strategy, which is then repeated. The first 20-min are used to perform tilted 6-beam scans to derive the vertical profile of the wind speed while avoiding to scan the nearby turbines. We note that the data provided to participants have been post-processed in regular (time, height) dimensions, so the tilted nature of the scans has no impact on the structure of the data in the provided files. Each 6-beam scan lasts about 4 seconds. After each 20-min period, the lidar stares vertically for the remaining 10 minutes. Because of the lidar blind zone, the lowest elevation with good quality data is 110 m a.g.l. Data are provided every 10 m up to 4 km. Data from this lidar have been QCed using the lidar dynamic filter approach.
    - **Profiling lidar**: a Windcube v2 profiling lidar is deployed at this site. The lidar uses a DBS, 5-beam approach. We provide a vertical profile of horizontal wind speed and the vertical component of the wind. One full profile takes about 5 s to complete. We provide data both as 10-minute averages and as instantaneous 1-s data. For the instantaneous data, we provide the three components of the wind speed. In both cases, observations are available every 20 m from 40 m up to 240 m a.g.l.. Data from this lidar have not been systematically QCed, but the CNR values are provided.
    - **Sonic anemometer**: Gill R3-50, omnidirectional mounted on top of a 4-meter tripod. We provide QCed, 30-min average values of wind speed, wind direction, u, v, w wind components, sonic temperature, sensible heat flux, friction velocity, TKE, Obukhov length. The turbulent fluxes and corresponding statistics were estimated from 30-minute raw data using software initially developed for ARM ECOR systems.
- **Site A2** (GPS coordinates: 36°19'05.5"N 97°24'32.7"W)
    - **Scanning lidar**: a Halo Photonics Streamline XR scanning lidar is deployed at this site. The lidar operates on a 30-min scanning strategy, which is then repeated. The first 20-min are used to perform regular 6-beam scans to derive the vertical profile of the wind speed. Each 6-beam scan lasts about 4 seconds. After each 20-min period, the lidar stares vertically for the remaining 10 minutes. Because of the lidar blind zone, the lowest elevation with good quality data is 110 m a.g.l. Data are provided every 10 m up to 4 km. Data from this lidar have been QCed using the lidar dynamic filter approach.
    - **Profiling lidar**: a Windcube v1 profiling lidar is deployed at this site. The lidar uses a DBS, 4-beam approach. We provide a vertical profile of horizontal wind speed and the vertical component of the wind. One full profile takes about 4 s to complete. Here, data are provided every 2 minutes, and at every 20 m from 40 m up to 220 m a.g.l.. Data from this lidar have been QCed using a simple CNR threshold (-22 dB). We also note that data from this lidar are only available from 02-19 UTC on 23 August 2023 and 03-18 UTC on 24 August 2023.
    - **Sonic anemometer**: Gill R3-50, omnidirectional mounted on top of a 4-meter tripod. We provide QCed, 30-min average values of wind speed, wind direction, u, v, w wind components, sonic temperature, sensible heat flux, friction velocity, TKE, Obukhov length. The turbulent fluxes and corresponding statistics were estimated from 30-minute raw data using software initially developed for ARM ECOR systems.
- **Site A5** (GPS coordinates: 36°21'42.5"N 97°22'53.8"W)
    - **Sonic anemometer**: Gill R3-50, omnidirectional mounted on top of a 4-meter tripod. We provide QCed, 30-min average values of wind speed, wind direction, u, v, w wind components, sonic temperature, sensible heat flux, friction velocity, TKE, Obukhov length. The turbulent fluxes and corresponding statistics were estimated from 30-minute raw data using software initially developed for ARM ECOR systems.
- **Site B** (GPS coordinates: 36°13'54.4"N 97°33'31.2"W)
    - **Profiling lidar**: a Windcube v2.1 profiling lidar is deployed at this site. The lidar uses a DBS, 5-beam approach. We provide a vertical profile of horizontal wind speed and the vertical component of the wind. One full profile takes about 5 s to complete. We provide data both as 10-minute averages and as instantaneous 1-s data. For the instantaneous data, we provide the three components of the wind speed. In both cases, observations are available every 20 m from 40 m up to 300 m a.g.l.. Data from this lidar have been QCed using the filtering algorithm provided by the instrument manufacturer (Vaisala). We also note that data from this lidar are only available from 13-19 UTC on 23 August 2023 and 03-18 UTC on 24 August 2023.
    - **Thermodynamic profiler**: ASSIST-II profiler, from which temperature has been retrieved using the TROPoe algorithm developed by Dave Turner (NOAA). For the instrument at site B, data are available at 30-minute resolution, from the ground up to over 15 km, at varying vertical resolution.
- **Site E36** (GPS coordinates: 36°07'01.0"N 97°30'39.2"W)
    - **Scanning lidar**: a Halo Photonics Streamline XR scanning lidar is deployed at this site as part of the CLAMPS module. We provide 10-minute average vertical profiles of wind speed (and vertical velocity) from this lidar. Because of the lidar blind zone, the lowest elevation with good quality data is 98.6 m a.g.l. Data are provided every 28 m up to over 10 km. Data from this lidar have been QCed using a simple CNR threshold (-23 dB).
    - **Thermodynamic profiler**: ASSIST-II profiler, from which temperature has been retrieved using the TROPoe algorithm developed by Dave Turner (NOAA). For the instrument at site E36, data are available at 10-minute resolution, from the ground up to over 15 km, at varying vertical resolution. Data are only available until 14 UTC on 24 August 2023.


Wake measurements (sites C1a, G, Golf Course, H, Turbine E06)
------------------------------------------------------------

- **Site C1a** (GPS coordinates: 36°21'41.8"N 97°30'36.1"W)
    - **Scanning lidar 1**: DATA ARE UNDERGOING QC -- DETAILS WILL BE POSTED LATER.
    - **Scanning lidar 2**: DATA ARE UNDERGOING QC -- DETAILS WILL BE POSTED LATER.
    - **Profiling lidar**: a Windcube v1 profiling lidar is deployed at this site. The lidar uses a DBS, 4-beam approach. We provide a vertical profile of horizontal wind speed and the vertical component of the wind. One full profile takes about 4 s to complete. Here, data are provided every 2 minutes, and at every 20 m from 40 m up to 220 m a.g.l.. Data from this lidar have been QCed using a simple CNR threshold (-22 dB). We also note that data from this lidar are only available from 02-19 UTC on 23 August 2023 and 02-18 UTC on 24 August 2023.
    - **Thermodynamic profiler**: ASSIST-II profiler, from which temperature has been retrieved using the TROPoe algorithm developed by Dave Turner (NOAA). For the instrument at site G, data are available at 30-minute resolution, from the ground up to over 15 km, at varying vertical resolution.
    - **Sonic anemometer**: DATA ARE UNDERGOING QC -- DETAILS WILL BE POSTED LATER.

- **Site G** (GPS coordinates: 36°23'58.1"N 97°24'28.9"W)
    - **Thermodynamic profiler**: ASSIST-II profiler, from which temperature has been retrieved using the TROPoe algorithm developed by Dave Turner (NOAA). For the instrument at site G, data are available at 30-minute resolution, from the ground up to over 15 km, at varying vertical resolution.
    - **Sonic anemometer**: Gill R3-50, omnidirectional mounted on top of a 4-meter tripod. We provide QCed, 30-min average values of wind speed, wind direction, u, v, w wind components, sonic temperature, sensible heat flux, friction velocity, TKE, Obukhov length. The turbulent fluxes and corresponding statistics were estimated from 30-minute raw data using software initially developed for ARM ECOR systems.

- **Site Golf Course** (GPS coordinates: 36°22'47.09"N 97°31'24.51"W)
    - **Scanning lidar**: a Halo Photonics Streamline XR scanning lidar is deployed at this site as part of the CLAMPS module. We provide 10-minute average vertical profiles of wind speed (and vertical velocity) from this lidar. Because of the lidar blind zone, the lowest elevation with good quality data is 98.6 m a.g.l. Data are provided every 28 m up to over 10 km. Data from this lidar have been QCed using a simple CNR threshold (-23 dB).
    - **Thermodynamic profiler**: ASSIST-II profiler, from which temperature has been retrieved using the TROPoe algorithm developed by Dave Turner (NOAA). For the instrument at site E36, data are available at 10-minute resolution, from the ground up to over 15 km, at varying vertical resolution.

- **Site H** (GPS coordinates: 36°26'12.7"N 97°24'27.9"W)
    - **Profiling lidar**: a ZephIR300 profiling lidar is deployed at this site. The lidar uses a VAD, continuous wave multi-beam approach. One complete profile takes about 15-20 s to complete and the data are available as 10-minute averages and instantaneous values. We provide a vertical profile of horizontal wind speed, the vertical component of the wind, and (as 10-minute average only) lidar-derived TI. Here, data are provided at every 20 m from 40 m up to 220 m a.g.l..
    - **Scanning lidar**: a Halo Photonics Streamline XR scanning lidar is deployed at this site. The lidar operates on a 30-min scanning strategy, which is then repeated. The first 20-min are used to perform regular 6-beam scans to derive the vertical profile of the wind speed. Each 6-beam scan lasts about 4 seconds. After each 20-min period, the lidar stares vertically for the remaining 10 minutes. Because of the lidar blind zone, the lowest elevation with good quality data is 110 m a.g.l. Data are provided every 10 m up to 4 km. Data from this lidar have been QCed using the lidar dynamic filter approach.
    - **Sonic anemometer**: Gill R3-50, omnidirectional mounted on top of a 4-meter tripod. We provide QCed, 30-min average values of wind speed, wind direction, u, v, w wind components, sonic temperature, sensible heat flux, friction velocity, TKE, Obukhov length. The turbulent fluxes and corresponding statistics were estimated from 30-minute raw data using software initially developed for ARM ECOR systems.

- **Turbine E06** (GPS coordinates: )
    - **Scanning lidar**: DATA ARE UNDERGOING QC -- DETAILS WILL BE POSTED LATER.

SCADA
------------------------------------------------------------

DETAILS WILL BE POSTED LATER

