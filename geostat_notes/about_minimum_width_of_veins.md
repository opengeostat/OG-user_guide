# Geostat note. About using minimum width for vein modelling.

Minimum width is a modelling parameter or constraint that is usually applied at the time of modelling narrow veins. The most common reason for using a minimum width is to ensure the average grade interpolated is similar to the grade of mining stopes. However, the same results are obtained by adding dilution and mineables shapes optimized (MSO). 

Let's review an example. Fig. 1. a) shows an interpolation in a narrow vein of constant thickness (1m) and applying dilution, assuming the stopes will be 5m width and 20m high. Fig. 1. b) shows the same narrow vein interpolated after applying a minimum width.
The average grade of vein and waste over 20 m is approximately 9.2 g/t in both cases. The vein modelled with minimum width this is `(8m*0g/t + 1m*2g/t + 1m*90g/t)/10m = 9.2g/t`. The 1m vein itself (Fig. 1. a)) is `(2 g/t + 90 g/t)/2= 46 g/t`, but there are 4m of waste at zero grade added as dilution, so the average grade is `(1m*46g/t + 4m*0g/t)/5m = 9.2g/t`.

| ![Figure 1](fig1.svg) |
|:--:|
| <i> Fig. 1 -  a) Narrow vein with dilution skin applied, and b) narrow vein modelled with minimum width. Drillhole and sample composites are shown as dashed black lines. </i>|

In most cases, interpolating the narrow vein without minimum width is preferred, especially if the vein contacts are well defined by visual inspection, grade, or other criteria. And this is why:
 1) The vein and the waste have different geostatistical distributions. Each one has higher grade continuity than both of them combined. Waste and vein distributions also have different means, variances, and spatial continuity, so the two combined may not be stationary and can be nonlinear. Combining the two statistical populations will produce variograms with very poor continuity. It will also make the mineralization appear higher nuggety and increase the coefficient of variation. Interpolations with linear techniques such as ordinary kriging and the inverse of the power of the distance will be sensitive to minor changes in interpolation parameters. They will also suffer from severe oversmoothing (underestimating high grades and overestimating low grades). 
 2) If the number of waste samples is large (like in fig 1), then the proportion of samples mineralized is low (low probability of higher grade samples). Therefore, many decisions based on sample distribution (histogram and CDF) will likely be wrong. For example, the 90 g/t composite will be considered an outlier and harshly capped. Likewise, techniques based on CDF, such as normal score transformation, normal score or lognormal variogram, global change of support, and conditional simulations, will be unreliable. 
 3) Modelling with minimum width will limit the ability of mining engineers to test different mining scenarios, for example, narrower stopes, preferential dilution to a specific side of the vein, or the implementation of more selective mining techniques. 

In general, it is always better to avoid mixing statistical populations by incorporating too many extremely low-grade samples in mineralized domains. In addition, it is advised not to incorporate mining constraints when modelling estimation domains. 
