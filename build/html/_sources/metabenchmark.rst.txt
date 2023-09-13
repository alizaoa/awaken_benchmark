.. _metabenchmark:


.. raw:: html

    <style> .red {color:red} </style>

.. role:: red


.. raw:: html

    <style> .blue {color:blue} </style>

.. role:: blue


Benchmark Template: Benchmark 1
================================

The benchmark for :ref:`testable hypothesis 1<testable_hypotheses>` concerning wind plant wakes is used as a template for future benchmarks.

Validation Objectives
---------------------

The goal of this benchmark is to evaluate the models' ability to accurately capture:

- Wind farm wake characteristics
    - Momentum deficit (magnitude and extent)
    - TKE increase (magnitude and extent)
    - Temperature, moisture
    - Boundary layer height

- Impacts on downstream wind plants
    - Power generation
    - Loads? (avoid overlap with testable hypothesis 2)

- Impacts on downstream environment
    - Temperature
    - Moisture

- Effects of inflow conditions
    - Wind speed
    - Wind direction
    - Turbulence
    - Atmospheric stability
    - Shear and veer

- Effects of geometry
    - Plant layout
    - Turbine size
    - Topography
    - Wake steering


Simulation Tools
----------------

The simulation tools targeted for comparison by this benchmark are:

- `WRF <https://www.mmm.ucar.edu/models/wrf>`_
- `FLORIS <https://www.nrel.gov/wind/floris.html>`_
- Engineering models
- Large-eddy simulation (LES)


Team
----

The team responsible for the development of this benchmark will include, at minimum:

- 1 team leader
- 1-2 instrumentation experts
- 1 expert for each simulation tool


Benchmark Cases
---------------

These scenarios will be used as benchmark cases:

1. :blue:`Wake of King Plains under stable conditions, flow from the south, 95%+ of turbines operating at maximum thrust coefficient (based on wind speed or turbine operation)`
2. :blue:`Wake of King Plains under unstable conditions, flow from the south, 95%+ of turbines operating at maximum thrust coefficient (based on wind speed or turbine operation)`
3. :blue:`Wake of King Plains under neutral conditions, flow from the south, 95%+ of turbines operating at maximum thrust coefficient (based on wind speed or turbine operation)`

1. :red:`Wake impact of Armadillo Flats on King plains under stable conditions, flow from the southwest, 95%+ of Armadillo Flats turbines operating at maximum thrust coefficient (based on wind speed or turbine operation)`
2. :red:`Wake impact of Armadillo Flats on King plains under unstable conditions, flow from the southwest, 95%+ of Armadillo Flats turbines operating at maximum thrust coefficient (based on wind speed or turbine operation)`
3. :red:`Wake impact of Armadillo Flats on King plains under neutral conditions, flow from the southwest, 95%+ of Armadillo Flats turbines operating at maximum thrust coefficient (based on wind speed or turbine operation)`

.. figure:: images/benchmark_cases.png


Inflow Observations Provided
----------------------------

The following parameters will be provided to benchmark participants in the form of statistics (cases 1, 2, and 3) and time series (cases 1 and 2) as inputs to their simulations:

+------------------------------------------+-------------------------------------------------------------------------------------------------------------------------+
| Input parameter                          | Data source instrument (site)                                                                                           |
+==========================================+=========================================================================================================================+
| Vertical profiles of:                    || Profiling lidar (:blue:`A1`, :blue:`A2`, :red:`B`)                                                                     |
|                                          || Scanning lidar used in profiling mode (:blue:`A1`)                                                                     |
| - Horizontal wind speed                  || Nacelle-mounted Windcube lidar (:blue:`turbine H05`)                                                                   |
| - Wind direction                         || Thermodynamic profiler (:blue:`AERI at A1`, :red:`ASSIST at B`)                                                        |
| - Vertical wind speed                    |                                                                                                                         |
| - Turbulence intensity                   |                                                                                                                         |
| - Turbulent kinetic energy               |                                                                                                                         |
| - Temperature                            |                                                                                                                         |
| - Dissipation rate                       |                                                                                                                         |
|                                          |                                                                                                                         |
+------------------------------------------+-------------------------------------------------------------------------------------------------------------------------+
| Near-surface:                            || Sonic anemometer (:blue:`A1`, :blue:`A2`, :red:`B`)                                                                    |
|                                          || Flux station (:blue:`A1`, :blue:`A2`, :red:`B`)                                                                        |
| - Wind speed                             |                                                                                                                         |
| - Wind direction                         |                                                                                                                         |
| - Obukhov length                         |                                                                                                                         |
| - Kinematic vertical turbulent heat flux |                                                                                                                         |
| - Virtual potential temperature          |                                                                                                                         |
| - Friction velocity                      |                                                                                                                         |
|                                          |                                                                                                                         |
+------------------------------------------+-------------------------------------------------------------------------------------------------------------------------+
| Atmospheric boundary layer height        || Ceilometer (:blue:`A1`)                                                                                                |
|                                          || Scanning/profiling lidar (:blue:`A1`, :blue:`A2`, :red:`B`)                                                            |
|                                          || Thermodynamic profiler (:blue:`AERI at A1`, :red:`ASSIST at B`)                                                        |
|                                          |                                                                                                                         |
|                                          |                                                                                                                         |
+------------------------------------------+-------------------------------------------------------------------------------------------------------------------------+
| Roughness length                         | Database?                                                                                                               |
+------------------------------------------+-------------------------------------------------------------------------------------------------------------------------+
| Air density                              |                                                                                                                         |
+------------------------------------------+-------------------------------------------------------------------------------------------------------------------------+



Simulation Outputs for Evaluation
---------------------------------

The following output parameters will be used to evaluate the accuracy of the simulations:

+-----------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+
| Output parameter                                                            | Data source instrument (site)                                                                                               |
+=============================================================================+=============================================================================================================================+
| Magnitude of momentum deficit at downstream cross-sections                  | Profiling/scanning lidar (:blue:`H`, :red:`C1a`); Nacelle-mounted lidar (:blue:`turbine E06`); Aircraft measurements; Radar |
+-----------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+
| Magnitude of turbulent kinetic energy increase at downstream cross-sections | Profiling/scanning lidar (:blue:`H`, :red:`C1a`); Nacelle-mounted lidar (:blue:`turbine E06`); Aircraft measurements; Radar |
+-----------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+
| Power loss of downstream wind plant                                         | :red:`SCADA from King Plains`                                                                                               |
+-----------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+
| Near-surface moisture and temperature                                       | Met station (:blue:`H`, :red:`C1a`)                                                                                         |
+-----------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+
| Temperature profile                                                         | Thermodynamic profiler (:blue:`H`, :red:`C1a`)                                                                              |
+-----------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+
| Vertical velocity at downstream cross-sections                              | Profiling/scanning lidar (:blue:`H`, :red:`C1a`); Nacelle-mounted lidar (:blue:`turbine E06`); Aircraft measurements        |
+-----------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+
| Downstream atmospheric boundary layer height                                | Ceilometer (:blue:`H`); Scanning/profiling lidar (:blue:`H`, :red:`C1a`); Thermodynamic profiler (:blue:`H`, :red:`C1a`)    |
+-----------------------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------+