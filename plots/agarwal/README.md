Agarwal Dataset – Figure Explanation (Chunk Sizes: 300, 500, 800, 1000)

All figures evaluate TFIDD on the Agarwal dataset under structured, piecewise concept drift across four temporal resolutions: (a) 300, (b) 500, (c) 800, and (d) 1000. Compared to RBF and Hyperplane, Agarwal exhibits more abrupt regime transitions, where class boundaries shift sharply rather than gradually.

1. Prequential Accuracy

The prequential accuracy curves show clear phase transitions corresponding to concept switches. At chunk size 300, accuracy fluctuations are frequent and more jagged due to high temporal sensitivity. As chunk size increases to 500, 800, and 1000, the transitions remain visible but become smoother, indicating variance reduction without masking regime shifts.

Unlike gradual streams, Agarwal shows distinct plateau–drop–recovery patterns. TFIDD maintains stable recovery after each transition without prolonged collapse. Highly reactive detectors produce unstable oscillations around switch points, while conservative detectors exhibit delayed recovery during regime change.

2.KS / MI Distribution Shift

The KS and MI curves demonstrate structured shift regions rather than random spikes. At chunk size 300, the drift strength values are higher and noisier due to small-window estimation. As chunk size increases, both KS and MI values stabilize while preserving visible regime changes. The decreasing amplitude across chunk sizes reflects statistical smoothing rather than disappearance of drift.

Importantly, MI remains consistently elevated relative to KS, suggesting multi-dimensional distribution restructuring rather than single-feature marginal change.

3. Cross-Chunk Alarm Analysis

Alarm frequency decreases steadily as chunk size increases. At chunk size 300, TFIDD produces higher alarm counts due to sharper sensitivity to regime switches. At 1000, alarms reduce substantially while still aligning with structural changes.

In contrast, classical detectors show unstable patterns. Some methods maintain low alarms but exhibit poor recovery, while others trigger frequently without proportional performance gains. TFIDD demonstrates monotonic alarm reduction with increasing chunk size, indicating controlled sensitivity rather than alarm inflation.

4. Drift Score Dynamics

The drift score plots show strong peaks during regime transitions, particularly at chunk sizes 300 and 500. Between transitions, the score gradually stabilizes. The adaptive threshold adjusts upward following sustained structural divergence, preventing repeated triggers during stable phases.

At larger chunk sizes, drift peaks remain distinct but are less volatile, reflecting improved statistical confidence in regime change detection.

Top Drift-Driving Features

The top feature importance plots reveal that different feature subsets dominate across chunk sizes. Unlike linear drift, Agarwal’s piecewise structure shifts importance rankings at each regime switch. The ordering of top features changes between chunk sizes, but dominant features remain consistently influential across resolutions.

This indicates that drift is not isolated to a single dimension but involves coordinated structural reconfiguration of the feature space.

5. Feature Importance Trajectories

Feature trajectories show clear regime-dependent importance blocks. Certain features dominate during early segments and lose influence after transitions. Smaller chunk sizes show sharper importance volatility, while larger chunk sizes smooth transitions without obscuring structural shifts.

These trajectories confirm that TFIDD captures interpretable feature-level drift aligned with known regime boundaries.

6. Stability vs Recovery Trade-off

The stability–recovery plots show that highly sensitive detectors achieve slightly faster reaction but incur higher false alarm rates. Conservative detectors maintain lower false alarms but suffer reduced recovery gain. Across all chunk sizes, TFIDD remains in a balanced region, maintaining low-to-moderate false alarms with stable recovery performance.

Notably, as chunk size increases, TFIDD shifts closer to the stability-optimal region without losing recovery capacity, indicating scalability across temporal resolutions.

7. Overall Interpretation

The Agarwal stream represents structured, piecewise concept drift with clear regime transitions. Increasing chunk size reduces variance while preserving regime boundaries. Across chunk sizes 300 to 1000, TFIDD maintains stable adaptation, interpretable feature-level dynamics, and controlled alarm behavior without excessive sensitivity or delayed response.
