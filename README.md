# Water-Classification-GEE
## Paper
* ### A full-automated and high-accuracy surface water mapping framework with robust training sample generation and temporal correction of contaminated images based on Google Earth Engine

## Abstract
　In the context of global climate changes and intensified human activities, efficient and continuous monitoring on surface water dynamics is essential for water resources management and protection. Abundant efforts have been devoted to the task of water mapping base on remote sensing images. However, few studies have fully considered the diverse spectral properties varied with water occurrence differences for the collection of reference samples in an automatic manner. Moreover, the statistics of water area were highly sensitive to the observation quality of satellite images, which lead to significant inconsistency among long-term continuous water datasets. This study aimed to develop a full-automatic GEE-based surface water mapping framework based on supervised random forest classifier. Firstly, we built a robust scheme to automatically construct training samples by merging the information from multi-source water occurrence products, i.e., the Joint Research Center’s (JRC) [Global Surface Water Dataset](https://global-surface-water.appspot.com/) (GSWD) and [global inland water dynamics datasets](https://www.glad.umd.edu/dataset/global-surface-water-dynamics) released by the Global Land Analysis and Discovery (GLAD) laboratory. The samples for permanent and seasonal water were mapped and collected separately, and then composited the final sample sets reflecting the spectral diversity of dynamic water targets. Secondly, an automatic temporal correction method was applied to repair the classified maps with invalid observations, thus reduce the uncertainties of derived water occurrence. The proposed framework was tested at five different sites in China. Overall, validation results showed that the proposed method can generate reliable samples (OA: 99.0%, Kappa: 0.966), and produce good-quality water mapping results (OA: 98.6%, Kappa: 0.957). Comparative tests indicated that the proposed method produced water maps with higher quality than the index-based detection methods, as well as GSWD and GLAD datasets. Besides, the temporal correction of contaminated information effectively reduced the uncertainties of derived water statistics. With the full-automatic processing pipeline, the proposed framework can be applied on spatially adaptive scales, thus better delineate the spatial and temporal characteristics of surface water. 

## About the algorithm
* #### This algorithm is based on [Google Earth Engine](https://earthengine.google.com/) (GEE) and [geemap](https://geemap.org/), so if you want to use it, it is essential for you to have a GEE account and install geemap.
* **About [GEE](https://earthengine.google.com/),** it combines a multi-petabyte catalog of satellite imagery and geospatial datasets with planetary-scale analysis capabilities. Scientists, researchers, and developers use Earth Engine to detect changes, map trends, and quantify differences on the Earth's surface. Earth Engine is now available for commercial use, and remains free for academic and research use. During the past few years, GEE has become very popular in the geospatial community and it has empowered numerous environmental applications at local, regional, and global scales. GEE provides both JavaScript and Python APIs for making computational requests to the Earth Engine servers.
* **About [geemap](https://geemap.org/),** it is a Python package for interactive mapping with [Google Earth Engine](https://earthengine.google.com/) (GEE), which is a cloud computing platform with a multi-petabyte catalog of satellite imagery and geospatial datasets.


## Using the algorithm

### 1. Sign up for a GEE account and install geemap

* **Sign up.** you must first [sign up](https://earthengine.google.com/signup/) for a [Google Earth Engine](https://earthengine.google.com/) (GEE) account.
[![](https://i.imgur.com/ng0FzUT.png)](https://earthengine.google.com)

* **Install geemap.** geemap is also available on conda-forge. If you have Anaconda or Miniconda installed on your computer, you can create a conda Python environment to install geemap.
```
  conda create -n gee python=3.8
  conda activate gee
  conda install geopandas
  conda install mamba -c conda-forge
  mamba install geemap localtileserver -c conda-forge
```

* **Update geemap.** If you use conda, you can update geemap to the latest version by running the following command in your terminal.
```
  conda update -c conda-forge geemap
```

* **Optionally.** you can install [Jupyter notebook extensions](https://github.com/ipython-contrib/jupyter_contrib_nbextensions), which can improve your productivity in the notebook environment. Some useful extensions include Table of Contents, Gist-it, Autopep8, Variable Inspector, etc. See this [post](https://towardsdatascience.com/jupyter-notebook-extensions-517fa69d2231) for more information.       
```
  conda install jupyter_contrib_nbextensions -c conda-forge
```

### 2. Producing the corresponding waterbody products required

#### 2.1 Preparation. Please refer to [00--preparation.ipynb](/code/00--preparation.ipynb)
```
  run 00--preparation.ipynb
```
#### 2.2 Automatic training sample construction. Please refer to [01--Automatic training sample construction.ipynb](/code/01--Automatic&#32;training&#32;sample&#32;construction.ipynb)
```
  run 01--Automatic training sample construction.ipynb
```
#### 2.3 Waterbody products.
* **Water occurrence (with temporal correction).** Please refer to [02.01--Water detection and Temporal correction and Calculation of water occurrence.ipynb](/code/02.01--Water&#32;detection&#32;and&#32;Temporal&#32;correction&#32;and&#32;Calculation&#32;of&#32;water&#32;occurrence.ipynb)
```
  run 02.01--Water detection and Temporal correction and Calculation of water occurrence.ipynb
```
* **Water occurrence (w/o temporal correction).** Please refer to [02.02--Water detection and Calculation of water occurrence.ipynb](/code/02.02--Water&#32;detection&#32;and&#32;Calculation&#32;of&#32;water&#32;occurrence.ipynb)
```
  run 02.02--Water detection and Calculation of water occurrence.ipynb
```
* **Water detection.** Please refer to [02.03--Water detection and Temporal correction.ipynb](/code/02.03--Water&#32;detection&#32;and&#32;Temporal&#32;correction.ipynb)
```
  run 02.03--Water detection and Temporal correction.ipynb
```
### 3. Download.
By default, all processing results are saved to GEE's Assets. If required, they can also be downloaded to a local disk or Google Drive.Please refer to [03--Download data to Google Driver or Local Dish.ipynb](/code/03--Download&#32;data&#32;to&#32;Google&#32;Driver&#32;or&#32;Local&#32;Dish.ipynb)
```
  run 03--Download data to Google Driver or Local Dish.ipynb
```

## Appendix
* **geemap tutorials.** A Python package for interactive mapping with Google Earth Engine, ipyleaflet, and ipywidgets.  
  GitHub repo: https://github.com/giswqs/geemap  
  Documentation: https://geemap.org  
  PyPI: https://pypi.org/project/geemap/  
  Conda-forge: https://anaconda.org/conda-forge/geemap  
  360+ GEE notebook examples: https://github.com/giswqs/earthengine-py-notebooks  
  GEE Tutorials on YouTube: https://www.youtube.com/c/QiushengWu  

 ## Contact
If you have any questions about it, please feel free to let me know. (:email: rnlibaoguang@cug.edu.cn)
