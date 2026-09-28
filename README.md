# PHASE: A Platform for Hardware and Software Evaluation of Memory Tiering

**Authors:** Dikla Tzafrir, Shaurya Patel, Joel Nider, and Alexandra (Sasha) Fedorova (University of British Columbia)

**Presented at DIMES '26 (4th Workshop on Disruptive Memory Systems), Prague, Czech Republic**

---

## 🚧 Code Release in Progress
The QEMU platform and kernel modules will be open-sourced in this repository by late October 2026.

## 📄 Paper
Read the full publication here: [ACM Digital Library](https://dl.acm.org/doi/10.1145/3831664.3837789).

## 💡 Overview
PHASE is a modular, QEMU-based emulation environment designed to integrate hardware hot-page far-memory tracking mechanisms with software-driven memory tiering policies. 

Traditionally, evaluating hardware telemetry required complex RTL or FPGA deployments, while software-only policies lacked hardware precision. PHASE bridges this co-design gap by allowing researchers to use a family of hardware trackers—modeled after the M5 top-k tracker—as a drop-in replacement for hot-page tracking in Linux kernel algorithms like TPP and Nomad, requiring minimal kernel changes.

## 📊 Key Findings
By combining a hardware far-memory Top-K tracker with existing software tiering policies, our evaluation demonstrates:

* **The Locality Paradox:** High-precision, conservative hardware tracking significantly outperforms 100% software locality by preventing thrashing and interconnect saturation.
* **Throughput & Latency:** Hardware-assisted tracking delivers up to 5.6x higher bandwidth and 6x lower memory access latency compared to aggressive software methods.
* **System CPU Overhead:** Offloading telemetry to the far-memory hardware drops kernel CPU utilization from over 45% (under TPP) down to under 0.3%, freeing CPU cores for actual application workloads.
* **Policy Interaction:** Accurate hardware tracking minimizes the necessity for complex, sophisticated software migration optimizations (like Nomad's shadow paging).
