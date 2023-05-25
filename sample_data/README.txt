Files:

h1.2000-11-15-10800.t0.nc ~ one time step from atmospheric rivers data (unstructured MPAS data)

h1.2000-11-15-10800.t0_720x1440 ~ a regridded regular Cartesian data set
h1.2000-11-15-10800.t0_360x720 ~ a smaller regridded data set

h1_2000-11-15-10800_nc_IVT_24.png ~ a sample image of what the IVT variable looks like when rendered




Some stats on the unstructured data set from Xarray:

>>> d = xr.open_dataset('h1.2000-11-15-10800.nc')
>>> d
<xarray.Dataset>
Dimensions:    (time: 8, ncol: 835586, nbnd: 2)
Coordinates:
  * time       (time) object 2000-11-15 03:00:00 ... 2000-11-16 00:00:00
Dimensions without coordinates: ncol, nbnd
Data variables:
    IVT        (time, ncol) float32 ...
    PRECT      (time, ncol) float32 ...
    TMQ        (time, ncol) float32 ...
    lat        (ncol) float64 ...
    lon        (ncol) float64 ...
    time_bnds  (time, nbnd) object ...
Attributes:
    Conventions:       CF-1.0
    source:            CAM
    case:              mass-scaling-fhist-ca-4608-l58-pmidfix-newdiag-200010-...
    logname:           xyhuang
    host:              cheyenne4
    initial_file:      /glade/scratch/xyhuang/MPAS-Model/ca.gridtopo.cfsr.ini...
    topography_file:   /glade/scratch/xyhuang/MPAS-Model/mpas_60_3_CA_nc3000_...
    model_doi_url:     https://doi.org/10.5065/D67H1H0V
    time_period_freq:  hour_3
    history:           Wed Mar  8 15:00:35 2023: ncks -v TMQ,IVT,PRECT,lat,lo...
    NCO:               netCDF Operators version 5.0.3 (Homepage = http://nco....

>>> d.min()
<xarray.Dataset>
Dimensions:    ()
Data variables:
    IVT        float64 0.1014
    PRECT      float64 0.0
    TMQ        float64 0.09367
    lat        float64 -89.9
    lon        float64 0.007309
    time_bnds  object 2000-11-15 00:00:00

>>> d.max()
<xarray.Dataset>
Dimensions:    ()
Data variables:
    IVT        float64 2.816e+03
    PRECT      float64 2.019e-05
    TMQ        float64 85.0
    lat        float64 89.94
    lon        float64 360.0
    time_bnds  object 2000-11-16 00:00:00
