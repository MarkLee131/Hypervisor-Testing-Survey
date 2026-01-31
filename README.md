# Hypervisor Testing Research Papers

[![Contributions Welcome](https://img.shields.io/badge/Contributions-Welcome-brightgreen.svg)]()
[![License](https://img.shields.io/badge/License-CC--BY--NC--4.0-blue.svg)](LICENSE)

> A systematic collection of research papers on hypervisor testing and fuzzing, including virtual device testing, vCPU emulation, hypercall interfaces, and nested virtualization. This repository accompanies our survey paper "Hypervisor Testing: Techniques, Challenges, and Future
Directions". Feel free to make contributions by creating pull requests.

---

## Paper Collection Methodology

We followed a rigorous literature review protocol adapted from [Kitchenham's guidelines](https://www.elsevier.com/__data/promis_misc/525444systematicreviewsguide.pdf):

**Database Search**: ACM Digital Library, IEEE Xplore, USENIX, DBLP, Semantic Scholar

**Search Query**:
```
("Hypervisor" OR "VMM" OR "QEMU" OR "KVM" OR "Xen" OR "Hyper-V" OR "VirtualBox" OR "Virtual Device")
AND ("Fuzzing" OR "Fuzz Testing" OR "Security Testing" OR "Vulnerability Detection" OR "Symbolic Execution")
```

**Venue Filter**: Top-tier security (S&P, USENIX Security, CCS, NDSS), systems (OSDI, SOSP, EuroSys, ATC), and software engineering (ICSE, FSE, ASE) conferences.

**Snowballing**: Backward (references) and forward (Google Scholar citations) until saturation.

**Tool Collection**: GitHub search with star ranking and activity filtering.

---

## Contents

### By Year

[2026](#2026) | [2025](#2025) | [2024](#2024) | [2023](#2023) | [2022](#2022) | [2021](#2021) | [2020](#2020) | [2017](#2017)

### By Testing Target

[Virtual Device Testing](#virtual-device-testing) | [vCPU Emulation Testing](#vcpu-emulation-testing) | [Hypercall and VM-Exit Testing](#hypercall-and-vm-exit-testing) | [Nested Virtualization Testing](#nested-virtualization-testing)

### By Technique

[Coverage-Guided Fuzzing](#coverage-guided-fuzzing) | [Grammar and Dependency-Aware Fuzzing](#grammar-and-dependency-aware-fuzzing) | [DMA-Centric Approaches](#dma-centric-approaches) | [Hybrid Fuzzing with Symbolic Execution](#hybrid-fuzzing-with-symbolic-execution) | [Trace-Based and Replay Approaches](#trace-based-and-replay-approaches) | [Universal and Black-Box Approaches](#universal-and-black-box-approaches)

---

## All Papers (By Year)

### 2026

#### EuroSys

- **NecoFuzz**: Effective Fuzzing of Nested Virtualization via Fuzz-Harness Virtual Machines
  - *Authors*: Ishii et al. (University of Tokyo)
  - *Target*: KVM, Xen, VirtualBox (Nested Virtualization)
  - *Findings*: 6 vulnerabilities (CVE-2023-30456, CVE-2024-21106)

#### NDSS

- **HyperMirage**: Direct State Manipulation in Hybrid Virtual CPU Fuzzing [[pdf]](https://www.sec.in.tum.de/i20/publications/hypermirage-direct-state-manipulation-in-hybrid-virtual-cpu-fuzzing/@@download/file/ndss26-summer-final1763.pdf)
  - *Authors*: Andreas et al.
  - *Target*: Multiple hypervisors (vCPU emulation)


### 2025

#### NDSS

- **Truman**: Constructing Device Behavior Models from OS Drivers to Fuzz Virtual Devices [[pdf]](https://www.ndss-symposium.org/wp-content/uploads/2025-301-paper.pdf)
  - *Authors*: Ma et al.
  - *Target*: QEMU, VirtualBox, VMware Workstation Pro, Parallels
  - *Findings*: 54 new bugs, 6 CVEs

#### ICSE

- **InSVDF**: Interface-State-Aware Virtual Device Fuzzing [[pdf]](https://ieeexplore.ieee.org/document/11029782/)
  - *Authors*: Zhang et al.
  - *Target*: QEMU
  - *Findings*: 2 new vulnerabilities, 1 CVE

### 2024

#### USENIX Security

- **HYPERPILL**: Fuzzing for Hypervisor-bugs by Leveraging the Hardware Virtualization Interface [[pdf]](https://www.usenix.org/system/files/usenixsecurity24-bulekov.pdf)
  - *Authors*: Bulekov et al.
  - *Target*: Multiple hypervisors (universal approach)


### 2023

#### S&P (IEEE Symposium on Security and Privacy)

- **ViDeZZo**: Dependency-aware Virtual Device Fuzzing [[pdf]](https://ieeexplore.ieee.org/document/10179354/)
  - *Authors*: Liu et al.
  - *Target*: QEMU, VirtualBox (28 virtual devices across 4 architectures)
  - *Findings*: 24 existing + 28 new bugs, 7 patches accepted

#### ASE

- **VD-Guard**: DMA Guided Fuzzing for Hypervisor Virtual Device [[pdf]](https://ieeexplore.ieee.org/document/10298337/)
  - *Authors*: Liu et al.
  - *Target*: QEMU, VirtualBox
  - *Findings*: 4 new vulnerabilities, 3 CVEs

#### DSN

- **IRIS**: A Record and Replay Framework to Enable Hardware-assisted Virtualization Fuzzing [[pdf]](https://ieeexplore.ieee.org/document/10202630/)
  - *Authors*: Cesarano et al. (Federico II University of Naples)
  - *Target*: Xen hypervisor
  - *GitHub*: https://github.com/dessertlab/iris

### 2022

#### USENIX Security

- **Morphuzz**: Bending (Input) Space to Fuzz Virtual Devices [[pdf]](https://www.usenix.org/system/files/sec22-bulekov.pdf)
  - *Authors*: Bulekov et al.
  - *Target*: QEMU

- **MundoFuzz**: Hypervisor Fuzzing with Statistical Coverage Testing and Grammar Inference [[pdf]](https://www.usenix.org/system/files/sec22-myung.pdf)
  - *Authors*: Myung et al.
  - *Target*: Multiple hypervisors

#### EuroSys

- **Nyx-Net**: Network Fuzzing with Incremental Snapshots [[pdf]](https://dl.acm.org/doi/10.1145/3492321.3519591)
  - *Authors*: Schumilo et al.
  - *Target*: Network services (extends Nyx framework)
  - *Findings*: Bugs in Lighttpd, MySQL client, Firefox IPC

### 2021

#### USENIX Security

- **Nyx**: Greybox Hypervisor Fuzzing using Fast Snapshots and Affine Types [[pdf]](https://www.usenix.org/system/files/sec21-schumilo.pdf)
  - *Authors*: Schumilo et al.
  - *Target*: QEMU/KVM, bhyve

#### CCS

- **V-Shuttle**: Scalable and Semantics-Aware Hypervisor Virtual Device Fuzzing [[pdf]](https://dl.acm.org/doi/10.1145/3460120.3484811)
  - *Authors*: Pan et al.
  - *Target*: QEMU, VirtualBox
  - *Findings*: 35 new bugs, 17 CVEs

- **HyperFuzzer**: An Efficient Hybrid Fuzzer for Virtual CPUs [[pdf]](https://dl.acm.org/doi/10.1145/3460120.3484748)
  - *Authors*: Ge et al. (Microsoft Research)
  - *Target*: Microsoft Hyper-V (vCPU emulation)
  - *Findings*: 11 previously unknown bugs

#### Black Hat USA

- **hAFL1**: Our Journey of Fuzzing Hyper-V and Discovering a Critical 0-Day [[slides]](https://www.blackhat.com/us-21/briefings/schedule/#hafl-our-journey-of-fuzzing-hyper-v-and-discovering-a-critical--day-23498)
  - *Authors*: Harpaz & Hadar (Guardicore, SafeBreach)
  - *Target*: Microsoft Hyper-V (vmswitch.sys)
  - *Findings*: CVE-2021-28476 (CVSS 9.9)

### 2020

#### NDSS

- **HYPER-CUBE**: High-Dimensional Hypervisor Fuzzing [[pdf]](https://www.ndss-symposium.org/wp-content/uploads/2020/02/23096.pdf)
  - *Authors*: Schumilo et al.
  - *Target*: QEMU, VirtualBox, ACRN, bhyve, VMware Fusion
  - *Findings*: 54 novel bugs, 43 CVEs

### 2017

#### RAID

- **VDF**: Targeted Evolutionary Fuzz Testing of Virtual Devices [[pdf]](https://link.springer.com/chapter/10.1007/978-3-319-66332-6_1)
  - *Authors*: Henderson et al.
  - *Target*: QEMU

---

## Papers by Testing Target

### Virtual Device Testing

Virtual devices are the primary attack surface of hypervisors, exposing interfaces for MMIO/PIO operations, DMA transfers, and interrupt handling.

- **HYPER-CUBE**: High-Dimensional Hypervisor Fuzzing (NDSS '20) [[pdf]](https://www.ndss-symposium.org/wp-content/uploads/2020/02/23096.pdf)
- **Nyx**: Greybox Hypervisor Fuzzing using Fast Snapshots and Affine Types (USENIX Security '21) [[pdf]](https://www.usenix.org/system/files/sec21-schumilo.pdf)
- **V-Shuttle**: Scalable and Semantics-Aware Hypervisor Virtual Device Fuzzing (CCS '21) [[pdf]](https://dl.acm.org/doi/10.1145/3460120.3484811)
- **hAFL1**: Our Journey of Fuzzing Hyper-V and Discovering a Critical 0-Day (Black Hat USA '21)
- **Morphuzz**: Bending (Input) Space to Fuzz Virtual Devices (USENIX Security '22) [[pdf]](https://www.usenix.org/system/files/sec22-bulekov.pdf)
- **ViDeZZo**: Dependency-aware Virtual Device Fuzzing (S&P '23) [[pdf]](https://ieeexplore.ieee.org/document/10179354/)
- **VD-Guard**: DMA Guided Fuzzing for Hypervisor Virtual Device (ASE '23) [[pdf]](https://ieeexplore.ieee.org/document/10298337/)
- **Truman**: Constructing Device Behavior Models from OS Drivers to Fuzz Virtual Devices (NDSS '25) [[pdf]](https://www.ndss-symposium.org/wp-content/uploads/2025-301-paper.pdf)
- **InSVDF**: Interface-State-Aware Virtual Device Fuzzing (ICSE '25) [[pdf]](https://ieeexplore.ieee.org/document/11029782/)
- **VDF**: Targeted Evolutionary Fuzz Testing of Virtual Devices (RAID '17) [[pdf]](https://link.springer.com/chapter/10.1007/978-3-319-66332-6_1)

### vCPU Emulation Testing

vCPU emulation involves instruction decoding, operand handling, privilege checks, and exception injection. Vulnerabilities can cause incorrect guest execution or enable guest-to-host escape.

- **HyperFuzzer**: An Efficient Hybrid Fuzzer for Virtual CPUs (CCS '21) [[pdf]](https://dl.acm.org/doi/10.1145/3460120.3484748)
- **HyperMirage**: Direct State Manipulation in Hybrid Virtual CPU Fuzzing (NDSS '26)

### Hypercall and VM-Exit Testing

Hypercalls provide a direct interface for guest-to-hypervisor communication, while VM-exits transfer control to the hypervisor for privileged operations.

- **MundoFuzz**: Hypervisor Fuzzing with Statistical Coverage Testing and Grammar Inference (USENIX Security '22) [[pdf]](https://www.usenix.org/system/files/sec22-myung.pdf)
- **HYPERPILL**: Fuzzing for Hypervisor-bugs by Leveraging the Hardware Virtualization Interface (USENIX Security '24) [[pdf]](https://www.usenix.org/system/files/usenixsecurity24-bulekov.pdf)

### Nested Virtualization Testing

Nested virtualization enables running hypervisors inside VMs, introducing additional complexity in VMCS shadowing, nested page table management, and VM-exit handling.

- **IRIS**: A Record and Replay Framework to Enable Hardware-assisted Virtualization Fuzzing (DSN '23) [[pdf]](https://ieeexplore.ieee.org/document/10202630/)
- **NecoFuzz**: Effective Fuzzing of Nested Virtualization via Fuzz-Harness Virtual Machines (EuroSys '26) [[pdf]](https://arxiv.org/pdf/2512.08858)

---

## Papers by Technique

### Coverage-Guided Fuzzing

Approaches that use code coverage feedback to guide input generation and explore new execution paths.

- **HYPER-CUBE**: High-Dimensional Hypervisor Fuzzing (NDSS '20) [[pdf]](https://www.ndss-symposium.org/wp-content/uploads/2020/02/23096.pdf)
- **Nyx**: Greybox Hypervisor Fuzzing using Fast Snapshots and Affine Types (USENIX Security '21) [[pdf]](https://www.usenix.org/system/files/sec21-schumilo.pdf)
- **Nyx-Net**: Network Fuzzing with Incremental Snapshots (EuroSys '22) [[pdf]](https://dl.acm.org/doi/10.1145/3492321.3519591)
- **MundoFuzz**: Hypervisor Fuzzing with Statistical Coverage Testing and Grammar Inference (USENIX Security '22) [[pdf]](https://www.usenix.org/system/files/sec22-myung.pdf)

### Grammar and Dependency-Aware Fuzzing

Approaches that leverage protocol specifications, message dependencies, or device behavior models to generate semantically valid inputs.

- **V-Shuttle**: Scalable and Semantics-Aware Hypervisor Virtual Device Fuzzing (CCS '21) [[pdf]](https://dl.acm.org/doi/10.1145/3460120.3484811)
- **ViDeZZo**: Dependency-aware Virtual Device Fuzzing (S&P '23) [[pdf]](https://ieeexplore.ieee.org/document/10179354/)
- **MundoFuzz**: Hypervisor Fuzzing with Statistical Coverage Testing and Grammar Inference (USENIX Security '22) [[pdf]](https://www.usenix.org/system/files/sec22-myung.pdf)
- **Truman**: Constructing Device Behavior Models from OS Drivers to Fuzz Virtual Devices (NDSS '25) [[pdf]](https://www.ndss-symposium.org/wp-content/uploads/2025-301-paper.pdf)
- **hAFL1**: Our Journey of Fuzzing Hyper-V and Discovering a Critical 0-Day (Black Hat USA '21)
### DMA-Centric Approaches

Approaches that specifically target DMA (Direct Memory Access) handling in virtual devices.

- **Morphuzz**: Bending (Input) Space to Fuzz Virtual Devices (USENIX Security '22) [[pdf]](https://www.usenix.org/system/files/sec22-bulekov.pdf)
- **VD-Guard**: DMA Guided Fuzzing for Hypervisor Virtual Device (ASE '23) [[pdf]](https://ieeexplore.ieee.org/document/10298337/)
- **InSVDF**: Interface-State-Aware Virtual Device Fuzzing (ICSE '25) [[pdf]](https://ieeexplore.ieee.org/document/11029782/)

### Hybrid Fuzzing with Symbolic Execution

Approaches that combine fuzzing with symbolic execution to systematically explore complex code paths.

- **HyperFuzzer**: An Efficient Hybrid Fuzzer for Virtual CPUs (CCS '21) [[pdf]](https://dl.acm.org/doi/10.1145/3460120.3484748)
  - Uses "Nimble Symbolic Execution" with Intel PT for efficient vCPU testing

### Trace-Based and Replay Approaches

Approaches that use execution traces or record-and-replay mechanisms.

- **VDF**: Targeted Evolutionary Fuzz Testing of Virtual Devices (RAID '17) [[pdf]](https://link.springer.com/chapter/10.1007/978-3-319-66332-6_1)
- **IRIS**: A Record and Replay Framework to Enable Hardware-assisted Virtualization Fuzzing (DSN '23) [[pdf]](https://ieeexplore.ieee.org/document/10202630/)

### Universal and Black-Box Approaches

Approaches designed to work across multiple hypervisors without requiring source code access or hypervisor-specific modifications.

- **HYPERPILL**: Fuzzing for Hypervisor-bugs by Leveraging the Hardware Virtualization Interface (USENIX Security '24) [[pdf]](https://www.usenix.org/system/files/usenixsecurity24-bulekov.pdf)
- **NecoFuzz**: Effective Fuzzing of Nested Virtualization via Fuzz-Harness Virtual Machines (EuroSys '26)[[pdf]](https://arxiv.org/pdf/2512.08858)

---

## Target Hypervisors Summary

| Hypervisor | Papers |
|------------|--------|
| **QEMU/KVM** | HYPER-CUBE, Nyx, Morphuzz, V-Shuttle, ViDeZZo, VD-Guard, Truman, InSVDF, VDF, NecoFuzz |
| **VirtualBox** | HYPER-CUBE, V-Shuttle, ViDeZZo, VD-Guard, Truman, NecoFuzz |
| **Hyper-V** | HyperFuzzer, hAFL1 |
| **Xen** | IRIS, NecoFuzz |
| **VMware** | HYPER-CUBE (Fusion), Truman (Workstation Pro) |
| **bhyve** | HYPER-CUBE, Nyx |
| **ACRN** | HYPER-CUBE |
| **Parallels** | Truman |

---

## Bug Discovery Statistics

| Tool | Venue | New Bugs | CVEs |
|------|-------|----------|------|
| HYPER-CUBE | NDSS '20 | 54 | 43 |
| V-Shuttle | CCS '21 | 35 | 17 |
| HyperFuzzer | CCS '21 | 11 | - |
| hAFL1 | Black Hat '21 | 1 | 1 (CVSS 9.9) |
| ViDeZZo | S&P '23 | 52 | 7+ |
| VD-Guard | ASE '23 | 4 | 3 |
| Truman | NDSS '25 | 54 | 6 |
| InSVDF | ICSE '25 | 2 | 1 |
| NecoFuzz | EuroSys '26 | 6 | 2 |

---

## Open-Source Tools

| Tool | Repository | Status |
|------|------------|--------|
| HYPER-CUBE | [RUB-SysSec/hypercube](https://github.com/RUB-SysSec/hypercube) | Available |
| Nyx | [nyx-fuzz/Nyx](https://github.com/nyx-fuzz/Nyx) | Available |
| Morphuzz | [QEMU upstream](https://www.qemu.org/) | Merged |
| V-Shuttle | [hustdebug/v-shuttle](https://github.com/hustdebug/v-shuttle) | Available |
| ViDeZZo | [HexHive/ViDeZZo](https://github.com/HexHive/ViDeZZo) | Available |
| IRIS | [dessertlab/iris](https://github.com/dessertlab/iris) | Available |
| Truman | [truman](https://github.com/vul337/Truman) | Available |

---

## Related Resources

### Foundational Tools

- **kAFL**: Hardware-Assisted Feedback Fuzzing for OS Kernels (USENIX Security '17) [[pdf]](https://www.usenix.org/system/files/conference/usenixsecurity17/sec17-schumilo.pdf) - Foundation for many hypervisor fuzzers
- **AFL**: American Fuzzy Lop - Core mutation strategies used by many tools
- **Intel PT**: Hardware tracing used for coverage feedback


---

## Seven-Dimensional Taxonomy

We propose a unified taxonomy for classifying hypervisor testing techniques. Each dimension represents an orthogonal design axis.

| Dimension | Question | Options |
|-----------|----------|---------|
| **D1: Target** | What component is tested? | Virtual devices, Hypercalls/VM-exits, vCPU emulation, Core subsystems |
| **D2: Input Model** | What is the input abstraction? | Raw bytes, Structured messages, I/O op sequences, Instruction+CPU state, Full VM state |
| **D3: Input Source** | Where do seeds come from? | Pattern/random, Trace-based, Specification-based, Inference-based, Driver-derived |
| **D4: Instrumentation** | How is execution observed? | Compile-time, Hardware tracing (Intel PT), Dynamic binary instrumentation, Emulation-based |
| **D5: Feedback** | What signals guide fuzzing? | Code coverage, State coverage, Interface coverage, Differential/semantic, Hybrid |
| **D6: Execution & Reset** | How is state managed? | VM snapshot, Fork-based (CoW), Full reboot, Nested virtualization |
| **D7: Oracle** | What counts as a bug? | Crash/hang, Sanitizers, Invariant violation, Differential divergence |

---

## Design Trade-offs

Four fundamental trade-offs govern hypervisor testing tool design:

### Trade-off 1: Generality vs. Depth
- **Universal fuzzers** (HyperPill): Work across multiple hypervisors but achieve shallower testing
- **Specialized fuzzers** (V-Shuttle, HyperFuzzer): Achieve deeper testing through target-specific optimizations
- **Principle**: *Start broad, go deep* - use universal approaches for initial assessment, then specialize

### Trade-off 2: Structure vs. Speed
- **Richer input models** (grammar-based, driver-derived): More valid inputs but higher generation overhead
- **Simpler models** (raw bytes): Higher throughput but more invalid inputs rejected by parsers
- **Principle**: *Match input complexity to protocol complexity*

### Trade-off 3: Observability vs. Deployability
- **Maximum observability** (emulation-based): 10-100x overhead but universal support
- **Hardware tracing** (Intel PT): <5% overhead but requires specific hardware
- **Principle**: *Use minimum sufficient instrumentation*

### Trade-off 4: Reset Fidelity vs. Throughput
- **Fork-based** (Morphuzz, ViDeZZo): Sub-millisecond reset but only user-space state
- **Snapshot-based** (NYX): 1-10ms reset with full VM state isolation
- **Principle**: *Isolate what matters* - fork for device fuzzing, snapshot for cross-device testing

---

## Open Challenges

| Challenge | Current Limitation | Potential Approach |
|-----------|-------------------|-------------------|
| **State Space Explosion** | Exponential growth in device states | Abstract interpretation, state hashing |
| **Semantic Validity** | Manual specification effort doesn't scale | LLM-assisted inference, driver analysis |
| **Coverage Noise** | Non-deterministic signals from interrupts/timers | Statistical filtering, deterministic replay |
| **Cross-Platform Portability** | Architecture-specific tools (x86-centric) | Hardware interface abstraction |
| **Scalable Triage** | Manual crash analysis at scale | Automated root cause clustering |
| **Emerging Architectures** | Limited ARM/RISC-V support | ARM CoreSight, portable frameworks |

### Research Gaps by Attack Surface

| Attack Surface | Papers | Gap Analysis |
|----------------|--------|--------------|
| Virtual Devices | 12 (71%) | Well-studied but complex protocols (NVMe, virtio-gpu) underexplored |
| vCPU Emulation | 2 (12%) | **Severely underexplored** - extension instruction sets (AVX-512, SGX) untested |
| Hypercalls/VM-Exit | 2 (12%) | **Severely underexplored** - systematic hypercall sequence testing missing |
| Core Subsystems | 0 (0%) | **Completely unexplored** - MMU virtualization, scheduling, IOMMU |

---

## Evaluation Guidelines

### Common Pitfalls (from our survey analysis)

| Pitfall | Prevalence | Recommendation |
|---------|------------|----------------|
| Throughput without coverage context | 41% | Report effective coverage rate alongside throughput |
| Device count without complexity classification | 53% | Classify devices by complexity (simple/medium/complex) |
| CVE count without severity/deduplication | 65% | Report bugs with root cause and CVSS severity |
| Snapshot configuration details omitted | 47% | Specify guest memory, timing, enabled devices |
| Non-standardized time budgets | 59% | Use 1h for quick comparison, 24h for thorough evaluation |
| Missing or inadequate baselines | 35% | Compare against at least one prior tool |

### Recommended Reporting Checklist

| Category | Required Information |
|----------|---------------------|
| **Target** | Hypervisor name/version; device list with complexity; commit hash |
| **Configuration** | Guest memory size; snapshot timing; enabled devices; instrumentation flags |
| **Metrics** | Edge coverage over time; throughput with context; per-device breakdown |
| **Bugs** | Deduplication method; root cause classification; severity (CVSS) |
| **Reproducibility** | Seeds and configurations; Docker/VM image; expected coverage range |
| **Baselines** | At least one prior tool on same targets/budget |
| **Statistics** | Multiple runs (>=5); mean and variance; significance tests |

---

## Contributing

Contributions are welcome:

* Adding new papers
* Updating paper information (links, findings)
* Suggesting improvements to categorization


## License

This documentation is licensed under [CC BY-NC 4.0](LICENSE). Individual papers retain their original copyrights.
