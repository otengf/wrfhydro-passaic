# wrfhydro-passaic
Developing an AI-Driven Hydroclimate Forecasting for Resilience: A Physics-Informed Framework for Climate Early-Warning Systems
Objectives:
1.	Construct and calibrate the physics models (i.e. WRF-Hydro/Noah-MP) against hydroclimatic observations in the Passaic River Basin (NJ).
2.	Develop a PINN to correct WRF-Hydro/NOAH-MP evapotranspiration (ET) biases using physical constraints.
3.	Train an LSTM ensemble on corrected outputs to produce probabilistic forecasts.
4.	Deliver an open-source, operational prototype capable of unified flood-drought forecasting.

# Progress Update

I have successfully completed the following steps:
1. Downloaded the model code (https://ral.ucar.edu/projects/wrf_hydro/model-code) and followed the Technical Description and User Guides (https://wrf-hydro.readthedocs.io/en/latest/index.html).
2. Built the model and ran a provided Test Case with 'idealized' forcing to ensure my setup is correct.
3. Ran the test case with one of the configurations available and compared my model output with the provided output files.

Next steps:
- Create customized geographical inputs and forcing data.
- Run the model with customized geographical inputs, the land surface model only, and idealized forcing.
