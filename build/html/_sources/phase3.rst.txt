.. _phase3:


.. raw:: html

    <style> .red {color:red} </style>

.. role:: red


.. raw:: html

    <style> .blue {color:blue} </style>

.. role:: blue


Phase 3: model improvement with inflow and wake observations
================================

Slides that show phase 2 results can be downloaded `here <https://app.box.com/s/kf9i4fzy9qqzhagf8ozpv8nty48n8zpa>`_.

In phase 3, The team releases ALL the inflow and wake observations and all King Plains SCADA to the benchmark participants.
The participants leverage the additional inputs and what learnt in Phase 1 and 2 to simulate the wakes from the King Plains and Armadillo Flats wind plants.
The benchmark team then compares the simulated results with the observed values and summarizes results in a journal article.

Please read the instructions below in detail.

Phase 3 officially starts on 13 March 2024, when results from Phase 2 are released. Participants are expected to submit results for Phase 3 (as specified below) by 30 April 2025.


UPDATES from phase 2
---------------------------------

- A reminder that USGS has wrong information for Armadillo Flats, please use the information we provide.


Model inputs and recommendations
---------------------------------

The following inputs and recommendations are provided to the benchmark participants, on top of what already released in Phase 1 and 2 (please read those list, too):

- SCADA
    - Normal operation: the following King Plains turbines were shut down the whole time on 24 August 2023: WIT_USKPL_SS001_WT011, WIT_USKPL_SS001_WT029, and WIT_USKPL_SS001_WT079. These four turbines were removed from the updated turbine location spreadsheet `here <https://app.box.com/s/segeqxz9dkayycrsyjdimgqsn1mynj8m>`_
    - Curtailment: we provide a 1-min time series, for each King Plains turbine, with a binary flag to indicate derated/curtailed operation. 1 = derated, 0 = normal.
    - Yaw misalignment: we provide a 1-min time series, for each King Plains turbine, of the yaw misalignment.
    - Power production: we provide a 1-min average time series of power produced by all King Plains turbines. 
    - Wind speed: we provide a 1-min average time series of wind speed measured by the anemometers on the nacelle of each King Plains turbine.
    - Wind direction: we provide a 1-min average time series of wind direction measured by the anemometers on the nacelle of each King Plains turbine. 
    - Data are available in netCDF format `here <https://app.box.com/s/jrhjer0bd0b5ztpdjg25z1immqmkf83r>`_.

- Observed wake wind speed, wind direction, and turbulence profiles
    - 10-minute average retrievals of horizontal wind speed, wind direction, three wind speed components, TI, and TKE are provided from the scanning lidar at site H. Data are provided every 10 m from 110 m to 4000 m a.g.l.
    - 4-s instantaneous retrievals of horizontal wind speed, wind direction, and the three wind components are provided from the scanning lidars at site H. Data are provided every 10 m from 110 m to 4000 m a.g.l.
    - 10-minute average retrievals of horizontal wind speed, wind direction, vertical wind speed are provided from the scanning lidar at site Golf Course. Data are provided every 20 m from 98 m to over 10,000 m a.g.l.
    - 10-minute average and 20-second retrievals of horizontal wind speed, wind direction, vertical wind speed are provided from the profiling lidar at site H. Data are provided every 20 m from 40 m to 240 m a.g.l.
    - 2-minute average retrievals of horizontal wind speed, wind direction, vertical wind speed are provided from the profiling lidar at site C1a. Data are provided every 20 m from 40 m to 220 m a.g.l.
    - data are available in netCDF format `here <https://app.box.com/s/lchdu36cylrevpukqir0ardaaicc6jqj>`_.
- Observed wind speed from a nacelle-mounted lidar
    - A scanning lidar is mounted on the nacelle roof of King Plain's turbine E06 (GPS coordinates: 36°24’39.708”N 97°24’21.24”W), and performs a variety of scans which sample both the inflow and the wake of the turbine (at different times), with a scanning strategy that is repeated every 2 hours. The details of the various scans are described below.
    - inflow turbulence scans (00:00-00:30 and every 2 hours after that): PPI scans which provide instantaneous radial wind speed over horizontal hub-height plane.
    - wake meandering scans (00:30-01:00 and every 2 hours after that): PPI and RHI scans which provide instantaneous radial wind speed over horizontal hub-height plane and over vertical plane aligned with turbine yaw position.
    - inflow statistics scans (01:00-01:20 and every 2 hours after that): PPI scans which provide 20-minute average streamwise wind speed and its standard deviation at 3D locations.
    - wake 3D statistics scans (01:00-01:40 and every 2 hours after that): PPI scans which provide 20-minute average streamwise wind speed and its standard deviation at 3D locations.
    - farm statistics scans (01:40-02:00 and every 2 hours after that): volumetric scans which provide 20-minute average streamwise wind speed and its standard deviation at 3D locations.
    - data are available in netCDF format `here <https://app.box.com/s/umrbo144lzb0rdfqsotyeezbh7av7vvk>`_.
- Observed downwind temperature profiles
    - 30-minute average temperature profiles from the surface up to over 15 km (at varying vertical resolution) from the ASSIST-II at site C1a and G.
    - 10-minute average temperature profiles from the surface up to over 15 km (at varying vertical resolution) from the ASSIST-II at site Golf Course.
    - data are available in netCDF format `here <https://app.box.com/s/9nysnm1mf1tcwhicwcibmluoebzfjb4u>`_.
- Observed downwind near-surface properties (wind speed, wind direction, u, v, w wind components, sonic temperature, sensible heat flux, friction velocity, TKE, Obukhov length)
    - 30-minute average time series at 4 m a.g.l. from sonic anemometers at sites G and H.
    - data are available in netCDF format `here <https://app.box.com/s/iwf4xgs21qp8iiyjmzh2zgvqh08hbgfi>`_.
More details about the observations can be found in the :ref:`Measurements<measurements>` page.

We note the following:
- participants are encouraged to make their own decisions about which inflow data set(s) to use to force their simulations. The results about the 'best' inflow data sets to use will be part of the overall results of the benchmark.
- any parameters not listed above are left to the decisions of the single participants.


Phase 3 submission
---------------------------------

Benchmark participants are required to submit the following FOUR files by 15 December 2024:

- ONE .txt file with model setup information:
	- domain extension
	- 3D grid resolution
	- temporal resolution (and specify if results are being submitted as averages or instantaneous values)
	- other model setup choices (e.g., PBL scheme in WRF)
	- any assumed constants used to run the model (e.g., roughness)
	- how your model calculates TI and TKE (if it does -- see more details below)
	- If you use any observations not directly provided as part of the benchmark (i.e., listed on this page), please make note of it in this file, and specify what you used and to do what.
	- What forcing data (e.g., reanalysis) you used to force your simulation, if any.
	- Your WRF namelists (for WRF-based models only).
	- What phase 3 input observations you leveraged.

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
	- in the above, v is the wind component along the North-South direction (positive going from South to North), u is the wind component along the East-West direction (positive going from West to East), w is the vertical component (positive going up).
	- more in general, units for all variables are detailed in the Glossary page here on the website.
	- we are also now providing python scripts that can be used to create templates with a different time resolution from the one provided by us. These scripts are really easy to use (they only require modifying ONE number as detailed in the scripts). The scripts are available in the same Box folders linked above.

Each participant should submit the FOUR files (one .txt file, three .netCDF files) in the Box folder communicated to each participant at the beginning of the benchmark. For any question about the result submission, please email nicola.bodini@nrel.gov.

