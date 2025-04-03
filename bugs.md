
### Open Issues

| Internal ID |  Description | Vendor ID | Reproducer Path | PoC | Status | Priority | ETA
| --- | --- | --- | --- | --- | --- | --- |--- |
| [13](https://github.com/argonne-lcf/AuroraBugTracking/issues/13) | Since ~20 Jan, unable to run even a single timestep of XGC at 4096 nodes. When it doesn't die from ping/RPC errors, it hangs. | _No response_ | xgc-es-cpp-gpu app, ES_ITER test case | Tim Williams | Open | 🚨 | _No response_ |
| [12](https://github.com/argonne-lcf/AuroraBugTracking/issues/12) | `CXI alloc failed on cxi0: request exceeds ACs limits` | _No response_ | None | Not Thomas | Open |  | _No response_ |
| [9](https://github.com/argonne-lcf/AuroraBugTracking/issues/9) | Multithreaded data-transfer can cause page-fault | N/A | Full QMCPACK | Ye Luo | Open--- WA available |  | _No response_ |
| [8](https://github.com/argonne-lcf/AuroraBugTracking/issues/8) | Lots of H2D copies produce CPU I9 error and incorrect value | N/A | Full QMCPACK | Ye Luo | Open | 🚨 | ? |
| [7](https://github.com/argonne-lcf/AuroraBugTracking/issues/7) | MPI_Bcast gets faster when turning off XPMEM | [pmodels/mpich#7334](https://github.com/pmodels/mpich/issues/7334) | see Issue on MPICH GitHub repo | Ye Luo | Open--- WA available |  | _No response_ |
| [6](https://github.com/argonne-lcf/AuroraBugTracking/issues/6) | MPICH memory allocation slows down at scale | [pmodels/mpich#7333](https://github.com/pmodels/mpich/issues/7333) | see MPICH issue | Ye Luo | Open--- WA available | 🚨 | _No response_ |
| [4](https://github.com/argonne-lcf/AuroraBugTracking/issues/4) | The default mpich module on Aurora can give incorrect results in GPU buffers passed through MPI calls. | [MPICH 7312](https://github.com/pmodels/mpich/pull/7312) | grid application (lattice QCD) | Patrick Steinbrecher, Tim Williams | Open -- WA available | 🚨 | _No response_ |

### Closed Issues

| Internal ID |  Description | Vendor ID | Reproducer Path | PoC | Status | Priority | ETA
| --- | --- | --- | --- | --- | --- | --- |--- |
| [3](https://github.com/argonne-lcf/AuroraBugTracking/issues/3) | The linker fails to find the object code for a function declared and implemented in a different .cpp source file. | CMPLRLLVM-66496 | /home/zippy/smalltests/aurora/xgc42/fails | Tim Williams | Closed -- Application source code bug |  |  |
