# Dask examples

This repo stores dask examples that were developed for NCI’s training purposes. They are being released through NCI’s training site after a period of peer-review.

Notes:

1. Those examples are in dev mode, hence might not be perfect such as comments, structure and design, etc. Feedback is welcome to help improve the quality.
2. More examples may be added from time to time. Therefore, you might see something different when cloning the repo each time.
3. A few packages will need to installed: graphviz, holoviews, datashader, pyarrow, bottleneck etc.
4. Typos might not be checked throughout.
5. Some examples (especially the toy problem ones) are copied from dask tutorial git repo, which are referenced inside of the examples.
6. Creating cluster like the cell below is not necessary when running some of the examples. It was designed to demonstrate distributed calculation through the dask dashboard when running those examples in the Pangeo environment on Gadi. You can decide whether to use it according to your own interests.

```
From dask.distributed import Client,LocalCluster
client = Client(scheduler_file=’scheduler.json’)
print(client)
```

| Example | datasets | description |
| --- | --- | --- |
| 1_11_basics | toy | Dask array, lazy loading and graph visualisation, progress bar, etc |
| 1_12_chunks | CMIP6 – oi10 | Read in CMIP6 by giving a chunksize |
| 1_13_delayed_toy | toy | Dask.delayed utility, apply it to a loop example to accelerate |
| 1_14_delayed_pandas_paleoceanography | Paleo climate csv | Apply dask.delayed to paleoclimate records (in csv files)<br> **Note:** Running this example on local computer is fine, but not on HPC with csv files not found error. I found [a similar issue](https://stackoverflow.com/questions/50987030/file-not-found-error-in-dask-program-run-on-cluster) and it may explain why and work arounds are discussed. |
| 1_15_dataframes_weather station | rainfall csv | Read in BoM rainfall csv data as dask.dataframe, and loop over a number of csv files (as chunks) to demonstrate distributed graph calculation.<br> Read/Write to Parquet for a better performance |
| 1_16_schedulars_weather station | rainfall csv | Apply Dask Schedulers (local thread, local processes, single thread, distributed schedulars) to the same workflow above. |
| 1_17_Numpy_AGDC <br> **Note:** The first little session needs a large HDF5 file. Given the git limits on file size, I can not make it available, but I can make it available on gadi:/scratch/public/jbw900/data/ <br> the last line, save to hdf5 does not work. | Gridded precipitation – rr8 | Synthetic data to demonstrate Dask Array (similar to NumPy Array). Explain parallelism (by chunks) on array for better performance by applying to AGDC datasets. |
| 1_18_DataArray_Xarray_CMIP6 <br>**Note:** Sometimes, I got killworker msg. | CMIP6 – fs38 | Dask.dataArray vs. Xarray.dataArray with the same standard xarray operations. |
| 1_19_Xarray_Gridded_Percipitation | CMIP6 – fs38 | Analysis of Gridded Ensemble Precipitation Estimates using CMIP6 model output. Extract a time series of annual maximum precipitation events over a region |
| 1_20_ ocean model_analysis_visulisation | CMIP6 – oi10 – GFDL highresSST-future | Using Holoviews and Datashader to visualise data <br> **Known issue:** Datashader shows snapshot very slowly |

| Example | Description |
| --- | --- |
| Dask_01_basics.ipynb |  |
| Dask_02_data_chunks_CMIP6.ipynb |  |
| Dask_03_fundermentals_Delayed.ipynb |  |
| Dask_04_delayed_pandas_palioceanography.ipynb |  |
| Dask_05_dataframes_ACTweather.ipynb |  |
| Dask_06_schedulers_ACTweather.ipynb |  |
| Dask_07_numpy_temperature.ipynb |  |
| Dask_08_xarray_CMIP6.ipynb |  |
| Dask_09_Xarray_precipitation.ipynb |  |
| Dask_10_interactive_visualise_CMIP6.ipynb |  |
| Dask_11_diagnositc_tools.ipynb |  |
| Dask_12_intensive_calculation_eReef.ipynb |  |
| Dask_13_distributed_dataframes_geochem.ipynb |  |
| Dask_14_distributed_advanced.ipynb |  |
| Dask_15_memory_compute_management.ipynb |  |
| Dask_16_bag.ipynb |  |
| Dask_17_machine_learning.ipynb |  |

dask-profile.html
dataframe_graph.pdf
graph.pdf
mydask.png
myfile.html
profile.html
scheduler.json
task-stream.html
% Can these files be cleaned up or moved to a subfolder?

Data used in these examples is licenced under the Creative Commons CC-BY4.0 licence (CHECK??), further information available (???). The images used in the 'images' directory are sourced from ????? and used with permision (CHECK??)
