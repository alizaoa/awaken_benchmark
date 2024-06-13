.. _benchmark_1_farmwake:


.. raw:: html

    <style> .red {color:red} </style>

.. role:: red


.. raw:: html

    <style> .blue {color:blue} </style>

.. role:: blue


Benchmark 1: Wakes, Diurnal Cycle
================================

Case Study
----------------------

The goal of this benchmark is to simulate the area around the King Plains and Armadillo Flats wind farms on 24 August 2023. The size of the modeling domain is left to the participants, however, we recommend to include both wind farms to be able to capture their interaction during the day to simulate.

IF the above is not possible, we recommend participants to focus on the region in the map below, to maximize chances for a valuable comparison across models.

.. figure:: images/limited_domain.png

The figure below shows the observed wind speed, wind direction and lidar-derived TKE at AWAKEN site A1 on the selected case study. The vertical dashed lines show local sunset (left) and sunrise (right).

.. figure:: images/a1_lidar.jpg


Validation Objectives
---------------------

The goal of this benchmark is to evaluate the models' ability to accurately capture:

- Wake (at both farm and turbine levels) characteristics
    - Momentum deficit
    - Turbulence increase

- Impacts on downstream wind plants
    - Power generation

- Impacts on downstream environment
    - Temperature

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


Simulation Tools
----------------

All simulation tools are welcome to participate in this benchmark. This includes, but it is not limited to:

- Mesoscale models, with different wind farm parameterizations
- Steady-state analytical models
- Dynamic wake meandering-type models
- Engineering models
- Large-eddy simulation (LES), both coupled to mesoscale or run at the microscale only
- Reynolds-averaged Navier–Stokes (RANS) simulations
- Machine learning models

Guidelines
-----------------------

- Participation in the benchmark is open to participants from countries that are part of the IEA Wind Task 57 “JAM”. Please contact paula.doubrawa@nrel.gov for further information about this.
- Simulation tools should be used to the limit of their capabilities. 2D, steady-state solutions will be accepted for low-fidelity models. 3D, time-varying solutions will be expected from mid-to-high fidelity models.
- The choice of domain size, grid spacing, time step, and other model configuration parameters is left to the discretion of the participants.
- Multi-model benchmark results will be published in journal article and co-authored by all participants who choose to release their results and participate in the publication effort.
- All provided results must observe the variable definitions and units as explicitly defined in the :ref:`glossary<glossary>`.


Team
----

A large team of researchers have participated to the preparation of this benchmark. The benchmark lead is Nicola Bodini (nicola.bodini@nrel.gov), feel free to reach out to him with questions!




