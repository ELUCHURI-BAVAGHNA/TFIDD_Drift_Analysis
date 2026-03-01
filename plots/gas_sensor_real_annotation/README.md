Gas Sensor Dataset – Figure Explanation (Annotated Drifts)

This dataset contains explicitly annotated drift regions corresponding to sensor recalibration phases and gas mixture changes. The shaded vertical regions in the figures represent known drift intervals. Results are reported for chunk sizes: (a) 300, (b) 500, (c) 800, and (d) 1000.

Unlike gradual environmental datasets, Gas Sensor exhibits sharper regime transitions with well-defined boundaries.

1. Prequential Accuracy

At chunk size 300, accuracy fluctuates strongly around annotated drift regions. Performance drops align closely with shaded intervals, followed by partial recovery. TFIDD stabilizes faster than highly reactive detectors, which show deeper oscillations.

As chunk size increases, accuracy curves become smoother. At 800 and 1000, transitions appear compressed into fewer but more pronounced segments. Larger chunking reduces variance but increases recovery lag after abrupt transitions.

The alignment between annotated drift regions and accuracy degradation confirms that performance changes correspond to true structural shifts rather than noise.

2. KS / MI Distribution Shift

Both KS and MI display pronounced spikes around annotated drift intervals. KS captures sharp marginal distribution changes, often peaking immediately at drift boundaries. MI reflects broader multivariate restructuring and shows sustained elevation across drift windows.

At chunk size 300, shift signals are high-frequency and granular. At larger chunk sizes, peaks consolidate, producing fewer but clearer distribution transitions. The persistence of elevated MI around drift windows confirms multi-feature structural change rather than isolated feature perturbation.

3. Cross-Chunk Alarm Analysis

Alarm frequency decreases steadily as chunk size increases. At chunk size 300, DDM produces substantially more alarms than TFIDD and MMD, reflecting high sensitivity to short-term fluctuations within drift windows.

TFIDD maintains moderate alarm counts aligned with annotated drift intervals. At chunk sizes 800 and 1000, alarm counts reduce significantly, indicating stable behavior under temporal aggregation.

The monotonic decline in alarms across chunk sizes suggests that short-window volatility, rather than false triggering, drives higher alarm counts at smaller chunk sizes.

4. Drift Score Dynamics

TFIDD drift scores rise sharply at annotated drift intervals. The adaptive threshold increases during high-variance periods and stabilizes afterward, preventing repeated triggering inside the same drift region.

At chunk size 300, multiple localized peaks appear within each annotated region, reflecting fine-grained detection. At 800 and 1000, drift appears as fewer but larger score surges, corresponding to aggregated regime transitions.

Score resets after adaptation indicate successful model stabilization before the next structural change.
Top Drift-Driving Features

Feature importance rankings change across chunk sizes, indicating that different sensor channels dominate during different drift intervals. At smaller chunk sizes, importance values are more dispersed, reflecting localized transient effects.

At larger chunk sizes, a smaller subset of features dominates importance, implying that aggregated drift reveals consistent structural drivers rather than short-term sensor noise.

The variability of dominant features across chunks aligns with physical recalibration phases in sensor arrays.

Feature Importance Trajectories

Feature trajectories show sharp spikes within annotated drift windows, followed by stabilization. At chunk size 300, trajectories are jagged and highly responsive. At 800 and 1000, trajectories become smoother and more block-like, reflecting regime segmentation.

Certain features exhibit repeated dominance across multiple drift regions, suggesting recurring sensitivity to specific gas concentration shifts.

5. Stability vs Recovery Trade-off

The stability–recovery plots show that highly reactive detectors achieve higher short-term recovery but at the cost of increased false alarm rates. Conservative detectors show low FAR but slower adaptation.

Across chunk sizes, TFIDD remains near the low-FAR region while maintaining competitive recovery gain. At chunk size 800, TFIDD achieves positive recovery with near-zero FAR, indicating balanced adaptation.

At chunk size 1000, FAR approaches zero for several detectors, but recovery gains diminish, reflecting delayed adaptation under coarse granularity.

6. Overall Interpretation

The Gas Sensor dataset demonstrates clearly defined abrupt drift phases corresponding to sensor recalibration and mixture shifts. Smaller chunk sizes provide fine-grained detection but increase volatility and alarms. Larger chunk sizes smooth drift signals and reduce alarms but may compress or delay adaptation.

Across all chunk sizes, TFIDD maintains strong alignment with annotated drift intervals, controlled alarm frequency, interpretable feature transitions, and balanced stability–recovery performance under abrupt structural shifts.
