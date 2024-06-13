# PCA Leads

### Principal component analysis of Arctic Sea ice using multi-spectral Sentinel-2 and RADAR Sentinel-1 data
#### Jullian C.B. Williams *†, Kiran Bhaganagar ††

##### † Department of Earth and Planetary Sciences, Center for Advanced Measurements in Extreme Environments (CAMEE), The University of Texas at San Antonio, 1 UTSA Circle, San Antonio, Texas 78249
##### †† Department of Mechanical Engineering, The University of Texas at San Antonio, 1 UTSA Circle, San Antonio, Texas 78249

###### corresponding author: jullian.williams@my.utsa.edu

# Summary
The increasing concern regarding climate change continues to motivate research in the Arctic. Within the delicate cycle of the cryosphere, leads are an important kinematic feature that regulate heat balances in the Arctic. Therefore, it is necessary to quantify the genesis of leads over time to identify when and where changes are occurring. The use of a principal component analysis (PCA) is one such tool that is used to identify the characteristics of seasonal ice variability. The PCA not only identifies “normal” or “dominant” conditions or features, but also extract anomalous spatial features from an archive of long-term sequence of images.
# Introduction
Leads are described as linear kinematic features found on sea ice surfaces. The formation of leads is akin to the process of plate tectonics, where shifting ice sheets diverge, converge and slide against each other, forming fissures in the ice. Leads are important to arctic habitats and wildlife (Stirling, 1997), polar navigation  (Lasserre, 2015) and global climate (Hutter, 2018). Leads are important regulators of heat in the Arctic, with open water and thin ice leads providing the first and second largest heat fluxes into the atmosphere (approximately 600 W.m-2 and 5 W.m-2 respectively, (Maykut 1982 and Li, 2019)).
Radar satellite imagery is used to observe and quantify the changes in lead fractions across the ice sheet. Radar data is particularly useful in quantifying lead fractions since the instrument can make observations in Polar regions regardless of weather conditions or time of year (Lindsay & Rothrock, 1995), (Rohrs & Kaleschke, 2012), (Brohan & Kalesche, 2014), (Willmes & Heinemann, 2015). The Sentinel-1 A/B instrument is a powerful, high resolution radar satellite imager that has been used for Polar observations since its launch in 2014 and 2016 (A and B respectively). The two-satellite constellation provides a 6-day exact repeat cycle, 12-day cross-over and a repeat frequency of less than 1 day in the Arctic (Lohse, 2020). Sentinel-1 has unprecedented nominal spatial resolution of ~40 m, which allows small scale leads on the ice surface to be captured.    
Google Earth Engine (GEE) hosts a large repository of satellite data, including the entire Sentinel catalog. GEE has been used in several research arenas, from vegetation and land use mapping (Gorelick et al., 2017 and Tsai, et al., 2018) to wetland and snow melt detection (Gulacsi, et al., 2020 and Liang et., al, 2021). Indeed, GEE and Sentinel-2 are proven powerhouses in the use of remote sensing techniques and climate observations in cloud computation environments. Currently, there are no studies published focusing on the detection of leads in the Arctic using this platform which provide a solution to the common big data problem of data storage and computation power.
This study provides a principal component technique to sea ice classification in the GEE cloud computation environment using Sentinel-2 optical data. The Beaufort Gyre (Figure 1), once described as an ice production area has shown a decrease in productivity with increased climate forcing over the last decade (Armitage, 2020). This motivates our investigation of sea ice lead prevalence during the lifetime of the Sentinel 1 & 2 instruments. The aim of this study is to classify sea ice open water and thin ice leads in the offshore Alaskan region in the Beaufort Gyre to assess the changes potential heat flux over the ice sheet.

# Datasets
1.	Sentinel-2 multi-spectral optical data: https://developers.google.com/earth-engine/datasets/catalog/sentinel-2
2. Sentinel-1 RADAR data: https://developers.google.com/earth-engine/datasets/catalog/COPERNICUS_S1_GRD

# Methods
##### Google Colab Python environment
Alongside the use of GEE for data retrieval, preparation and classification, we opt to use Google Colab, a cloud computation python environment. Indeed, Google Colab (GC) is an exceptional tool for the use of superior python functions in the cloud, minimizing the pressure of data storage while simultaneously enhancing processing power through parallelization. GC allows the user to mount their Google Drive storage point to the environment, allowing easy data imports and exports of results.

##### Python Modules
* from datetime import datetime
* import pandas as pd
* import geopandas as gpd
* import numpy as np
* import matplotlib.pyplot as plt
* from matplotlib import cm
* import matplotlib.cbook
* from mpl_toolkits.basemap import Basemapimport random
* from mpl_toolkits.axes_grid1 import make_axes_locatable
* from scipy import stats
* import matplotlib.image as mpimg
* from sklearn.metrics import r2_score
* from sklearn.decomposition import PCA
* import warnings

