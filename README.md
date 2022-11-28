# Benchmarking Cloud Storage Read Throughput for Big Data with Dask
*Jacob Green*  

The work of [Ryan Abernathey et al.](https://github.com/earthcube2020/ec20_abernathey_etal) is expanded upon in this repository, aiming to benchmark cloud storage read throughput of file types essential to Machine Learning, Geospatial, & Weather applications. As the need for on-demand retrival from cloud-based stores increases, documenting the access speeds of widely-used file types is more important than ever before. By using Dask, a pythonic parallel computation library, we can measure the strengths, limitations, and overall performance of parallel reads from the cloud.

The goals of this benchmarking are:
- Measuring read throughput for CSV and NetCDF data formats. These are file types that many are familiar with, and to this day are widely used in all industries.
- Comparing these classic file formats with the read throughput of their cloud native counterparts: Parquet, TileDB Embedded, and Zarr
- Analyzing any gains or drops in read performance when configuring each format with different chunk sizes & compression algorithms. This goal is partiularly important because it will set a precendent on the optimal amount of preprocessing a data set will need before it can be accessed from cloud storage.
- Testing different clouds and how much they alter read speed performance
- Calculating an estimate of storage & egress costs for the same data across different clouds. Keep in mind that the cost estimate will only be for the data tested in this project, but should give a solid basis for price differences between each cloud.

Another focus of this project is to allow users to input their own files into the throughput measurement Jupyter notebook to measure read performance using a local cluster. A distributed cluster of machines may not be easily accessable in many cases, so it is important to be able to measure the capability of a single node to read data in parallel. Through testing using their own hardware & data set(s), users will be able to determine the best file format and amount of parallel reads required for maximum speedup on a given cloud storage provider. Options setting the extent of testing to be done are included in the notebook, so the user has a fair amount of flexibility in how detailed they want the results to be. Editing the code to operate on a distributed cluster is also relatively straightforward, so tests can be performed in any context the user wishes.

This project is still under development, so the scope and other details are subject to change.

## Required Libraries Installation Instructions:
To run the `transferSpeeds.ipynb` Jupyter Notebook, the following commands will need to be run on a new or existing conda environment:
- `conda install dask -c conda-forge`
- `conda install -c conda-forge xarray netCDF4 bottleneck`
- `conda install -c conda-forge intake-xarray`
- `conda install -c conda-forge matplotlib`
- `conda install -c anaconda scipy`
- `conda install -c conda-forge gcsfs`
- `conda install -c conda-forge s3fs`
- `conda install -c conda-forge fastparquet`
- `conda install -c conda-forge h5netcdf`
- `pip install pyarrow`
- `pip install tiledb`

I found this to be the most simple way to run the notebook, but users can choose to install the libraries with whatever method they wish.