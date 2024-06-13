.. _phase2:


.. raw:: html

    <style> .red {color:red} </style>

.. role:: red


.. raw:: html

    <style> .blue {color:blue} </style>

.. role:: blue


Phase 2: model improvement with inflow observations
================================

In phase 2, The team releases ALL the inflow observations and SOME SCADA to the benchmark participants.
The participants leverage the additional inputs and what learnt in Phase 1 to simulate the wakes from the King Plains and Armadillo Flats wind plants.
The benchmark team then compares the simulated results with the observed values. 

Please read the instructions below in detail.

Phase 2 officially starts in October 2024, when results from Phase 1 are released. Participants are expected to submit results for Phase 2 (as specified below) by 15 December 2024.

Model inputs and recommendations
---------------------------------

The following inputs and recommendations are provided to the benchmark participants, on top of what already released in Phase 1 (please read that list, too):

- SCADA
    - TBD
- Recommended boundary and initial condition data set
    - TBD
- Observed inflow wind speed, wind direction, and turbulence profiles
    - 10-minute average retrievals of horizontal wind speed, wind direction, three wind speed components, TI, and TKE are provided from the scanning lidars at sites A1 and A2. Data are provided every 10 m from 110 m to 4000 m a.g.l.
    - 4-s instantaneous retrievals of horizontal wind speed, wind direction, and the three wind components are provided from the scanning lidars at sites A1 and A2. Data are provided every 10 m from 110 m to 4000 m a.g.l.
    - 10-minute average retrievals of horizontal wind speed, wind direction, vertical wind speed are provided from the scanning lidar at site E36. Data are provided every 10 m from 98 m to over 10,000 m a.g.l.
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
- participants are encouraged to make their own decisions about which inflow data set(s) to use to force their simulations. The results about the 'best' inflow data sets to use will be part of the overall results of the benchmark.
- any parameters not listed above are left to the decisions of the single participants.



Phase 2 submission
---------------------------------

Benchmark participants are required to submit the following FOUR files by 15 December 2024:

- ONE .txt file with model setup information:
	- domain extension
	- 3D grid resolution
	- temporal resolution
	- other model setup choices (e.g., PBL scheme in WRF)
	- any assumed constants used to run the model (e.g., roughness)

- ONE .netCDF file with modeled atmospheric inflow. The .netCDF file template to be filled with simulated data can be found `here <https://app.box.com/s/nf4x11ubp20a00qntbexp4ukcfgzsb61>`_. Do NOT change the structure (e.g., variable names, dimensions) of the file. Please interpolate your simulated data to match the heights listed below whenever reasonable (e.g., if your simulated domain extends to 2 km a.g.l., DO NOT guess/extrapolate any values above that). NaNs should be used anytime simulated data are not available (e.g., a model with output available at 2-minute resolution would have 119 NaNs and only 1 value for every 2-minute period in the template) or cannot be interpolated. You can see the coordinates of the AWAKEN sites in the :ref:`Measurements<measurements>` page.
	- Time series of 1-s wind speed, wind direction, TKE, Obukhov length and friction velocity (u*) at sites A1, A2, and A5 at 4 m a.g.l..
	- Time series of 1-s horizontal wind speed, vertical wind speed, wind direction, TI, and TKE at sites A1, A2, B, and E36 every 10 m from 40 m through 4000 m a.g.l.. 
	- Time series of 1-s temperature at sites B and E36 at the following heights: [0, 10, 21, 33, 46, 61, 77, 95, 114, 136, 159, 185, 214, 245, 280, 318, 359, 405, 456, 512, 573, 640, 714, 795, 885, 983, 1092, 1211, 1342, 1486, 1645, 1819, 2011, 2223, 2455, 2710, 2991, 3300, 3640, 4014] m a.g.l.. 

- ONE .netCDF file with modeled turbine response. The .netCDF file to be filled with simulated data can be found `here <https://app.box.com/s/vs2h194c2z2alktwgivzjt1ain4nstle>`_. Do NOT change the structure (e.g., variable names, dimensions) of the file. NaNs should be used where simulated data are not available.
	- Time series of 1-s hub-height (80 m, 88.5 m, or 90 m a.g.l., see heights for various turbines in the spreadsheet linked above) wind speed at the locations (see coordinates in spreadsheet linked above) of all the Armadillo Flats and King Plains turbines.
	- Time series of 1-s power produced by each of the Armadillo Flats and King Plains turbines.

- ONE .netCDF file with modeled wake. The .netCDF file to be filled with simulated data can be found `here <https://app.box.com/s/mrjd4om1ffh29d695dqaedyy97b3c9o4>`_. Do NOT change the structure (e.g., variable names, dimensions) of the file. NaNs should be used where simulated data are not available.
	MORE DETAILS TO COME

Each participant should submit the FOUR files (one .txt file, three .netCDF files) in the Box folder communicated to each participant at the beginning of the benchmark. For any question about the result submission, please email nicola.bodini@nrel.gov.

