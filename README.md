# Multimmit numerical measurement supplements

This package contains two compact, machine-readable transcriptions of the measurement tables accompanying the paper. They contain aggregate measurements, not raw logs, metadata about individuals, or access credentials.

* `multimmit-90-run-summary.csv`: 90 accepted Multimmit testbed/scenario/mode runs, with achieved throughput, placement latency quantiles (P25, P50, P75, P99), ordered-delivery median, and payment receipt median when applicable. The eight censorship rows in this file describe **all blocks** in each censorship run.
* `multimmit-censored-view-summary.csv`: eight 500k-tx/s rows, restricted to the **blocks associated with censoring views**. Victim-chain data are selected by inferring the view in which the block would have been finalized if the leader had been honest, using the median finalization view of nonvictim blocks submitted within 25 ms. Other-chain values use blocks first finalized in those censoring views. The nine censors control consecutive views in each 50-view cycle. This table reports the victim-block count and share first finalized by extension.

All times are in milliseconds. A blank receipt or extension-share field means the metric is not applicable or was not reported. The outputs are transcribed from the supplied measurement reports, not independently verified against the source telemetry. 

These tables make the reported numerical results available without rerunning the 50-validator cloud deployments. They do not by themselves supply enough observations to recreate within-run latency distributions or interquartile plots for the comparison protocols; those depend on the published comparison records and, for Multimmit, the raw per-block cohort data.

The source, configs, and reproduction scripts are separately described in the anonymously hosted code artifact.
