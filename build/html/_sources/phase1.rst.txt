.. _phase1:


.. raw:: html

    <style> .red {color:red} </style>

.. role:: red


.. raw:: html

    <style> .blue {color:blue} </style>

.. role:: blue


Phase 1: model calibration
================================


In phase 1, modelers will use inflow measurements and other data sets to calibrate their simulation tool to match the observed inflow conditions.

Please read the instructions below in detail.

Phase 1 officially starts on 28 May 2024. Participants are expected to submit results for Phase 1 (as specified below) by 1 September 2024.


Model inputs and recommendations
---------------------------------

The following inputs and recommendations are provided to the benchmark participants:

- Recommended topographical data set
    - USGS 1⁄3 arc-sec Digital Elevation Models (DEMs) - USGS National Map 3DEP Downloadable Data Collection Retrieved from https://data.usgs.gov/datacatalog/data/USGS:3a81321b-c153-416f-98b7-cc8e5f0e17c3. We note that for mesoscale models coarser data sets can be used, such as the WRF default 30-sec data set.
- Recommended land use data set
    - National Land Cover Dataset 1 arc-sec 2019, about 30 m spatial resolution, can be downloaded from https://doi.org/10.5066/P9KZCM54. We note that WRF can use its default data base.
- Recommended roughness length values
    - We do not impose a fixed roughness length value to the benchmark participants. Instead, this should be considered as a calibration parameter to match the observed atmospheric conditions. In general, the AWAKEN region is characterized by pastures, crops, and scattered trees, so that roughness length values between 0.1-0.2 m seem appropriate. We also note that in WRF the roughness will be calculated by the planetary boundary layer used, based on the selected surface layer scheme.
- King Plain and Armadillo Flats turbine locations and dimensions
    - Can be downloaded from `here <https://app.box.com/s/ho2cf03d1blytt4ga80spnv3uz87tepu>`_. Note: the USGS wind turbine data base information about these two wind farms are NOT accurate.
- Wind turbine model
    - The turbines in the King Plains and Armadillo Flats wind farms are of three different models, as detailed in :doc:`field_site`. For each of the three turbine types, we provide an open-source turbine model, including Cp and Ct curves, RPM table, pitch table, lift and drag table. The open-source model can be found at https:/github.com/NREL/openfast-turbine-models. A report describing the model is available here.
- SCADA
    - TBD
- Recommended reanalysis product
    - TBD
- Observed inflow wind speed, wind direction, and turbulence profiles
    - 10-minute average retrievals of wind speed, wind direction, three wind speed components, TI, and TKE are provided from the scanning lidars at sites A1 and A2. Data are provided every 10 m from 110 m to 4000 m a.g.l.
    - 4-s instantaneous retrievals of wind speed, wind direction, and the three wind components are provided from the scanning lidars at sites A1 and A2. Data are provided every 10 m from 110 m to 4000 m a.g.l.
    - 10-minute average retrievals of wind speed, wind direction, vertical wind speed are provided from the scanning lidar at site E36. Data are provided every 10 m from 98 m to over 10,000 m a.g.l.
    - 10-minute average and 1-second retrievals of horizontal wind speed, wind direction, vertical wind speed (and, for the 1-s data, two horizontal wind components) are provided from the profiling lidar at site B. Data are provided every 20 m from 40 m to 300 m a.g.l.
    - 10-minute average and 1-second retrievals of horizontal wind speed, wind direction, vertical wind speed (and, for the 1-s data, two horizontal wind components) are provided from the profiling lidar at site A1. Data are provided every 20 m from 40 m to 240 m a.g.l.
    - 2-minute average retrievals of horizontal wind speed, wind direction, vertical wind speed are provided from the profiling lidar at site A2. Data are provided every 20 m from 40 m to 220 m a.g.l.
    - data are available in netCDF format `here <https://app.box.com/s/4vvnfbf5kg0w9uvf6xkeo35j1bxcurt6>`_.
    - `this <https://app.box.com/s/8gf7qhs9iakp11pw02c9g3t01ebvxp6z>`_ python script can be used as an example to access and explore these data sets.
- Observed inflow temperature profiles
    - 30-minute average temperature profiles from the surface up to over 15 km (at varying vertical resolution) from the ASSIST-II at site B.
    - 10-minute average temperature profiles from the surface up to over 15 km (at varying vertical resolution) from the ASSIST-II at site E36. Data are not available after 14 UTC.
    - data are available in netCDF format `here <https://app.box.com/s/3uifnj5690yitzc5ipltc7hlg3j18lnk>`_.
    - `this <https://app.box.com/s/zukgw131xpsqr4bbz5iphwtmdw3t85jb>`_ python script can be used as an example to access and explore these data sets.
- Observed inflow near-surface properties (wind speed, wind direction, u, v, w wind components, sonic temperature, sensible heat flux, friction velocity, TKE, Obukhov length)
    - 30-minute average time series at 4 m a.g.l. from sonic anemometers at sites A1, A2, and A5.
    - data are available in netCDF format `here <https://app.box.com/s/g9voxn84yw9bw1coxp5h2hz0muafj1af>`_.
    - `this <https://app.box.com/s/0o2aynluyi9wg4zt6evml4n1et7fxkvr>`_ python script can be used as an example to access and explore these data sets.
More details about the observations can be found in the :ref:`Measurements<measurements>` page.

We note the following:

- all inflow observations are provided in netcdf format. This python script can be used as an example to open and visualize some of the inflow files.

- participants are encouraged to make their own decisions about which inflow data set(s) to use to force their simulations. The results about the 'best' inflow data sets to use will be part of the overall results of the benchmark.

- connected to the above, please refer to this presentation to visualize some of the differences in the provided inflow observations among different AWAKEN sites.

- any parameters not listed above are left to the decisions of the single participants.


Phase 1 submission
---------------------------------

Benchmark participants are required to submit the following by 1 September 2024:


Format
Script to test format




