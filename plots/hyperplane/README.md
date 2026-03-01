Hyperplane Dataset – Figure Explanation (Chunk Sizes: 300, 500, 800, 1000)

All figures evaluate TFIDD on the Hyperplane dataset under gradual concept drift across four temporal resolutions: (a) 300, (b) 500, (c) 800, and (d) 1000. The goal is to examine how detection behavior, stability, and interpretability evolve as chunk size increases.

Prequential Accuracy

These plots show test-then-train accuracy over time. At chunk size 300, accuracy curves exhibit stronger short-term fluctuations due to higher temporal resolution. As chunk size increases to 500, 800, and 1000, the trajectories become progressively smoother, reflecting statistical stabilization over larger windows. Larger chunks reduce variance and suppress transient oscillations, though adaptation becomes slightly less reactive. Across all resolutions, TFIDD maintains stable post-drift accuracy without the sharp resets seen in highly reactive detectors or the stagnation observed in overly conservative ones.

KS / MI Distribution Shift

These figures present distributional change using the Kolmogorov–Smirnov statistic and Mutual Information variation between consecutive windows. With smaller chunks, both KS and MI signals fluctuate more strongly because estimates are based on fewer samples. As chunk size increases, the distribution shift curves become smoother and more consistent, confirming that the Hyperplane drift is gradual rather than abrupt. The reduced variance at larger chunk sizes explains why conservative detectors become less reactive under coarser temporal resolution.

Cross-Chunk Alarm Analysis

This comparison shows average alarm frequency across chunk sizes. As temporal resolution becomes coarser, alarm frequency generally decreases due to statistical smoothing. DDM exhibits high variability and instability across resolutions, while MMD remains highly conservative with minimal alarms. TFIDD maintains bounded and consistent alarm behavior across all chunk sizes, demonstrating robustness to temporal resolution changes without alarm explosion.

Drift Score, Top Features, and Feature Importance Trajectories

The drift score plots show the instantaneous drift magnitude alongside the adaptive threshold. At chunk size 300, score spikes are sharper and more reactive. At larger chunk sizes, the score evolves more smoothly and aligns clearly with sustained drift periods. TFIDD triggers alarms only when structural divergence persists beyond the adaptive threshold, avoiding isolated spikes.

The top drift-driving feature plots rank features using permutation importance. Across all chunk sizes, dominant features remain largely consistent, indicating that drift affects a structured subset of dimensions rather than the entire feature space.

The feature importance trajectory plots further confirm this behavior. Dominant features shift during drift intervals, while non-dominant features remain relatively stable. Larger chunk sizes produce smoother importance curves, reinforcing the interpretation that TFIDD responds to meaningful structural evolution rather than random noise.

Stability vs Recovery Trade-off

These plots compare False Alarm Rate against Recovery Gain. Highly sensitive detectors achieve faster reaction but suffer from elevated false alarms and unstable recovery. Extremely conservative methods maintain low false alarms but adapt slowly. Across all chunk sizes, TFIDD consistently occupies a balanced region, maintaining controlled sensitivity, moderate delay, and stable recovery performance.

Overall Interpretation

Increasing chunk size reduces statistical variance, smooths drift signals, and lowers alarm frequency. Despite these changes in temporal resolution, TFIDD remains stable, interpretable, and robust across chunk sizes 300 to 1000. The results confirm that TFIDD effectively handles gradual drift in the Hyperplane dataset while preserving balanced detection behavior and feature-level interpretability.