##### Principal Component Analysis
The PCA method is such that the first component will always contain the most variation found in the original data. This is referred to as the “integrated brightness” and provides a good index of the general image characteristics. In the case of sea ice data, the image scenes may be water or ice dominant. The second component then highlights the major differences between the image channels. In fact, it is suggested that studies using multitemporal monthly data over an annual cycle display a second component that tracks the seasonal evolution well (Piwowar, et al., 1996). Principal components three and onward usually represent increasingly local variation and anomalies. Therefore, we propose that it is within these variations that the open water and thin ice leads may be characterized.

###### Plotting Techniques
The results of the principal component analysis yield mean and anomalous digital signals from the false RGB color composite images. From this, we can visualize these parameters graphically in Arctic map plots as well as quantitatively in scatter plots to display the orthogonal components. The mean and standard deviations will give a margin of error of the spectral boundaries of the lead types versus the ice ridges in the image scenes which can be both spectrally and geometrically similar.  

# References
1. Armitage, T., Manucharyan, G., Petty, A., Kwok, R., and Thompson, A. (2020). Enhanced eddy activity in the Beaufort Gyre in response to sea ice loss. Nature Communications, 11(1). doi: 10.1038/s41467-020-14449-z.

2. Bröhan, D., Kaleschke, L., & Notz, D. (2014). Analysis of Arctic sea-ice leads from Advanced Microwave Scanning Radiometer.

3. Gorelick, N., Hancher, M., Dixon, M., Ilyushchenko, S., Thau, D., and Moore, R. (2017). Google Earth Engine: Planetary-scale geospatial analysis for everyone. Remote Sensing Of Environment, 202, 18-27. doi: 10.1016/j.rse.2017.06.031.

4. Gulácsi, A., and Kovács, F. (2020). Sentinel-1-Imagery-Based High-Resolution Water Cover Detection on Wetlands, Aided by Google Earth Engine. Remote Sensing, 12(10), 1614. doi: 10.3390/rs12101614.

5. Hutter, N., Zampieri, L., and Losch, M. (2018). Leads and ridges in Arctic sea ice from RGPS data and a new tracking algorithm. The Cryosphere Discussions, 1-27. doi: 10.5194/tc-2018-207.

6. Lasserre, F. (2014). Simulations of shipping along Arctic routes: comparison, analysis and economic perspectives. Polar Record, 51, 239 - 259.

7. Li, X., Krueger, S. K., Strong, C., Mace, G. G., and Benson, S. (2020). Midwinter Arctic leads form and dissipate low clouds. Nature Communications, 11(1), 1-8.

8. Liang, D., Guo, H., Zhang, L., Cheng, Y., Zhu, Q., and Liu, X. (2021). Time-series snowmelt detection over the Antarctic using Sentinel-1 SAR images on Google Earth Engine. Remote Sensing Of Environment, 256, 112318. doi: 10.1016/j.rse.2021.112318.

9. Lindsay, R., and Rothrock, D. (1995). Arctic sea ice leads from advanced very high resolution radiometer images. Journal of Geophysical Research, 100(C3), 4533. doi: 10.1029/94jc02393.

10. Maykut, G.A. (1982). Large‐scale heat exchange and ice production in the central Arctic. Journal of Geophysical Research, 87, 7971-7984.

11. Piwowar, J., and LeDrew, E. (1996). Principal Components Analysis of Arctic Ice Conditions between 1978 and 1987 as Observed from the SMMR Data Record. Canadian Journal Of Remote Sensing, 22(4), 390-403. doi: 10.1080/07038992.1996.10874663.

12. Röhrs, J., and Kaleschke, L. (2012). An algorithm to detect sea ice leads by using AMSR-E passive microwave imagery. The Cryosphere, 6(2), 343-352. doi: 10.5194/tc-6-343-2012.

13. Stirling, I. (1997). The importance of polynyas, ice edges, and leads to marine mammals and birds. Journal Of Marine Systems, 10(1-4), 9-21. doi: 10.1016/s0924-7963(96)00054-1.

14. Tsai, Y., Stow, D., Chen, H., Lewison, R., An, L., and Shi, L. (2018). Mapping Vegetation and Land Use Types in Fanjingshan National Nature Reserve Using Google Earth Engine. Remote Sensing, 10(6), 927. doi: 10.3390/rs10060927.

15. Wakulinska, M., & Marcinkowska-Ochtyra, A. (2020). Multi-Temporal Sentinel-2 Data in Classification of Mountain Vegetation. Remote. Sens., 12, 2696.

16. Williams, J. C.; Ackley, S. F.; Mestas-Nuñez, A. M.; Macdonald, G. J. Lead Detection with Sentinel-1 in the Beaufort Gyre using Google Earth Engine. Preprints 2024, 2024050284. https://doi.org/10.20944/preprints202405.0284.v1

17. Willmes, S. and Heinemann, G. (2015). Sea-Ice Wintertime Lead Frequencies and Regional Characteristics in the Arctic, 2003–2015. Remote Sensing, 8(1), 4. doi: 10.3390/rs8010004.
