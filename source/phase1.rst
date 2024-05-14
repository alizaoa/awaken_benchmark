.. _phase1:


.. raw:: html

    <style> .red {color:red} </style>

.. role:: red


.. raw:: html

    <style> .blue {color:blue} </style>

.. role:: blue


Phase 1: the baseline
================================

In Phase 1, the benchmark team releases LIMITED inflow observations at AWAKEN for 24 August 2023 and NREL’s open-source wind turbine model to the benchmark participants.
The participants leverage the limited inputs and their own best practices to simulate the wakes from the King Plains and Armadillo Flats wind plants.
The benchmark team then compares the simulated results with the observed values.

Please read the instructions below in detail.

Phase 1 officially starts on 28 May 2024. Participants are expected to submit results for Phase 1 (as specified below) by 1 September 2024.


Model inputs and recommendations
---------------------------------

The following inputs and recommendations are provided to the benchmark participants:

- Recommended topographical data set
    - USGS 1⁄3 arc-sec Digital Elevation Model (DEM) can be downloaded from the USGS website (https://data.usgs.gov/datacatalog/data/USGS:3a81321b-c153-416f-98b7-cc8e5f0e17c3). We note that for mesoscale models coarser data sets can be used, such as the WRF default 30-sec data set. Below, we provide a suggested step-by-step process on how to use the USGS data in WRF:
	- Download the s11_w041_1arc_v3.tif file from the link above
	- In QGIS, Layer -> Add Layer -> Add Raster Layer; select the s11_w041_1arc_v3.tif file
	- Using the GIS4WRF plugin, GIS4WRF -> Datasets -> Process -> Convert active layer to WPS binary -> Is this layer's data categorical? (NO) -> Save data
	- Copy binaries and index files to a new directory, for instance, “topo_srtm_3s”
	- Move “topo_srtm_3s” to the directory that stores WRF static datasets, which is usually WPS_GEOG
	- Create the new terrain class “topo_srtn_1_3s” in GEOGRID.TBL
	- Select as an option in the WRF namelist.wps
		geog_data_res = 'topo_srtm_1_3s'

- Recommended land use data set
    - National Land Cover Dataset 1 arc-sec 2019, about 30 m spatial resolution, can be downloaded from https://www.sciencebase.gov/catalog/item/604a4fb1d34eb120311b0039. Below, we provide a suggested step-by-step process on how to use this data in WRF:
	- Download the nlcd_2019_land_cover_l48_20210604.zip file from the link above and extract data
	- Import nlcd_2019_land_cover_l48_20210604.img into QGIS (Layer->Add-Layer->Raster->Source)
	- Using the GIS4WRF plugin: Plugins->GIS4WRF->Datasets->Process->Convert active layer to WPS binary, and save it inside a folder named ‘nlcd2019_ll_1s’, for instance
	- Move WPS binaries to the directory that stores WRF static datasets, which is usually WPS_GEOG
	- The GEOGRID.TBL dictionary must create a new object (for example, with the name “nlcd20_1s”) that selects and points to the NLCD 2019 data; later on, this option should be selected in the namelist.wps
	- The LANDUSE.TBL and VEGPARM.TBL dictionaries must create a new object (for example, with the name “NLCD20”) that contains a table that relates the land use categories with surface characteristics, such as roughness
	- The WRF namelist.wps should contain
		geog_data_res = 'nlcd20_1s'
	- The WRF namelist.input should contain
 		num_soil_layers = 4,
 		num_land_cat = 20

- Recommended roughness length values
    - We do not impose a fixed roughness length value to the benchmark participants. Instead, this should be considered as a calibration parameter to match the observed atmospheric conditions. In general, the AWAKEN region is characterized by pastures, crops, and scattered trees, so that roughness length values between 0.03-0.2 m seem appropriate. We also note that in WRF the roughness will be calculated by the land surface model used, and then adopted in the selected surface layer scheme.

- King Plain and Armadillo Flats turbine locations and dimensions
    - Can be downloaded `here <https://app.box.com/s/3mkdtxqmwtg5bhzl6tcahultb60t9lz6>`_. Note: the USGS wind turbine data base information about these two wind farms are NOT accurate.

- Wind turbine model
    - The turbines in the King Plains and Armadillo Flats wind farms are of three different models, as detailed in :doc:`field_site`. For each of the three turbine types, we provide an open-source turbine model, including Cp and Ct curves, RPM table, pitch table, lift and drag table. The open-source model and documentation on how to use it can be found `here <https:/github.com/NREL/openfast-turbine-models>`_.

- Observed inflow wind speed, wind direction, and turbulence. Data also include the day before (23 August 2023) the selected case study if needed.
    - 10-minute average and 1-second retrievals of horizontal wind speed, wind direction, vertical wind speed (and, for the 1-s data, two horizontal wind components) are provided from the profiling lidar at site A1. Data are provided every 20 m from 40 m to 240 m a.g.l.
    - 10-minute average retrievals of TI and TKE are provided from the scanning lidar at site A1. Data are provided at 110 m a.g.l.
    - data are available in netCDF format `here <https://app.box.com/s/o6xh24i0liygn10eh6duup4spd7pxcvu>`_.
    - `this <https://app.box.com/s/3llpu1nybakz9g73gnr29ox3jg4wvbs5>`_ python script can be used as an example to access and explore these data sets.
- Observed inflow temperature. Data also include the day before (23 August 2023) the selected case study if needed.
    - 30-minute average temperature profiles at the surface from the ASSIST-II at site B.
    - data are available in netCDF format `here <https://app.box.com/s/c6m0o6nwkkp937rq4pxz5c2y0j2rg2c9>`_.
    - `this <https://app.box.com/s/maluixmdg8739xru9x5usf9hbh1euxm4>`_ python script can be used as an example to access and explore this data set.
- Observed inflow Obukhov length. Data also include the day before (23 August 2023) the selected case study if needed.
    - 30-minute average time series at 4 m a.g.l. from sonic anemometers at site A1.
    - data are available in netCDF format `here <https://app.box.com/s/ljbkhynxlhltc15vifrd3ava4van9pgq>`_.
    - `this <https://app.box.com/s/zwr18vq18b756l3w3j8uoly44s52uvqk>`_ python script can be used as an example to access and explore this data set.
More details about the observations can be found in the :ref:`Measurements<measurements>` page.

We note that any parameters not listed above are left to the decisions of each participant.


Phase 1 submission
---------------------------------

Benchmark participants are required to submit the following FOUR files by 1 September 2024:

- ONE .txt file with model setup information:
	- domain extension
	- 3D grid resolution
	- temporal resolution
	- other model setup choices (e.g., PBL scheme in WRF)
	- any assumed constants used to run the model (e.g., roughness)

- ONE .netCDF file with modeled atmospheric inflow. The .netCDF file to be filled with simulated data can be found `here <https://app.box.com/s/nf4x11ubp20a00qntbexp4ukcfgzsb61>`_. Do NOT change the structure (e.g., variable names, dimensions) of the file. Please interpolate your simulated data to match the heights listed below whenever reasonable (e.g., if your simulated domain extends to 2 km a.g.l., DO NOT guess/extrapolate any values above that). NaNs should be used anytime simulated data are not available or cannot be interpolated. You can see the coordinates of the AWAKEN sites in the :ref:`Measurements<measurements>` page.
	- Time series of 30-minute average wind speed, wind direction, TKE, Obukhov length and friction velocity (u*) at sites A1, A2, and A5 at 4 m a.g.l..
	- Time series of 10-minute average horizontal wind speed, vertical wind speed, wind direction, TI, and TKE at sites A1, A2, B, and E36 every 10 m from 40 m through 4000 m a.g.l.. 
	- Time series of 10-minute average temperature at sites B and E36 at the following heights: [0, 10, 21, 33, 46, 61, 77, 95, 114, 136, 159, 185, 214, 245, 280, 318, 359, 405, 456, 512, 573, 640, 714, 795, 885, 983, 1092, 1211, 1342, 1486, 1645, 1819, 2011, 2223, 2455, 2710, 2991, 3300, 3640, 4014] m a.g.l.. 

- ONE .netCDF file with modeled turbine response. The .netCDF file to be filled with simulated data can be found `here <https://app.box.com/s/vs2h194c2z2alktwgivzjt1ain4nstle>`_. Do NOT change the structure (e.g., variable names, dimensions) of the file. NaNs should be used where simulated data are not available.
	- Time series of 10-minute average hub-height (80 m or 88.5 m, see heights for various turbines in the spreadsheet linked above) wind speed at the locations (see coordinates in spreadsheet linked above) of all the Armadillo Flats and King Plains turbines.
	- Time series of 10-minute average power produced by each of the Armadillo Flats and King Plains turbines.

- ONE .netCDF file with modeled wake. The .netCDF file to be filled with simulated data can be found `here <https://app.box.com/s/mrjd4om1ffh29d695dqaedyy97b3c9o4>`_. Do NOT change the structure (e.g., variable names, dimensions) of the file. NaNs should be used where simulated data are not available.
	MORE DETAILS TO COME

Each participant should submit the FOUR files (one .txt file, three .netCDF files) in the Box folder communicated to each participant at the beginning of the benchmark. For any question about the result submission, please email nicola.bodini@nrel.gov.




