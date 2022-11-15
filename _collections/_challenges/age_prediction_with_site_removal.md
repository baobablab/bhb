---
layout: page
title: Age prediction with site-effect removal
cat: regression
subcat: age
headline: 
teasing: A challenge on the openBHB dataset that aims to i) predict age from derived 3D T1w anatomical MRI data while ii) removing site/scanner information from the learned representation.
challenge_url: https://ramp.studio/problems/brain_age_with_site_removal
icon: age_prediction_with_site_removal.jpg
image: age_prediction_with_site_removal.jpg
added: 2021
---

### Link to the challenge

The challenge is available on [RAMP.studio](https://ramp.studio/problems/brain_age_with_site_removal).
The code of the challenge is available on GitHub [RAMP.kits](https://github.com/ramp-kits/brain_age_with_site_removal).

### Contents

1. [Challenge description](#challenge-description)
2. [Ranking of the best models](#ranking-of-the-best-models)
3. [Metrics](#metrics)
4. [Baselines](#baselines)


### Challenge description

The challenge uses the openBHB dataset and aims to i) predict age from derived
data from 3D T1 anatomical MRI while ii) removing site information from the
learned representation. Thus, we aim to compare the capacity of proposed
models to encode a relevant representation of the data (feature extraction
and dimensionality reduction) that preserve the biological variability
associated with age while removing the site-specific information. The
algorithms submitted must output a low-dimension features vector (p < 10000).
Derived data are composed of Quasi-Raw, VBM, and SBM.


### Ranking of the best models

A public leaderboard with up-to-date results is available
[here](https://ramp.studio/events/brain_age_with_site_removal_open_2022/leaderboard)

**Warning:** This public leaderboard contains the **metrics computed on the public validation set**.
It may be biased by models trained on all public data. To access to this
leaderboard, you must be registered to the challenge.

Last update: 28/07/2022

<div style="overflow-x:scroll" markdown="1">

|   rank | submission          |   submission ID | team                | private challenge_metric   | private mae_age    | private rmse_age    | private bacc_site   | private ext_mae_age   |   train time [s] |   validation time [s] |   test time [s] |
|-------:|:--------------------|----------------:|:--------------------|:---------------------------|:-------------------|:--------------------|:--------------------|:----------------------|-----------------:|----------------------:|----------------:|
|    1   | expw-1ekelhvz       |           13638 | carloalbertobarbano | 1.468 &#177; 0.012         | 2.612 &#177; 0.002 | 3.800 &#177; 0.003  | 0.052 &#177; 0.001  | 3.564 &#177; 0.004    |          2748.43 |               2397.19 |         1318.61 |
|    2   | expw-j1vaqg5y       |           13637 | carloalbertobarbano | 1.494 &#177; 0.008         | 2.666 &#177; 0.001 | 3.882 &#177; 0.002  | 0.053 &#177; 0.001  | 3.596 &#177; 0.003    |          2677.27 |               2313.17 |         1275.97 |
|    3   | expw-5a12ey9d       |           13653 | carloalbertobarbano | 1.526 &#177; 0.016         | 2.871 &#177; 0.011 | 4.224 &#177; 0.021  | 0.055 &#177; 0.002  | 3.649 &#177; 0.017    |          2674.24 |               2210.06 |         1184.2  |
|    4   | expw-w0ci971l       |           13625 | carloalbertobarbano | 1.540 &#177; 0.008         | 2.552 &#177; 0.002 | 3.542 &#177; 0.002  | 0.051 &#177; 0.001  | 3.761 &#177; 0.005    |          2776.37 |               2338.03 |         1258.04 |
|    5   | expw-c3xwloe5       |           13636 | carloalbertobarbano | 1.555 &#177; 0.028         | 2.636 &#177; 0.001 | 3.725 &#177; 0.000  | 0.054 &#177; 0.003  | 3.741 &#177; 0.003    |          2919.56 |               2431.2  |         1357.48 |
|    6   | mae-1uidjvci        |           13658 | carloalbertobarbano | 1.572 &#177; 0.006         | 2.785 &#177; 0.000 | 4.019 &#177; 0.001  | 0.070 &#177; 0.001  | 3.489 &#177; 0.004    |          3961.94 |               2146.59 |         1158.23 |
|    7   | expw-nl49poa9       |           13629 | carloalbertobarbano | 1.576 &#177; 0.036         | 2.823 &#177; 0.003 | 4.191 &#177; 0.007  | 0.050 &#177; 0.004  | 3.878 &#177; 0.004    |          2603.52 |               2225.57 |         1205.97 |
|    8   | yaware-139qvvlx     |           13617 | carloalbertobarbano | 1.655 &#177; 0.006         | 2.623 &#177; 0.001 | 3.820 &#177; 0.003  | 0.059 &#177; 0.001  | 3.858 &#177; 0.010    |          3091.74 |               2432.63 |         1409.68 |
|    9   | mae-1opsr9qb-fix2   |           13612 | carloalbertobarbano | 1.682 &#177; 0.015         | 2.804 &#177; 0.001 | 4.044 &#177; 0.001  | 0.072 &#177; 0.002  | 3.707 &#177; 0.001    |          4209.02 |               2375.71 |         1303.72 |
|   10   | mae-p9fx600h        |           13644 | carloalbertobarbano | 1.698 &#177; 0.031         | 2.781 &#177; 0.000 | 3.973 &#177; 0.001  | 0.070 &#177; 0.004  | 3.768 &#177; 0.006    |          4118.95 |               2392.27 |         1338.34 |
|   11   | mae-9y1093sp        |           13650 | carloalbertobarbano | 1.709 &#177; 0.007         | 2.770 &#177; 0.007 | 4.271 &#177; 0.015  | 0.058 &#177; 0.001  | 4.014 &#177; 0.013    |          2886.2  |               2461.9  |         1322.57 |
|   12   | threshold-ykx8p7pc  |           13623 | carloalbertobarbano | 1.738 &#177; 0.016         | 2.947 &#177; 0.004 | 4.746 &#177; 0.021  | 0.057 &#177; 0.002  | 4.098 &#177; 0.010    |          2710.43 |               2288.69 |         1281.82 |
|   13   | mae-2dwf0avv        |           13646 | carloalbertobarbano | 1.746 &#177; 0.019         | 2.781 &#177; 0.001 | 3.986 &#177; 0.001  | 0.083 &#177; 0.003  | 3.679 &#177; 0.003    |          3940.23 |               2246.44 |         1226.05 |
|   14   | expw-vpgbhh18       |           13666 | carloalbertobarbano | 1.760 &#177; 0.005         | 2.795 &#177; 0.003 | 4.064 &#177; 0.002  | 0.054 &#177; 0.001  | 4.232 &#177; 0.003    |          2907.06 |               2718.17 |         1329.55 |
|   15   | expw-mm4qykh7       |           13665 | carloalbertobarbano | 1.766 &#177; 0.014         | 2.818 &#177; 0.002 | 4.156 &#177; 0.002  | 0.052 &#177; 0.001  | 4.271 &#177; 0.004    |          2962.12 |               2699.67 |         1368.86 |
|   16   | yaware-ooz7z2yo     |           13613 | carloalbertobarbano | 1.815 &#177; 0.018         | 2.665 &#177; 0.002 | 4.042 &#177; 0.010  | 0.066 &#177; 0.002  | 4.102 &#177; 0.010    |          2891.05 |               2385.28 |         1319.73 |
|   17   | expw-anck0dqb       |           13631 | carloalbertobarbano | 1.816 &#177; 0.027         | 2.731 &#177; 0.006 | 4.116 &#177; 0.014  | 0.049 &#177; 0.002  | 4.503 &#177; 0.010    |          2712.75 |               2323.73 |         1233.33 |
|   18.5 | mae-2r9qbai5        |           13645 | carloalbertobarbano | 1.839 &#177; 0.055         | 2.756 &#177; 0.001 | 3.946 &#177; 0.001  | 0.093 &#177; 0.009  | 3.749 &#177; 0.002    |          3913.36 |               2245.77 |         1228.19 |
|   18.5 | threshold-thmmtpts  |           13641 | carloalbertobarbano | 1.839 &#177; 0.014         | 2.826 &#177; 0.005 | 4.211 &#177; 0.016  | 0.069 &#177; 0.001  | 4.112 &#177; 0.003    |          2594.82 |               2301.58 |         1189.43 |
|   20   | expw-mis1lp61       |           13652 | carloalbertobarbano | 1.840 &#177; 0.025         | 2.767 &#177; 0.004 | 4.049 &#177; 0.003  | 0.054 &#177; 0.003  | 4.432 &#177; 0.024    |          2551.61 |               2151.98 |         1168.22 |
|   21   | expw-phjd8eel       |           13663 | carloalbertobarbano | 1.843 &#177; 0.005         | 2.854 &#177; 0.002 | 4.184 &#177; 0.002  | 0.054 &#177; 0.001  | 4.427 &#177; 0.004    |          2915.84 |               2621.31 |         1340.19 |
|   22   | expw-i3qmz1yh       |           13627 | carloalbertobarbano | 1.849 &#177; 0.021         | 2.666 &#177; 0.003 | 3.964 &#177; 0.005  | 0.050 &#177; 0.001  | 4.547 &#177; 0.019    |          2593.6  |               2170.38 |         1200.25 |
|   23   | expw-1bc3qxx7       |           13670 | carloalbertobarbano | 1.855 &#177; 0.012         | 2.797 &#177; 0.002 | 4.155 &#177; 0.002  | 0.054 &#177; 0.001  | 4.446 &#177; 0.003    |          3201.86 |               2914.34 |         1484.51 |
|   24   | expw-xcq8t2h5       |           13655 | carloalbertobarbano | 1.884 &#177; 0.025         | 2.811 &#177; 0.010 | 4.107 &#177; 0.021  | 0.058 &#177; 0.003  | 4.413 &#177; 0.013    |          2564.58 |               2195.72 |         1172.57 |
|   25   | yaware-09cby77i     |           13633 | carloalbertobarbano | 1.927 &#177; 0.015         | 2.600 &#177; 0.003 | 3.721 &#177; 0.005  | 0.068 &#177; 0.002  | 4.316 &#177; 0.011    |          3053.52 |               2517.91 |         1382.38 |
|   26   | mae-p9qumcga        |           13647 | carloalbertobarbano | 1.948 &#177; 0.008         | 2.963 &#177; 0.001 | 4.326 &#177; 0.000  | 0.093 &#177; 0.001  | 3.974 &#177; 0.001    |          3282.3  |               2546.85 |         1415.62 |
|   27   | rn18-e0a1l01-Kg1-k  |           13348 | carloalbertobarbano | 1.991 &#177; 0.011         | 3.308 &#177; 0.005 | 4.605 &#177; 0.009  | 0.055 &#177; 0.001  | 4.754 &#177; 0.007    |          2793.91 |               2320.87 |         1254.39 |
|   28   | doublexpl-i4pqgq1m  |           13590 | carloalbertobarbano | 2.018 &#177; 0.007         | 3.924 &#177; 0.006 | 5.698 &#177; 0.007  | 0.047 &#177; 0.000  | 5.058 &#177; 0.014    |          2768.55 |               2333.21 |         1246.15 |
|   29   | supcon-2xrhn98q     |           13605 | carloalbertobarbano | 2.019 &#177; 0.019         | 4.027 &#177; 0.006 | 5.946 &#177; 0.007  | 0.045 &#177; 0.001  | 5.108 &#177; 0.012    |          2819.89 |               2355.78 |         1277.94 |
|   30   | mae-gmhxx2va        |           13651 | carloalbertobarbano | 2.023 &#177; 0.039         | 2.959 &#177; 0.001 | 4.292 &#177; 0.001  | 0.119 &#177; 0.008  | 3.830 &#177; 0.003    |          2936.26 |               2284.82 |         1241.01 |
|   31   | supconk-1ih0zwe1    |           13593 | carloalbertobarbano | 2.037 &#177; 0.005         | 4.023 &#177; 0.005 | 5.806 &#177; 0.009  | 0.046 &#177; 0.000  | 5.132 &#177; 0.011    |          2782    |               2415.6  |         1267.05 |
|   32   | mae-deiqt9ah        |           13649 | carloalbertobarbano | 2.042 &#177; 0.029         | 2.962 &#177; 0.001 | 4.329 &#177; 0.001  | 0.113 &#177; 0.006  | 3.932 &#177; 0.006    |          3098.32 |               2504.86 |         1321.83 |
|   33   | yaware-pa1l1xkl     |           13634 | carloalbertobarbano | 2.056 &#177; 0.055         | 2.763 &#177; 0.017 | 4.155 &#177; 0.029  | 0.059 &#177; 0.005  | 4.805 &#177; 0.031    |          2698.1  |               2265.89 |         1230.61 |
|   34   | yaware-kdxj1r48     |           13632 | carloalbertobarbano | 2.056 &#177; 0.105         | 2.791 &#177; 0.002 | 4.303 &#177; 0.006  | 0.062 &#177; 0.011  | 4.753 &#177; 0.016    |          2733.69 |               2341.34 |         1250.68 |
|   35   | mae-3cqg08ye        |           13648 | carloalbertobarbano | 2.086 &#177; 0.011         | 2.960 &#177; 0.001 | 4.262 &#177; 0.001  | 0.118 &#177; 0.002  | 3.955 &#177; 0.004    |          3014.19 |               2436.65 |         1249.48 |
|   36   | doublexpl-r5g9x95x  |           13606 | carloalbertobarbano | 2.104 &#177; 0.003         | 4.125 &#177; 0.005 | 6.077 &#177; 0.009  | 0.046 &#177; 0.000  | 5.300 &#177; 0.008    |          2737.57 |               2374.56 |         1249.28 |
|   37   | weak-e0wx6o5d       |           13603 | carloalbertobarbano | 2.105 &#177; 0.009         | 8.737 &#177; 0.025 | 12.251 &#177; 0.001 | 0.016 &#177; 0.000  | 7.330 &#177; 0.030    |          2730.32 |               2294.02 |         1244.97 |
|   38   | rn18-gauss-200      |           13571 | carloalbertobarbano | 2.114 &#177; 0.015         | 3.630 &#177; 0.002 | 5.083 &#177; 0.002  | 0.052 &#177; 0.001  | 5.135 &#177; 0.009    |          2866.84 |               2408.83 |         1281.28 |
|   39   | weak-177sqidd       |           13592 | carloalbertobarbano | 2.121 &#177; 0.010         | 7.763 &#177; 0.033 | 13.249 &#177; 0.006 | 0.048 &#177; 0.000  | 5.273 &#177; 0.024    |          2574.82 |               2216.72 |         1167.95 |
|   40   | yaware-w85oskw1     |           13616 | carloalbertobarbano | 2.147 &#177; 0.054         | 2.711 &#177; 0.006 | 3.933 &#177; 0.008  | 0.077 &#177; 0.007  | 4.634 &#177; 0.028    |          2827.55 |               2404.89 |         1301.22 |
|   41   | double-1cwmwcqt     |           13602 | carloalbertobarbano | 2.148 &#177; 0.003         | 4.135 &#177; 0.003 | 6.104 &#177; 0.008  | 0.055 &#177; 0.000  | 5.120 &#177; 0.007    |          2679.13 |               2299.42 |         1225.77 |
|   42   | weak-3ce0hzqn       |           13583 | carloalbertobarbano | 2.162 &#177; 0.022         | 4.052 &#177; 0.009 | 6.426 &#177; 0.007  | 0.056 &#177; 0.002  | 5.129 &#177; 0.005    |          3047.56 |               2532.99 |         1363.03 |
|   43   | rn18-A-a1l01-k3     |           13449 | carloalbertobarbano | 2.165 &#177; 0.010         | 2.758 &#177; 0.008 | 4.012 &#177; 0.018  | 0.067 &#177; 0.003  | 4.881 &#177; 0.060    |          2915.66 |               2402.85 |         1366.14 |
|   44.5 | weak-2jdamum8       |           13584 | carloalbertobarbano | 2.186 &#177; 0.009         | 4.813 &#177; 0.004 | 8.160 &#177; 0.011  | 0.059 &#177; 0.000  | 5.116 &#177; 0.021    |          2870.53 |               2465.42 |         1316.84 |
|   44.5 | weak-l01-2jdamum8   |           13587 | carloalbertobarbano | 2.186 &#177; 0.009         | 4.813 &#177; 0.004 | 8.160 &#177; 0.011  | 0.059 &#177; 0.000  | 5.116 &#177; 0.021    |          2718.92 |               2381.24 |         1244.09 |
|   46   | doublexpl-1txrgg1v  |           13594 | carloalbertobarbano | 2.211 &#177; 0.018         | 2.935 &#177; 0.003 | 4.185 &#177; 0.007  | 0.052 &#177; 0.002  | 5.376 &#177; 0.007    |          2601.39 |               2295.07 |         1224.93 |
|   47   | threshold-09zixrf9  |           13642 | carloalbertobarbano | 2.224 &#177; 0.045         | 2.653 &#177; 0.003 | 4.189 &#177; 0.020  | 0.136 &#177; 0.009  | 4.047 &#177; 0.013    |          2625.3  |               2299.79 |         1221.49 |
|   48   | rn18-A-a1l01-k3-fts |           13462 | carloalbertobarbano | 2.229 &#177; 0.023         | 2.805 &#177; 0.017 | 4.080 &#177; 0.024  | 0.073 &#177; 0.001  | 4.884 &#177; 0.027    |          4286.79 |               2516.22 |         1318.45 |
|   49   | mae-7fgmfda6        |           13659 | carloalbertobarbano | 2.242 &#177; 0.040         | 2.760 &#177; 0.002 | 4.088 &#177; 0.002  | 0.084 &#177; 0.005  | 4.715 &#177; 0.004    |          5868.69 |               2731.36 |         1395.16 |
|   50   | yaware-8s28g9jk     |           13640 | carloalbertobarbano | 2.263 &#177; 0.028         | 2.624 &#177; 0.003 | 3.735 &#177; 0.004  | 0.145 &#177; 0.006  | 4.036 &#177; 0.004    |          2611.16 |               2283.38 |         1181.58 |
|   51   | rn18-e0a1l01-2      |           13345 | carloalbertobarbano | 2.266 &#177; 0.010         | 3.023 &#177; 0.006 | 4.392 &#177; 0.009  | 0.060 &#177; 0.001  | 5.277 &#177; 0.011    |          2818.07 |               2296.11 |         1268.65 |
|   52   | resnet18-3d-supcon  |           13243 | carloalbertobarbano | 2.271 &#177; 0.011         | 2.696 &#177; 0.004 | 4.214 &#177; 0.011  | 0.090 &#177; 0.001  | 4.681 &#177; 0.024    |          2793.93 |               2405.05 |         1281.95 |
|   53   | threshold-bsecf64m  |           13630 | carloalbertobarbano | 2.282 &#177; 0.027         | 2.780 &#177; 0.011 | 4.137 &#177; 0.020  | 0.085 &#177; 0.004  | 4.775 &#177; 0.013    |          2760.19 |               2399.64 |         1279.92 |
|   54   | rn18-A-a1l01-k2     |           13412 | carloalbertobarbano | 2.300 &#177; 0.101         | 2.937 &#177; 0.004 | 4.386 &#177; 0.019  | 0.082 &#177; 0.011  | 4.874 &#177; 0.011    |          2978.58 |               2550.23 |         1403.89 |
|   55   | yaware-sfbkbkby     |           13639 | carloalbertobarbano | 2.308 &#177; 0.054         | 2.609 &#177; 0.003 | 3.803 &#177; 0.009  | 0.136 &#177; 0.011  | 4.202 &#177; 0.010    |          2870.86 |               2488.36 |         1297.21 |
|   56   | rn18-e0a1l01        |           13244 | carloalbertobarbano | 2.314 &#177; 0.037         | 2.767 &#177; 0.001 | 4.007 &#177; 0.003  | 0.086 &#177; 0.004  | 4.838 &#177; 0.016    |          2805.29 |               2382.51 |         1277.46 |
|   57   | doublexpl-1pheq2fy  |           13601 | carloalbertobarbano | 2.327 &#177; 0.024         | 3.036 &#177; 0.013 | 4.370 &#177; 0.019  | 0.058 &#177; 0.001  | 5.461 &#177; 0.045    |          2778.47 |               2384.59 |         1257.67 |
|   58   | rn18-A-a1l01-k      |           13358 | carloalbertobarbano | 2.340 &#177; 0.094         | 2.944 &#177; 0.003 | 4.397 &#177; 0.012  | 0.084 &#177; 0.011  | 4.927 &#177; 0.011    |          3001.05 |               2507.78 |         1374.95 |
|   59   | mae-uciwzyph        |           13660 | carloalbertobarbano | 2.355 &#177; 0.016         | 2.777 &#177; 0.001 | 4.108 &#177; 0.002  | 0.087 &#177; 0.002  | 4.905 &#177; 0.006    |          5898.23 |               2747.13 |         1371.53 |
|   60   | rn18-mae-1k         |           13350 | carloalbertobarbano | 2.370 &#177; 0.040         | 2.724 &#177; 0.006 | 4.009 &#177; 0.010  | 0.120 &#177; 0.008  | 4.476 &#177; 0.008    |          3607.64 |               2315.83 |         1275.05 |
|   61   | threshold-jh0tk38j  |           13643 | carloalbertobarbano | 2.402 &#177; 0.026         | 2.615 &#177; 0.003 | 3.751 &#177; 0.004  | 0.151 &#177; 0.005  | 4.238 &#177; 0.017    |          2737.02 |               2426.62 |         1282.96 |
|   62   | rn18-supcon-quad    |           13352 | carloalbertobarbano | 2.408 &#177; 0.022         | 2.886 &#177; 0.005 | 4.276 &#177; 0.023  | 0.078 &#177; 0.002  | 5.170 &#177; 0.067    |          2643.38 |               2200.58 |         1243.37 |
|   63   | yaware-apyqr2sz     |           13615 | carloalbertobarbano | 2.428 &#177; 0.079         | 2.850 &#177; 0.007 | 4.143 &#177; 0.009  | 0.066 &#177; 0.009  | 5.493 &#177; 0.052    |          3000.68 |               2537.24 |         1369.03 |
|   64   | mae-3lauru5f        |           13607 | carloalbertobarbano | 2.430 &#177; 0.023         | 2.909 &#177; 0.001 | 4.243 &#177; 0.001  | 0.088 &#177; 0.002  | 5.045 &#177; 0.006    |          4329.5  |               2486.59 |         1379.67 |
|   65   | double-1w3hdtuo     |           13604 | carloalbertobarbano | 2.431 &#177; 0.026         | 3.616 &#177; 0.006 | 5.387 &#177; 0.015  | 0.076 &#177; 0.004  | 5.264 &#177; 0.026    |          2852.08 |               2492.02 |         1312.43 |
|   66   | mae-494heetj        |           13656 | carloalbertobarbano | 2.435 &#177; 0.046         | 2.680 &#177; 0.001 | 4.019 &#177; 0.000  | 0.116 &#177; 0.008  | 4.643 &#177; 0.011    |          5918.13 |               2861.19 |         1481.58 |
|   67   | rn18-supcon-A-quad  |           13357 | carloalbertobarbano | 2.476 &#177; 0.049         | 3.065 &#177; 0.009 | 4.515 &#177; 0.012  | 0.128 &#177; 0.006  | 4.587 &#177; 0.024    |          2929.14 |               2545.39 |         1379.73 |
|   68   | yaware-r07q08n4     |           13621 | carloalbertobarbano | 2.482 &#177; 0.059         | 3.088 &#177; 0.019 | 4.313 &#177; 0.022  | 0.082 &#177; 0.007  | 5.267 &#177; 0.005    |          3128.6  |               2549.87 |         1445.79 |
|   69   | 200-gauss-l01-cont  |           13580 | carloalbertobarbano | 2.496 &#177; 0.023         | 3.341 &#177; 0.006 | 4.831 &#177; 0.009  | 0.056 &#177; 0.001  | 5.928 &#177; 0.023    |          2789.33 |               2453.5  |         1311.86 |
|   70   | rn18-supcon-quad1k  |           13353 | carloalbertobarbano | 2.503 &#177; 0.056         | 2.847 &#177; 0.006 | 4.271 &#177; 0.018  | 0.086 &#177; 0.008  | 5.223 &#177; 0.059    |          2869.15 |               2496.85 |         1339.25 |
|   71   | doublexpl-uv9ong8a  |           13589 | carloalbertobarbano | 2.503 &#177; 0.020         | 3.408 &#177; 0.006 | 4.917 &#177; 0.003  | 0.063 &#177; 0.002  | 5.742 &#177; 0.049    |          2703.36 |               2336.95 |         1273.2  |
|   72   | double-l01-yszb74lp |           13588 | carloalbertobarbano | 2.539 &#177; 0.034         | 3.688 &#177; 0.010 | 5.149 &#177; 0.004  | 0.057 &#177; 0.001  | 6.008 &#177; 0.058    |          2668.6  |               2388.52 |         1233.09 |
|   73   | yaware-xeef4u9u     |           13626 | carloalbertobarbano | 2.550 &#177; 0.110         | 3.077 &#177; 0.023 | 4.386 &#177; 0.030  | 0.074 &#177; 0.010  | 5.584 &#177; 0.022    |          2756.87 |               2313.75 |         1219.22 |
|   74   | mae-1jshwutr        |           13661 | carloalbertobarbano | 2.558 &#177; 0.065         | 2.660 &#177; 0.001 | 3.887 &#177; 0.003  | 0.115 &#177; 0.010  | 4.893 &#177; 0.004    |          5939.31 |               2880.19 |         1432.84 |
|   75   | mae-rmlxa5d9        |           13608 | carloalbertobarbano | 2.572 &#177; 0.016         | 4.878 &#177; 0.035 | 6.587 &#177; 0.037  | 0.064 &#177; 0.003  | 5.877 &#177; 0.042    |          4204.6  |               2375.68 |         1320.73 |
|   76   | double-10kb9tcq     |           13597 | carloalbertobarbano | 2.612 &#177; 0.011         | 3.073 &#177; 0.005 | 4.443 &#177; 0.009  | 0.077 &#177; 0.001  | 5.634 &#177; 0.013    |          2861.67 |               2368.16 |         1284.01 |
|   77   | yaware-38bxmee4     |           13624 | carloalbertobarbano | 2.623 &#177; 0.064         | 3.086 &#177; 0.008 | 4.490 &#177; 0.010  | 0.057 &#177; 0.006  | 6.205 &#177; 0.027    |          2848.61 |               2359.34 |         1233.86 |
|   78   | threshold-alp80xna  |           13628 | carloalbertobarbano | 2.627 &#177; 0.109         | 3.043 &#177; 0.012 | 4.401 &#177; 0.021  | 0.085 &#177; 0.010  | 5.508 &#177; 0.020    |          2651.79 |               2244.09 |         1208.42 |
|   79.5 | 200-gauss-l01       |           13579 | carloalbertobarbano | 2.687 &#177; 0.033         | 3.432 &#177; 0.010 | 5.070 &#177; 0.014  | 0.062 &#177; 0.002  | 6.177 &#177; 0.046    |          2767.5  |               2442.7  |         1326.09 |
|   79.5 | supcon-4pviy9vi     |           13600 | carloalbertobarbano | 2.687 &#177; 0.033         | 3.432 &#177; 0.010 | 5.070 &#177; 0.014  | 0.062 &#177; 0.002  | 6.177 &#177; 0.046    |          2775.05 |               2394.5  |         1258.28 |
|   81   | weak-l1-xea18f3u    |           13591 | carloalbertobarbano | 2.769 &#177; 0.054         | 4.272 &#177; 0.006 | 6.607 &#177; 0.005  | 0.060 &#177; 0.004  | 6.452 &#177; 0.011    |          2649.7  |               2301.37 |         1208.89 |
|   82   | double-1cteu4cw     |           13585 | carloalbertobarbano | 2.773 &#177; 0.027         | 3.492 &#177; 0.009 | 4.896 &#177; 0.008  | 0.053 &#177; 0.001  | 6.716 &#177; 0.016    |          2826.59 |               2439.11 |         1294.18 |
|   83   | rn18-e0a1l0-gauss2  |           13346 | carloalbertobarbano | 2.795 &#177; 0.039         | 5.167 &#177; 0.014 | 6.945 &#177; 0.004  | 0.061 &#177; 0.002  | 6.461 &#177; 0.022    |          2726.01 |               2410.12 |         1317.18 |
|   84   | mae-1opsr9qb        |           13609 | carloalbertobarbano | 2.971 &#177; 0.019         | 4.982 &#177; 0.053 | 6.897 &#177; 0.081  | 0.060 &#177; 0.002  | 6.912 &#177; 0.110    |          4171.62 |               2380.57 |         1282.22 |
|   85   | mae-1opsr9qb-fix    |           13610 | carloalbertobarbano | 2.971 &#177; 0.019         | 4.982 &#177; 0.053 | 6.897 &#177; 0.081  | 0.060 &#177; 0.002  | 6.912 &#177; 0.110    |          4119.39 |               2370.89 |         1270.01 |
|   86   | resnet18-3d-mae     |           13242 | carloalbertobarbano | 3.006 &#177; 0.050         | 2.994 &#177; 0.002 | 4.358 &#177; 0.004  | 0.116 &#177; 0.006  | 5.728 &#177; 0.015    |          3822.13 |               2479.38 |         1328.34 |
|   87   | yaware-3jm0a5ld     |           13622 | carloalbertobarbano | 3.025 &#177; 0.130         | 3.477 &#177; 0.021 | 4.894 &#177; 0.027  | 0.093 &#177; 0.011  | 6.183 &#177; 0.038    |          2823.35 |               2333.89 |         1269.52 |
|   88   | weak-2zoic6fk       |           13598 | carloalbertobarbano | 3.096 &#177; 0.070         | 3.162 &#177; 0.009 | 4.494 &#177; 0.021  | 0.068 &#177; 0.003  | 6.936 &#177; 0.146    |          2842.72 |               2380.79 |         1283.19 |
|   89   | double-exp-3pi2r1t0 |           13586 | carloalbertobarbano | 3.297 &#177; 0.023         | 3.620 &#177; 0.017 | 5.025 &#177; 0.020  | 0.066 &#177; 0.000  | 7.448 &#177; 0.066    |          2649.64 |               2245.44 |         1199.61 |
|   90   | starting_kit_01     |           13239 | frcaud              | 3.348 &#177; 0.126         | 2.549 &#177; 0.009 | 3.632 &#177; 0.010  | 0.080 &#177; 0.008  | 7.132 &#177; 0.050    |          6362.83 |               3325.6  |         1631.09 |
|   91   | rn18-supcon-gauss   |           13351 | carloalbertobarbano | 3.463 &#177; 0.036         | 3.484 &#177; 0.019 | 5.218 &#177; 0.026  | 0.066 &#177; 0.000  | 7.823 &#177; 0.074    |          2959.67 |               2419.85 |         1298    |
|   92   | weak-1vuffgfh       |           13595 | carloalbertobarbano | 3.795 &#177; 0.058         | 3.710 &#177; 0.009 | 5.441 &#177; 0.019  | 0.073 &#177; 0.003  | 8.317 &#177; 0.084    |          2752.87 |               2416.48 |         1253.94 |

</div><br/>


### Metrics

Models submitted are evaluated with the standard linear evaluation protocol
(see Figure below) to predict age and site from the data encoded by the
submitted models.


![Evaluation protocol]({{site.url}}{{site.baseurl}}/images/resources/model-evaluation-workflow.jpg){:class="center"}

**Legend:** model evaluation workflow of a new submission. When a new trained
model is submitted to [RAMP](https://ramp.studio/problems/brain_age_with_site_removal),
a linear probe (regressor for age prediction and classifier for site
classification) is trained on top of the public embedded data (i.e. public
data encoded by the submitted model). Once trained, this linear probe predicts
the downstream targets (age and site) on the private embedded data (age is
predicted from both private internal and external tests while site is
predicted from private internal test only). 3 metrics are then derived: Mean
Absolute Error (MAE) for age prediction on internal and external test; Balanced
Accuracy (BAcc) for site prediction on internal test.  These 3 metrics are
combined to derive the final challenge metric Lc.

Three metrics are computed on encoded data (a.k.a model representation):

- **MAE{int}** :arrow_down: Mean Absolute Error (MAE) for age prediction on
  internal test (images acquired from same scanners/sites as training images);
- **MAE{ext}** :arrow_down: MAE for age prediction on external test
  (cross-scanners/sites images);
- **Bacc** :arrow_down Balanced Accuracy for site prediction on internal test.

The overall challenge metrics is computed as follows:


> Lc = **BAcc**(sites)^0.3 . **MAE{ext}**(age) + (1/Nsites)^0.3  **MAE{int}**(age)

As a result, the model representation should be invariant to noise induced
during acquisition (low Bacc) but should retain biological variability
associated to age (low MAE).


### Baselines

**Implementation:** you can find the PyTorch implementation of the previous
models in the GitHub repository:
[https://github.com/Duplums/brain_age_with_site_removal](https://github.com/Duplums/brain_age_with_site_removal).
        
We performed baseline experiments,a nd trained CNNs with various architectures
on whole-brain measures (VBM and Quasi-Raw). The objective function is a
simple l1-loss on age prediction for all models. 
We tested ComBat data-based debiasing models, that correponds to classical
harmonization of the training set (test sets are left unharmonized since
age and site labels are not available). We reported the 3 metrics used in
the challenge: MAE on the openBHB and privateBHB test sets and Bacc for
site prediction. The latent space dimension varied across CNN architectures
and it is always reported.

<div style="overflow-x:scroll" markdown="1">

**De-biasing method** | **Model (latent dims)**  | | | **VBM** | | | **Quasi-Raw** | | |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |  :---: |  :---: |
| | Int. Test MAE | Ext. Test MAE | Site Pred. BAcc | Lc | Int. Test MAE | Ext. Test MAE | Site Pred. BAcc | Lc
❌ | DenseNet(1024) | 2.55 ± 0.009  | 7.13 ± 0.05 | 8.0 ± 0.9 | 3.34 | 2.48 ± 0.03 | 2.92 ± 0.07 | 15.2 ± 0.6 | 1.66
❌ | ResNet(512) | 2.67 ± 0.05 | 4.18 ± 0.01 | 6.7 ± 0.1 | 1.86 | 2.60 ± 0.003 | 2.85 ± 0.004 | 7.6 ± 0.1 | 1.31
❌ | AlexNet(128 | 2.72 ± 0.01 | 4.66 ± 0.05 | 8.3 ± 0.2 | 2.21 | 2.96 ± 0.005 | 3.65 ± 0.009 | 16.2 ± 0.5 | 2.11
ComBat | DenseNet(1024) | 5.92 ± 0.01 | 10.48 ± 0.17 | 2.23 ± 0.06 | 5.08 | ❌ | ❌ | ❌ | ❌
ComBat | ResNet(512) | 4.15 ± 0.009 | 4.76 ± 0.03 | 4.5 ± 0.0 | 1.88  | ❌ | ❌ | ❌ | ❌
ComBat | AlexNet(128 | 3.37 ± 0.01 | 5.23 ± 0.12 | 6.8 ± 0.3 | 2.33 | ❌ | ❌ | ❌ | ❌

</div><br/>


**Legend:** baselines obtained with 1) no de-biasing strategy (first 3 rows) and
2) ComBat residualization on training data (last 3 rows) with VBM and Quasi-Raw
data for 3 representative CNN families.

We can notice that all models retain site information without any debiasing
strategy. Overall, Quasi-Raw data are more biased than VBM, and CNN preserve
this bias to some extent. The ResNet seems to be the best trade-off as it
is robust to site and it generalizes well on the privateBHB test set.
Interesingly, ComBat harmonization does remove most of site bias in CNN
representation space (with site prediction Bacc almost matching the one
obtained using only age as input). However, it also heavily degrades CNN
performance on age prediction for all testing sets (in particular for DenseNet).
ComBat is not fitted for Quasi-Raw data as it mainly relies on voxel-wise
statistics, and raw data are not properly registrated voxel-wise across images.
Consequently, we did not evaluated this approach on Quasi-Raw images.

