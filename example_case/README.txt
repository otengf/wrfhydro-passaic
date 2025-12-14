#Overview This test case includes prepared geospatial data and input files for a
sample domain (region of interest) and prepared forcing data.  This domain is a
small region (15km x 16km) encompassing the West Branch of the Croton River, NY,
USA (USGS stream gage 0137462010) during Hurricane Irene, 2011-08-26 to 2011-09-02.
The simulation begins with a restart from a spinup period from 2010-10-01 to
2011-08-26. The forcing data prepared for this test case is NOAA Analysis of Record
for Calibration (AORC) hourly data. There are 3 basic routing configurations
included in the test case, National Water Model (NWM), Gridded, and NCAR Reach.

See the WRF-Hydro V5.4 Technical Description located at https://wrf-hydro.readthedocs.io/
for a more detailed description of model physics options, configurations, and input files.
However, some non-standard files will be described below.

For instructions on how to set up and run this test case see the Test Case User
Guides available at https://wrf-hydro.readthedocs.io/en/latest/appendices.html

#Directory contents Croton_NY: directory containing all input files for the
Croton, NY example test case
	|
	-FORCING: Directory containing all AORC hrldas formatted hourly
	forcing data for the simulation period.
	-Gridded: Directory containing all files required for the gridded routing
	configuration with lakes included
		|
		-DOMAIN: Directory containing all geospatial data and input files for
		the Gridded routing option.
		-lake_shapes: directory containing shape files that define lakes
		-RESTART: Directory containing model restart files for the Gridded
		routing option.
		-referenceSim: Directory containing restart files and a hydrograph from
		a successful run for reference
		-hydro.namelist: Fortran namelist file for the hydro model.
		-namelist.hrldas: Fortran namelist file for the Noah-MP land surface
		model.
		-croton_frxst_pts_csv.csv: .CSV formatted file of gage locations in
		latitude/longitude coordinates (WGS84)
	-Gridded_no_lakes: Directory containing all files required for the gridded routing
	configuration without lakes
		|
		-DOMAIN: Directory containing all geospatial data and input files for
		the Gridded routing option
		-RESTART: Directory containing model restart files for the Gridded
		routing option.
		-referenceSim: Directory containing restart files and a hydrograph from
		a successful run for reference
		-hydro.namelist: Fortran namelist file for the hydro model.
		-namelist.hrldas: Fortran namelist file for the Noah-MP land surface
		model.
		-croton_frxst_pts_csv.csv: .CSV formatted file of gage locations in
		latitude/longitude coordinates (WGS84)
	-NWM: Directory containing all files required for the National Water Model
	(NWM) routing configuration
		|
		-DOMAIN: Directory containing all geospatial data and input files for
		the NWM routing option.
			|
			-RouteLink_nudgeEdit.nc: An edited route link file with one gage
			removed from nudging
		-RESTART: Directory containing model restart files for the NWM routing
		option.
		-referenceSim: Directory containing restart files and hydrograph from a
		successful run for reference
		-nudgingTimeSliceObs: Directory containing nudging "time slice"
		observation files.
		-hydro.namelist: Fortran namelist file for the hydro model.
		-namelist.hrldas: Fortran namelist file for the Noah-MP land surface
		model.
	-Reach: Directory containing all files required for NCAR reach routing
		configuration
		|
		-DOMAIN: Directory containing all geospatial data and input files for
		the NCAR reach routing option.
		-stream_network: directory containing files that define the stream
		network.
		-RESTART: Directory containing model restart files for the NCAR reach
		routing option.
		-referenceSim: Directory containing restart files and hydrograph from a
		successful run for reference
		-hydro.namelist: Fortran namelist file for the hydro model.
		-namelist.hrldas: Fortran namelist file for the Noah-MP land surface
		model.
	-Supplemental: Directory containing supplemental files used to create the example
	case, including forcing files used for spinup
		|
		-supplimental_forcing.tar.gz: Tar ball containing additional forcing
		data for spinup
		-namelist.wps: Reduced namelist.wps used to create the geogrid file using
		the WRF-Hydro geogrid Docker utilitiy.
		-supp_precip.tar.gz: Supplemental regridded StageIV precipitation data.
	-USGS-Obs.csv: csv files containing USGS 15 minute streamflow data for
	gages in the domain.
	-study_map.PNG: Study area map
	-namelist_patches.json: json file used by wrfhydropy python package for
	namelist parsing
