RBF Dataset – Figure Explanation (Chunk Sizes: 300, 500, 800, 1000)

All figures evaluate TFIDD on the RBF dataset under gradual, nonlinear drift across four temporal resolutions: (a) 300, (b) 500, (c) 800, and (d) 1000. Compared to Hyperplane, RBF introduces more complex decision boundary movement, making stability and sensitivity balance more challenging.

1. Prequential Accuracy

The prequential accuracy curves show stronger volatility at chunk size 300, where the nonlinear drift produces noticeable drops and recoveries. As chunk size increases to 500, 800, and 1000, the trajectories become progressively smoother, reflecting reduced variance in parameter updates. However, unlike Hyperplane, the RBF stream exhibits deeper intermediate accuracy dips, indicating structural boundary movement rather than simple linear drift. TFIDD maintains competitive recovery across all chunk sizes without prolonged degradation, while overly reactive detectors display sharper oscillations and conservative methods show slower adaptation.

2. KS / MI Distribution Shift

The KS and MI curves show more pronounced localized spikes in RBF compared to Hyperplane. At chunk size 300, distribution shift signals fluctuate strongly due to smaller window estimates. At chunk sizes 800 and 1000, the curves become smoother, but distinct peaks remain visible, confirming structured nonlinear drift rather than noise. The presence of isolated KS spikes at higher chunk sizes indicates localized boundary deformation rather than global distribution shift.

3. Cross-Chunk Alarm Analysis

Average alarm frequency decreases as chunk size increases, consistent with statistical smoothing. DDM exhibits very high alarm counts at chunk sizes 300 and 500, indicating oversensitivity to nonlinear fluctuations. MMD remains extremely conservative with near-zero alarms at larger chunk sizes. TFIDD shows a controlled and monotonic reduction in alarms from 300 to 1000, demonstrating robustness to temporal granularity without alarm inflation.

4. Drift Score, Top Features, and Feature Importance Trajectories

The drift score plots reveal sharper and higher peaks in RBF compared to Hyperplane, especially at chunk sizes 300 and 500. These peaks correspond to nonlinear boundary shifts. The adaptive threshold tracks sustained structural divergence rather than isolated spikes, allowing TFIDD to respond to meaningful change while ignoring transient variation.

Top drift-driving feature plots show that different feature subsets dominate at different chunk sizes, indicating that RBF drift affects multiple dimensions in a distributed manner. Unlike linear drift, the importance ranking is less static across resolutions.

Feature importance trajectories confirm this dynamic behavior. Several features exhibit intermittent dominance during drift periods, and importance values fluctuate more aggressively at smaller chunk sizes. Larger chunk sizes smooth these trajectories while preserving the structural transitions.

5. Stability vs Recovery Trade-off

The stability-recovery plots show that highly sensitive detectors achieve marginally faster reaction but incur increased false alarms. Conservative detectors maintain very low false alarm rates but show limited recovery improvement. Across all chunk sizes, TFIDD remains in a balanced region, maintaining low false alarm rates while preserving competitive recovery under nonlinear drift conditions.

6. Overall Interpretation

The RBF stream presents a more complex drift structure, with nonlinear boundary movement and localized distribution changes. Increasing chunk size reduces variance and alarm frequency, but structural drift signals remain visible. Across chunk sizes 300 to 1000, TFIDD demonstrates stable adaptation, controlled sensitivity, and interpretable feature-level behavior without alarm explosion or excessive conservatism.
