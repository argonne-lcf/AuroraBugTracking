
### Open Issues

| Internal ID | Description | Vendor ID | Reproducer Path | PoC | Status | Priority | ETA | Date Opened | Last Updated |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| [25](https://github.com/argonne-lcf/AuroraBugTracking/issues/25) | Compile fail in Lattice App | Brian reproduced and confirms fixed in 2025.1 | /lus/flare/projects/Aurora_deployment/applications.hpc.argonne-national-lab.aurora.anl-testing/source/reproducers/dpcpp/bug_cgpt_icpx | Xiao-Yong Jin | Open | 🚨 | Brian confirms fixed in 2025.1 | 2025-05-01 | 2025-05-02 |
| [24](https://github.com/argonne-lcf/AuroraBugTracking/issues/24) | Noticeably more "ping failed" than before the 2025.1 SDK + 1099.12 UMD/KMD upgrade |  |  |  |  |  |  | 2025-05-01 | 2025-05-01 |
| [23](https://github.com/argonne-lcf/AuroraBugTracking/issues/23) | Apps stop running after Apr 29 upgrade due to libstdc++ dependency | _No response_ | See details | Ye Luo | Open |  | _No response_ | 2025-04-30 | 2025-05-02 |
| [22](https://github.com/argonne-lcf/AuroraBugTracking/issues/22) | SYCL In-order queue broken | NEO-14641 | /lus/flare/projects/Aurora_deployment/applications.hpc.argonne-national-lab.aurora.anl-testing/source/reproducers/dpcpp/in-order | Thomas Applencourt | Open (WA available) |  | _No response_ | 2025-04-23 | 2025-04-25 |
| [20](https://github.com/argonne-lcf/AuroraBugTracking/issues/20) | Issue with gpu-bind for mpiexec under ZE_FLAT_DEVICE_HIERARCHY=FLAT mode | _No response_ | See below | Abhishek, Nathan, Khalid | Open |  | _No response_ | 2025-04-16 | 2025-04-23 |
| [19](https://github.com/argonne-lcf/AuroraBugTracking/issues/19) | Severe CPU memory growth in MPICH | _No response_ | /flare/catalyst/world_shared/zippy/reproducers/issue19 | Tim Williams | Open |  | _No response_ | 2025-04-04 | 2025-04-24 |
| [18](https://github.com/argonne-lcf/AuroraBugTracking/issues/18) | Ping failures and hangs with production runs using GPT/GRID | ANL-251, RITM0404147, RITM0404148, RITM0405730 | /lus/flare/projects/LatticeFlavor/lehner | Xiao-Yong Jin | Open |  | _No response_ | 2025-04-04 | 2025-04-18 |
| [17](https://github.com/argonne-lcf/AuroraBugTracking/issues/17) | hang with MPI pipelining | https://github.com/pmodels/mpich/issues/7373 | Build and run commands are in the MPICH issue. | James Osborn | Open (WA available) |  | _No response_ | 2025-04-03 | 2025-04-08 |
| [16](https://github.com/argonne-lcf/AuroraBugTracking/issues/16) | Catastrophic memory error in context lmp_aurora_kokkos | _No response_ | public LAMMPS | Chris Knight | Open |  | N/A | 2025-04-03 | 2025-04-03 |
| [13](https://github.com/argonne-lcf/AuroraBugTracking/issues/13) | XGC hangs at scale | _No response_ | xgc-es-cpp-gpu app, ES_ITER test case | Tim Williams | Open | 🚨 | _No response_ | 2025-04-03 | 2025-04-03 |
| [12](https://github.com/argonne-lcf/AuroraBugTracking/issues/12) | CXI alloc failed on cxi1: request exceeds ACs limits | _No response_ | None | Not Thomas | Open |  | _No response_ | 2025-04-01 | 2025-04-07 |
| [9](https://github.com/argonne-lcf/AuroraBugTracking/issues/9) | Multithreaded data-transfer can cause page-fault | N/A | Full QMCPACK | Ye Luo | Open (WA available) |  | _No response_ | 2025-04-01 | 2025-04-03 |
| [8](https://github.com/argonne-lcf/AuroraBugTracking/issues/8) | Lots of H2D copies produce CPU I9 error and incorrect value | N/A | Full QMCPACK | Ye Luo | Open | 🚨 | ? | 2025-04-01 | 2025-04-24 |

### Closed Issues

| Internal ID | Description | Vendor ID | Reproducer Path | PoC | Status | Priority | Date Opened | Closed Date |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| [21](https://github.com/argonne-lcf/AuroraBugTracking/issues/21) | Error during write with Quantum ESPRESSO | _No response_ | see .zip file attached below, also /lus/flare/projects/matml_aesp_CNDA/dir_io_QE_crash | Filippo Simini | Open | 🚨 | 2025-04-17 | 2025-04-18 |
| [7](https://github.com/argonne-lcf/AuroraBugTracking/issues/7) | MPI_Bcast gets faster when turning off XPMEM | [pmodels/mpich#7334](https://github.com/pmodels/mpich/issues/7334) | see Issue on MPICH GitHub repo | Ye Luo | Open (WA available) |  | 2025-04-01 | 2025-04-24 |
| [6](https://github.com/argonne-lcf/AuroraBugTracking/issues/6) | MPICH memory allocation slows down at scale | [pmodels/mpich#7333](https://github.com/pmodels/mpich/issues/7333) | see MPICH issue | Ye Luo | Open (WA available) | 🚨 | 2025-04-01 | 2025-04-24 |
| [4](https://github.com/argonne-lcf/AuroraBugTracking/issues/4) | Incorrect results in receive buffer in GPU memory | [MPICH 7312](https://github.com/pmodels/mpich/pull/7312) | grid application (lattice QCD) | Patrick Steinbrecher, Tim Williams | Open (WA available) | 🚨 | 2025-03-25 | 2025-04-24 |
| [3](https://github.com/argonne-lcf/AuroraBugTracking/issues/3) | Linker error found by XGC | CMPLRLLVM-66496 | /home/zippy/smalltests/aurora/xgc42/fails | Tim Williams | Closed (Application source code bug) |  | 2025-03-19 | 2025-03-28 |
