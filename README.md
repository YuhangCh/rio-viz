# rio-viz

[![Packaging status](https://badge.fury.io/py/rio-viz.svg)](https://badge.fury.io/py/rio-viz)
[![CircleCI](https://circleci.com/gh/developmentseed/rio-viz.svg?style=svg)](https://circleci.com/gh/developmentseed/rio-viz)
[![codecov](https://codecov.io/gh/developmentseed/rio-viz/branch/master/graph/badge.svg?token=MVVL228Lug)](https://codecov.io/gh/developmentseed/rio-viz)

Rasterio plugin to visualize Cloud Optimized GeoTIFF in browser.

![](https://user-images.githubusercontent.com/10407788/60689165-78be7780-9e88-11e9-84b9-9a3602156ef2.jpg)


Freely adapted from the great [mapbox/rio-glui](https://github.com/mapbox/rio-glui)

### Install

You can install rio-viz using pip

```bash 
$ pip install -U pip cython==0.28
$ pip install rio-viz
```

or from source

```bash
$ git clone https://github.com/developmentseed/rio-viz.git
$ cd rio-viz

# python-vtzero will only compile with Cython < 0.29
$ pip install cython==0.28
$ pip install -e .
```

### How To

```bash 
$  rio viz --help
Usage: rio viz [OPTIONS] SRC_PATHS...

  Rasterio Viz cli.

Options:
  --nodata NUMBER|nan        Set nodata masking values for input dataset.
  --style [satellite|basic]  Mapbox basemap
  --port INTEGER             Webserver port (default: 8080)
  --host TEXT                Webserver host url (default: 127.0.0.1)
  --mapbox-token TOKEN       Pass Mapbox token
  --no-check                 Ignore COG validation
  --simple                   Launch simple viewer
  --help                     Show this message and exit.

Note: 

You can provide multiple paths (e.g: bands stored as separate path) to rio-viz:

```bash
$ rio viz https://s3.eu-central-1.amazonaws.com/remotepixel-eu-central-1/sentinel-s2-l1c/tiles/18/T/XR/2019/4/21/0/B0{4,3,2}.tif
```

### Experimental 

rio-viz supports Mapbox VectorTiles encoding from a raster array. This feature was added to visualize sparse data stored as raster but will also work for dense array. This is highly experimental and might be slow to render in certain browser and/or for big rasters.

![](https://user-images.githubusercontent.com/10407788/56853984-4713b800-68fd-11e9-86a2-efbb041daeb0.gif)


## Contribution & Development

Issues and pull requests are more than welcome.

**dev install**

```bash
$ git clone https://github.com/developmentseed/rio-viz.git
$ cd rio-viz
$ pip install -e .[dev]
```

**Python3.7 only**

This repo is set to use `pre-commit` to run *my-py*, *flake8*, *pydocstring* and *black* ("uncompromising Python code formatter") when commiting new code.

```bash
$ pre-commit install
```

## Authors
Created by [Development Seed](<http://developmentseed.org>)

