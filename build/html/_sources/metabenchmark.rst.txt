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

Three scenarios will be used as benchmark cases:

1. :blue:`Wake of King Plains under stable conditions, flow from the south, 95%+ of turbines operating at maximum thrust coefficient (based on wind speed or turbine operation)`
2. :blue:`Wake of King Plains under unstable conditions, flow from the south, 95%+ of turbines operating at maximum thrust coefficient (based on wind speed or turbine operation)`
3. :red:`Wake impact of Armadillo Flats on King plains under stable conditions, flow from the southwest, 95%+ of Armadillo Flats turbines operating at maximum thrust coefficient (based on wind speed or turbine operation)`

.. figure:: images/benchmark_cases.png


Inflow Observations Provided
----------------------------

The following parameters will be provided to benchmark participants in the form of statistics and time series as inputs to their simulations:

+-----------------------------------------+-------------------------------------------------------------------------------------------------------------------------+
| Input parameter                         | Data source instrument (site)                                                                                           |
+=========================================+=========================================================================================================================+
| Hub-height wind speed and direction     | Profiling lidar (:blue:`A1`, :blue:`A2`, :red:`B`); Nacelle-mounted lidar (:blue:`turbine H05`)                         |
+-----------------------------------------+-------------------------------------------------------------------------------------------------------------------------+
| Wind speed and direction profile        | Profiling lidar (:blue:`A1`, :blue:`A2`, :red:`B`)                                                                      |
+-----------------------------------------+-------------------------------------------------------------------------------------------------------------------------+
| Hub-height turbulence intensity         | Profiling lidar (:blue:`A1`, :blue:`A2`, :red:`B`); Nacelle-mounted lidar (:blue:`turbine H05`)                         |
+-----------------------------------------+-------------------------------------------------------------------------------------------------------------------------+
| Turbulence intensity profile            | Profiling lidar (:blue:`A1`, :blue:`A2`, :red:`B`)                                                                      |
+-----------------------------------------+-------------------------------------------------------------------------------------------------------------------------+
| Atmospheric boundary layer height       | Ceilometer (:blue:`A1`); Scanning/profiling lidar (:blue:`A1`, :blue:`A2`, :red:`B`); Thermodynamic profiler (:red:`B`) |
+-----------------------------------------+-------------------------------------------------------------------------------------------------------------------------+
| Roughness length                        | Database?                                                                                                               |
+-----------------------------------------+-------------------------------------------------------------------------------------------------------------------------+
| Obukhov length                          | Sonic anemometer (:blue:`A1`, :blue:`A2`, :red:`B`)                                                                     |
+-----------------------------------------+-------------------------------------------------------------------------------------------------------------------------+
| Kinetmatic vertical turbulent heat flux | Sonic anemometer (:blue:`A1`, :blue:`A2`, :red:`B`)                                                                     |
+-----------------------------------------+-------------------------------------------------------------------------------------------------------------------------+
| Virtual potential temperature           | Sonic anemometer (:blue:`A1`, :blue:`A2`, :red:`B`)                                                                     |
+-----------------------------------------+-------------------------------------------------------------------------------------------------------------------------+
| Air density                             |                                                                                                                         |
+-----------------------------------------+-------------------------------------------------------------------------------------------------------------------------+



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