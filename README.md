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

      names, n = get_varnames(file)
     
  example output:
  
      print(names)
      
      ['thickness',
       'xVel',
       'yVel',
       'Z_surface',
       'Z_base',
       'dThickness/dt',
       'xbVel',
       'ybVel',
       'dragCoef',
       'viscosityCoef',
       'activeBasalThicknessSource',
       'activeSurfaceThicknessSource']
       
       print(n)
       
       12
  
* `amr_meansdf` unpacks all the variables in each plot file in a directory and calculates the mean for each, extracting the time variable and appending them to a dataframe, creating a timeseries. Currently takes the mean over level 0. 

      path = [path/to/directory]
      files = glob(os.path.join(path, "plot.*"))
      df = amr_meansdf(files)
      
  example output:
  
      print(df)
      
                  thickness       xVel       yVel   Z_surface       Z_base  dThickness/dt  \
      0    696.185707   0.142538  -0.438888  708.435730 -2991.138761 -6.227319e+277   
      1    696.154966  -0.097746  -0.629438  708.414337 -2991.239848  -2.480048e-02   

               xbVel      ybVel       dragCoef  viscosityCoef  \
      0     0.142538  -0.438888  6.227319e+297  6.227319e+297   
      1    -0.097746  -0.629438  6.227319e+297  6.227319e+297   

           activeBasalThicknessSource  activeSurfaceThicknessSource   time  
      0                 1.234568e+300                 1.234568e+300    0.0  
      1                 -7.304886e-02                  9.872002e-02    1.0  

### `b5_plot_functions.py`

* `plot_b5` plots a variable from a BISICLES plot file


* `plot_umod` plot velocity magnitude from a BISICLES plot file
