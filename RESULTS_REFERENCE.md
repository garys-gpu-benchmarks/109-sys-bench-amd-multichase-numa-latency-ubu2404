# Results: 109 multichase Pointer-Chase

**Main goal:** Measure cache and NUMA pointer-chase latency  
**Tools:** Compile src/multichase.c; run build/multichase under numactl via scripts/collect_multichase.py

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_142 · recorded 2026-11-16). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× AMD Instinct MI300X VF (196288 MB) · INTEL(R) XEON(R) PLATINUM 8568Y+ · Ubuntu 24.04.5 LTS · kernel 6.8.0-147-generic · driver 7.1.9.31600000
- **Run:** 2026-11-16T11:05:22Z · status **N/A-EXPECTED** (exit 0)
- **Time (mm:ss):** setup 00:07 · benchmark 00:02 · whole run 00:19
- **Source:** run 109_20261116_110522
- **Command:** `bash run_benchmark.sh --smoke --num-numa-nodes 1 --working-set-size l1=16384,l2=262144,l3=2097152,local_dram=268435456,remote_dram=268435456 --stride 64 --warmup-iters 10000 --num-iterations 200000 --num-threads 1 --thread-affinity 0-3`

| # | Metric | Result |
|---|---|---|
| 1 | Pointer-chase latency for the L1-cache tier (latency_ns_l1) | 1.43979 |
| 2 | Pointer-chase latency for the L2-cache tier (latency_ns_l2) | 4.05368 |
| 3 | Pointer-chase latency for the L3-cache tier (latency_ns_l3) | 8.660455 |
| 4 | Local DRAM latency, ns (latency_ns_local_dram) | 57.388945 |
| 5 | Remote DRAM latency, ns, na on a host with fewer than two NUMA nodes (latency_ns_remote_dram) | na (expected: needs a second NUMA node) |
<!-- /profile:smoke -->
