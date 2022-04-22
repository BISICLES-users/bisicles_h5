# bisicles_h5

Collection of functions for the analysis and plotting of BISICLES plot files, using h5py and bisiclesh5. 

Prerequisites:

* bisiclesh5 (python_reader repository)
* pandas
* h5py
* joblib
* multiprocessing
* matplotlib

### `b5_analysis_functions.py`

* `get_varnames` unpacks variable names in a plot file and the number of components, returning a list and integer. 


* `amr_meansdf` unpacks all the variables in each plot file in a directory and calculates the mean for each and appending them to a dataframe, creating a timeseries. 



### `b5_plot_functions.py`

* `plot_b5` plots a variable from a BISICLES plot file


* `plot_umod` plot velocity magnitude from a BISICLES plot file
