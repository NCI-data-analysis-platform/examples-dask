# Dask examples

This repo stores dask examples that were developed for NCI’s training purposes. They are being released through NCI’s training site after a period of peer-review.

Notes:

1. Feedback is welcome to help improve the quality. Please provide feedback via git pull request or issues.
2. More examples may be added from time to time. Therefore, you might see something different when cloning the repo each time.
3. **Requirements:** A few packages will need to installed: graphviz, holoviews, datashader, pyarrow, bottleneck etc.
4. Some examples (especially the toy problem ones) are copied from dask tutorial git repo, which are referenced inside of the examples.
5. Creating a cluster like the cell below is not necessary when running some of the examples. It was designed to demonstrate distributed calculation through the dask dashboard when running those examples in the Pangeo environment on Gadi. You can decide whether to use it according to your own interests.

```
From dask.distributed import Client,LocalCluster
client = Client(scheduler_file=’scheduler.json’)
print(client)
```

| Example | datasets | description |
| --- | --- | --- |
| 1_20_ ocean model_analysis_visulisation | CMIP6 – oi10 – GFDL highresSST-future | Using Holoviews and Datashader to visualise data <br> **Known issue:** Datashader shows snapshot very slowly |

| Example | Description |
| --- | --- |
| Dask_01_basics.ipynb | Dask provided tutorial: dask array, lazy loading and graph visualisation, progress bar, etc |
| Dask_02_data_chunks_CMIP6.ipynb | Read in CMIP6 data and explore chunksize |
| Dask_03_fundamentals_Delayed.ipynb | Dask provided: Dask.delayed utility, apply to a loop to accelerate |
| Dask_04_delayed_pandas_paleoceanography.ipynb | Apply dask.delayed to paleoclimate records (in csv files)<br> **Note:** This example will only work for members of NCI project dk92 operating on the filesystem. Data needs to be made independently available. |
| Dask_05_dataframes_ACTweather.ipynb | Read in BoM rainfall csv data as dask.dataframe, and loop over a number of csv files (as chunks) to demonstrate distributed graph calculation. Read/Write to Parquet to demonstrate better performance |
| Dask_06_schedulers_ACTweather.ipynb | Apply Dask Schedulers (local threads, local processes, single thread, distributed schedulers) to the same workflow above. |
| Dask_07_numpy_temperature.ipynb | Dask provided tutorial: Numpy and dask analogues. Example using Australian rainfall data. |
| Dask_08_xarray_CMIP6.ipynb | Dask.dataArray vs. xarray.dataArray with the same standard xarray operations, persist data in memory. |
| Dask_09_Xarray_precipitation.ipynb | Analysis of Gridded Ensemble Precipitation Estimates using CMIP6 model output. Extract a time series of annual maximum precipitation from an ensemlbe at a point. |
| Dask_10_interactive_visualise_CMIP6.ipynb |  |
| Dask_11_diagnositc_tools.ipynb |  |
| Dask_12_intensive_calculation_eReefs.ipynb |  |
| Dask_13_distributed_dataframes_geochem.ipynb |  |
| Dask_14_distributed_advanced.ipynb |  |
| Dask_15_memory_compute_management.ipynb |  |
| Dask_16_bag.ipynb |  |
| Dask_17_machine_learning.ipynb |  |

dask-profile.html
mydask.png
myfile.html
profile.html
task-stream.html
% Can these files be cleaned up or moved to a subfolder?

Data used in these examples is licenced under the Creative Commons CC-BY4.0 licence (CHECK??), further information available (???). The images used in the 'images' directory are sourced from ????? and used with permision (CHECK??)
