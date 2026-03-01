Electricity Dataset – Figure Explanation (Chunk Sizes: 300, 500, 800, 1000)

All figures evaluate TFIDD on the real-world Electricity dataset without ground-truth drift annotations across four temporal resolutions: (a) 300, (b) 500, (c) 800, and (d) 1000. Unlike synthetic streams, drift structure here is unknown, irregular, and potentially influenced by seasonality, demand fluctuations, and market dynamics.

1.Prequential Accuracy

The prequential accuracy curves show gradual performance oscillations rather than sharp regime shifts. At chunk size 300, accuracy is more volatile, reflecting sensitivity to short-term fluctuations. As chunk size increases, the trajectories become smoother and more stable, particularly at 800 and 1000.

Performance degradation appears progressive rather than abrupt, suggesting gradual drift. TFIDD maintains competitive accuracy across all chunk sizes without prolonged collapse. Highly reactive detectors exhibit larger oscillations, while conservative methods show slower adaptation during sustained shifts.

2. KS / MI Distribution Shift

The KS and MI plots indicate persistent distribution variation across time. MI remains consistently high, reflecting multi-dimensional distribution changes typical of real-world streams. KS shows localized spikes, especially at chunk sizes 500 and 800, indicating marginal distribution changes layered over broader structural evolution.

At chunk size 300, estimates are noisier. At 800 and 1000, the curves stabilize, showing smoother but still sustained drift intensity. The absence of isolated, extreme spikes suggests evolving conditions rather than abrupt regime replacement.

3. Cross-Chunk Alarm Analysis

Alarm frequency decreases substantially as chunk size increases. At chunk size 300, DDM generates extremely high alarms, reflecting oversensitivity to real-world noise. Even at larger chunk sizes, DDM remains alarm-heavy.

TFIDD maintains consistently low and controlled alarm counts across chunk sizes. Alarm frequency reduces from 300 to 1000 without collapsing to zero, indicating balanced sensitivity. MMD remains highly conservative with minimal alarms.

The monotonic reduction in TFIDD alarms with increasing chunk size demonstrates robustness to temporal granularity without alarm inflation.

4. Drift Score Dynamics

The drift score plots show sustained moderate drift levels rather than isolated spikes. At chunk size 300, the score fluctuates frequently. At 500 and above, the adaptive threshold rises gradually during extended divergence periods, preventing repeated triggering.

Peaks correspond to stronger market shifts, but between peaks the score stabilizes rather than oscillating randomly. Larger chunk sizes reduce volatility while preserving meaningful structural variation.

Top Drift-Driving Features

Top feature importance plots reveal that a small subset of features consistently dominates across chunk sizes. However, ranking order varies with temporal resolution, indicating evolving feature relevance over time.

Compared to synthetic datasets, Electricity shows stronger magnitude differences in permutation importance, reflecting real-world multi-factor dependency.

Feature Importance Trajectories

Feature trajectories show regime-like blocks of dominance where certain features gain influence for extended intervals before declining. At chunk size 300, trajectories are jagged and highly reactive. At larger chunk sizes, transitions appear smoother but remain interpretable.

The persistence of dominant features across time suggests structured market behavior rather than random noise.

5. Stability vs Recovery Trade-off

The stability–recovery plots show that highly sensitive detectors incur extremely high false alarm rates without proportional recovery gains. Conservative detectors maintain low false alarms but achieve limited recovery improvement.

Across all chunk sizes, TFIDD remains near the low-FAR region while maintaining competitive recovery performance. As chunk size increases, TFIDD moves closer to the stability-optimal zone without sacrificing adaptation capability.

6. Overall Interpretation

The Electricity stream exhibits gradual, irregular, real-world drift without annotated boundaries. Increasing chunk size reduces variance and alarm frequency while preserving structural performance trends. Across chunk sizes 300 to 1000, TFIDD demonstrates controlled sensitivity, stable adaptation, interpretable feature dynamics, and resistance to alarm explosion in a noisy real-world environment.
