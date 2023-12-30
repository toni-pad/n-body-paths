# n-body-paths
Calculating paths in the Solar System

# Getting the data
First point is get the position and velocity and mass of Solar System elements.
It is available at [Horizons project from NASA´s Jet Propulsion Laboratory](https://ssd.jpl.nasa.gov/horizons/).
Using the API, all the information for bigger objects can be obtained.

First, you can get the list of all Major Body with command:
```
https://ssd.jpl.nasa.gov/api/horizons.api?format=text&COMMAND='MB'
```

And then, use a sigle call for every object using the ID# value in the list. To get the Earth center (ID#399) related to the Solar System Barycenter (SSB) in the Voyager 1 land-off is like that:
```
https://ssd.jpl.nasa.gov/api/horizons.api?format=text&COMMAND='399'&OBJ_DATA='YES'&MAKE_EPHEM='YES'&EPHEM_TYPE='VECTORS'&CENTER='*@SSB'&START_TIME='1977-09-05'&STOP_TIME='1977-09-06'&STEP_SIZE='1 d'&QUANTITIES='1,29'&OUT_UNITS='KM-S'
```

Or you can get physical data of the object with:
```
https://ssd.jpl.nasa.gov/api/horizons.api?format=text&COMMAND='399'&OBJ_DATA='YES'&OUT_UNITS='KM-S'
```
And just the ephemeris with
```
https://ssd.jpl.nasa.gov/api/horizons.api?format=text&COMMAND='399'&OBJ_DATA='NO'&MAKE_EPHEM='YES'&EPHEM_TYPE='VECTORS'&CENTER='*@SSB'&START_TIME='1977-09-05'&STOP_TIME='1977-09-06'&STEP_SIZE='1 d'&QUANTITIES='1,29'&OUT_UNITS='KM-S'
```
