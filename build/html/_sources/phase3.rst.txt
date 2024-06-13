.. _phase3:


.. raw:: html

    <style> .red {color:red} </style>

.. role:: red


.. raw:: html

    <style> .blue {color:blue} </style>

.. role:: blue


Phase 3: model improvement with inflow and wake observations
================================

In Phase 3, the team releases ALL the wake observations and ALL SCADA to the benchmark participants.
The participants leverage the additional inputs and what learnt in Phase 2 to simulate the wakes from the King Plains and Armadillo Flats wind plants.
The benchmark team then compares the simulated results with the observed values and summarizes results in a journal article.

Please read the instructions below in detail.

Phase 3 officially starts in January 2025, when results from Phase 2 are released. Participants are expected to submit results for Phase 3 (as specified below) by 15 March 2025.


Model inputs and recommendations
---------------------------------

The following inputs and recommendations are provided to the benchmark participants, on top of what has already been released in Phases 1 and 2:

MORE DETAILS TO COME.


Phase 3 submission
---------------------------------

Benchmark participants are required to submit the following FOUR files by 15 March 2025:

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

