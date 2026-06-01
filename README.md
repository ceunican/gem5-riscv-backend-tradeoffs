# Reproducibility Artifact: Design Tradeoffs in Backend Organization in Out-Of-Order RISC-V Processors

This repository contains the necessary patch and instructions to reproduce the experiments detailed in the paper "Design Tradeoffs in Backend Organization in Out-Of-Order RISC-V Processors".

## gem5 Source Code
The modifications made to the gem5 source code are available in `backend-tradeoffs.patch`. This patch includes:
- Our implementation of a **Least-Full** instruction steering policy.
- Custom statistics added to accurately monitor and evaluate the behavior of the `IqUnits`.

*Note:* The Least-Full steering policy provided in this patch was developed specifically for the experiments in this paper. We note that it conceptually aligns with the recently proposed upstream gem5 PR [#3115](https://github.com/gem5/gem5/pull/3115) (`cpu-o3: add LeastLoaded IQ insertion policy`), which further highlights the community's growing interest in standardizing this mechanism.

### Applying the patch
```bash
# 1. Clone the official gem5 repository
git clone https://github.com/gem5/gem5
cd gem5

# 2. Checkout the specific base commit used in our evaluation
git checkout 7a2b0e4

# 3. Apply the patch
git apply backend-tradeoffs.patch
