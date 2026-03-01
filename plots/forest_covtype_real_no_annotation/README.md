Forest Covertype Dataset – Figure Explanation (Chunk Sizes: 300, 500, 800, 1000)

All figures evaluate TFIDD on the Forest Covertype stream without annotated drift boundaries across four chunk sizes: (a) 300, (b) 500, (c) 800, and (d) 1000. This dataset reflects natural environmental variation, terrain heterogeneity, and long-term spatial distribution shifts rather than synthetic regime switches.

1.Prequential Accuracy

The prequential accuracy curves show sustained high performance after the initial burn-in phase. At chunk size 300, accuracy fluctuates more frequently, reflecting sensitivity to short-term distribution changes. As chunk size increases, trajectories become smoother and more stable, especially at 800 and 1000.

Performance degradation appears gradual rather than catastrophic, indicating progressive structural evolution. TFIDD maintains competitive accuracy throughout the stream without prolonged instability. Highly reactive detectors show slightly larger oscillations, while conservative methods adapt more slowly during extended distribution changes.

2. KS / MI Distribution Shift

The KS and MI curves reveal structured distribution movement. MI increases notably at specific intervals, especially at chunk sizes 500 and 800, indicating strong multidimensional shifts. KS remains comparatively smaller but shows localized spikes corresponding to marginal feature redistribution.

At larger chunk sizes, MI exhibits clearer phase transitions, suggesting macro-level structural evolution rather than noise. The divergence between KS and MI indicates that shifts are primarily multivariate rather than isolated marginal changes.

3. Cross-Chunk Alarm Analysis

Alarm frequency decreases significantly as chunk size increases. At chunk size 300, DDM produces extremely high alarm counts, reflecting strong sensitivity to natural variability. Even at chunk size 1000, DDM remains substantially more reactive than other detectors.

TFIDD maintains very low and stable alarm counts across all chunk sizes. The reduction in alarms with increasing chunk size demonstrates robustness to temporal aggregation. MMD remains highly conservative with minimal alarms throughout.

The monotonic decrease in TFIDD alarms suggests controlled sensitivity without alarm explosion under environmental variability.

4. Drift Score Dynamics

The TFIDD drift score shows an early sharp increase during the initial transition phase, followed by a long region of moderate oscillation. At chunk size 300, the score exhibits higher variance. As chunk size increases, the trajectory becomes smoother while preserving clear structural phases.

The adaptive threshold stabilizes after the initial phase, preventing repeated triggering during extended but moderate drift periods. Later segments show gradual score elevation rather than abrupt spikes, indicating evolving terrain structure instead of sudden regime change.

Top Drift-Driving Features

Top feature importance plots show consistent dominance of a small subset of features across chunk sizes. However, feature ranking varies slightly with chunk size, suggesting temporal dependence in environmental feature relevance.

At chunk size 300, importance magnitudes are more dispersed. At larger chunk sizes, dominance becomes clearer, indicating aggregation amplifies structurally significant variables.

Feature Importance Trajectories

Feature trajectories reveal extended dominance blocks where specific features control the decision boundary for long intervals before gradually declining. At smaller chunk sizes, transitions are noisier and more granular. At 800 and 1000, trajectories become smoother and show clearer regime-like segments.

This behavior suggests spatial or ecological substructure shifts rather than random noise-driven fluctuation.

5. Stability vs Recovery Trade-off

The stability–recovery plots show that highly sensitive detectors incur higher false alarm rates without proportional recovery gain. Conservative detectors maintain low false alarms but achieve limited recovery improvement.

Across all chunk sizes, TFIDD remains positioned near the low-FAR region while preserving competitive recovery performance. As chunk size increases, TFIDD moves closer to the stability-optimal region without losing adaptation capability.

6. Overall Interpretation

The Forest Covertype stream exhibits gradual, structured distribution evolution characteristic of real-world environmental data. Increasing chunk size reduces volatility and alarm frequency while maintaining interpretability of drift dynamics. Across chunk sizes 300 to 1000, TFIDD demonstrates stable adaptation, low false alarms, interpretable feature transitions, and robustness under sustained multivariate environmental drift.
