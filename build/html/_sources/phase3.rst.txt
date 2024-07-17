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

- ONE .txt file with model setup information:
	- domain extension
	- 3D grid resolution
	- temporal resolution
	- other model setup choices (e.g., PBL scheme in WRF)
	- any assumed constants used to run the model (e.g., roughness)
	- how your model calculates TI and TKE (if it does -- see more details below)
	- If you use any observations not directly provided as part of the benchmark (i.e., listed on this page), please make note of it in this file, and specify what you used and to do what.

- ONE .netCDF file with modeled atmospheric inflow. The .netCDF file template to be filled with simulated data can be found `here <https://app.box.com/s/nf4x11ubp20a00qntbexp4ukcfgzsb61>`_. Do NOT change the variable names and heights in the file. Please interpolate your simulated data to match the heights listed below whenever reasonable (e.g., if your simulated domain extends to 2 km a.g.l., DO NOT guess/extrapolate any values above that). Please DO change the temporal dimension in the template to match that of your model output. If your model output is available at really high frequency, such that the file to submit would become too big, please do NOT calculate averages, and just submit instantaneous data at whatever time resolution you feel comfortable submitting results at. Please only submit TI and TKE if your model directly outputs them. If that is the case, please specify in the .txt file above how they are calculated (averaging time, center of the window, etc.). If your model does NOT directly calculate TI and TKE, please do NOT provide them in the submitted file, and we will calculate them ourselves whenever possible to ensure consistency. NaNs should be used where simulated data are not available. You can find the coordinates of the AWAKEN sites in the :ref:`Measurements<measurements>` page.
	- Time series of u, v, w, wind speed, wind direction, TI, TKE, Obukhov length at sites A1, A2, and A5 at 4 m a.g.l..
	- Time series of u, v, w, wind speed, wind direction, TI, TKE at sites A1, A2, B, and E36 every 10 m from 40 m through 4000 m a.g.l.. 
	- Time series of temperature at sites B and E36 at the following heights: [0, 10, 21, 33, 46, 61, 77, 95, 114, 136, 159, 185, 214, 245, 280, 318, 359, 405, 456, 512, 573, 640, 714, 795, 885, 983, 1092, 1211, 1342, 1486, 1645, 1819, 2011, 2223, 2455, 2710, 2991, 3300, 3640, 4014] m a.g.l.. 

- ONE .netCDF file with modeled turbine response. The .netCDF file to be filled with simulated data can be found `here <https://app.box.com/s/vs2h194c2z2alktwgivzjt1ain4nstle>`_. Do NOT change the variable names and heights in the file. The same considerations as above apply for the time resolution of the results to submit. NaNs should be used where simulated data are not available.
	- Time series of hub-height (80 m, 88.5 m, or 90 m a.g.l., see heights for various turbines in the spreadsheet linked above) wind speed at the locations (see coordinates in spreadsheet linked above) of all the Armadillo Flats and King Plains turbines. Note: these simulated values will be compared with those from the turbine SCADA, whose values are reported AFTER a nacelle transfer function is applied.
	- Time series of power produced by each of the Armadillo Flats and King Plains turbines.

- ONE .netCDF file with modeled wake. The .netCDF file to be filled with simulated data can be found `here <https://app.box.com/s/mrjd4om1ffh29d695dqaedyy97b3c9o4>`_. Do NOT change the variable names and heights in the file. The same considerations as above apply for the time resolution of the results to submit. NaNs should be used where simulated data are not available. You can see the coordinates of the AWAKEN sites in the :ref:`Measurements<measurements>` page.
	- Time series of u, v, w, wind speed, wind direction, TI, TKE at sites C1a, H, and Golf Course every 10 m from 40 m through 4000 m a.g.l..
	- Time series of u, v, w, wind speed, wind direction, TI, TKE, Obukhov length at sites C1a, G, and H at 4 m a.g.l..
	- Time series of temperature at sites H, C1a, G, and Golf Course at the following heights: [0, 10, 21, 33, 46, 61, 77, 95, 114, 136, 159, 185, 214, 245, 280, 318, 359, 405, 456, 512, 573, 640, 714, 795, 885, 983, 1092, 1211, 1342, 1486, 1645, 1819, 2011, 2223, 2455, 2710, 2991, 3300, 3640, 4014] m a.g.l.. 
	- Evolution of wind speed and wind direction across eight horizontal planes north of the E06 King Plains turbine. Height a.g.l. (m) of the eight horizontal planes: 27, 59, 90.5, 122, 154, 217.5, 281, 344.5. Note that the data shall be compiled using a coordinate system centered on the E06 turbine, with x being north-south, y east-west, z vertical. In the template, for each horizontal plane, the x dimension varies from 0 (i.e., the turbine) to ~ +4 km (i.e., north of the turbine) at every 127 m (i.e., 1 rotor diameter); the y dimension varies from -2.54 km (i.e., west of the turbine) to +2.54 km (i.e., east of the turbine) at every 127 m (i.e., 1 rotor diameter).

Notes: 
	- in the above, u is the wind component along the North-South direction (positive going from South to North), u is the wind component along the East-West direction (positive going from West to East), w is the vertical component (positive going up).
	- more in general, units for all variables are detailed in the Glossary page here on the website.
	- we are also now providing python scripts that can be used to create templates with a different time resolution from the one provided by us. These scripts are really easy to use (they only require modifying ONE number as detailed in the scripts). The scripts are available in the same Box folders linked above.

Each participant should submit the FOUR files (one .txt file, three .netCDF files) in the Box folder communicated to each participant at the beginning of the benchmark. For any question about the result submission, please email nicola.bodini@nrel.gov.

