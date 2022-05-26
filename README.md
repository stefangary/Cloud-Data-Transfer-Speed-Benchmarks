# Benchmarking Google Cloud Storage Read Throughput for Big Data with Dask
*Jacob Green*  

The work of [Ryan Abernathy](https://github.com/earthcube2020/ec20_abernathey_etal) is expanded upon in this repository,  
aiming to benchmark cloud storage read throughput of file types essential to Machine Learning, Geospatial, & Weather applications.  
As the need for on-demand retrival from cloud-based stores increases, documenting the access speeds of widely-used file types is more  
important than ever before. By using Dask, a pythonic parallel computation library, we can measure the strenths, limitations, and  
overall performance of parallel reads from the cloud.  

The goals of this benchmarking are:
- Measuring read throughput for CSV, NetCDF, and grib2 data formats. These are file types that many are familiar with, and to this day  
are widely used in all industries.
- Comparing these classic file formats with the read throughput of their cloud native counterparts: AVRO, ORC, Parquet, TileDB Embedded, and Zarr
- Analyzing any gains or drops in read performance when partitioning big data into subfiles. This goal is partiularly important because it will 
set a precendent on the optimal amount of preprocessing a data set will need before it can be accessed from cloud storage.
