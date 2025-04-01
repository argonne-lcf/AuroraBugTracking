| Internal ID |  Description | Vendor ID | Reproducer Path | PoC | Status | Priority | ETA
| --- | --- | --- | --- | --- | --- | --- |--- |
| [9](https://github.com/argonne-lcf/AuroraBugTracking/issues/9) | Multithreaded data-transfer can cause page-fault | N/A | Full QMCPACK | Ye Luo | Open--- WA available |  | _No response_ |
| [8](https://github.com/argonne-lcf/AuroraBugTracking/issues/8) | Lots of H2D copies produce CPU I9 error and incorrect value | N/A | Full QMCPACK | Ye Luo | Open |  | ? |
| [7](https://github.com/argonne-lcf/AuroraBugTracking/issues/7) | MPI_Bcast gets faster when turning off XPMEM | https://github.com/pmodels/mpich/issues/7334 | see Issue on MPICH GitHub repo | Ye Luo | Open--- WA available |  | _No response_ |
| [6](https://github.com/argonne-lcf/AuroraBugTracking/issues/6) | MPICH memory allocation slows down at scale | https://github.com/pmodels/mpich/issues/7333 | see MPICH issue | Ye Luo | Open--- WA available |  | _No response_ |
| [4](https://github.com/argonne-lcf/AuroraBugTracking/issues/4) | The default mpich module on Aurora can give incorrect results in GPU buffers passed through MPI calls. | [MPICH 7312](https://github.com/pmodels/mpich/pull/7312) | grid application (lattice QCD) | Patrick Steinbrecher, Tim Williams | Open -- WA available |  | _No response_ |
| [3](https://github.com/argonne-lcf/AuroraBugTracking/issues/3) | The linker fails to find the object code for a function declared and implemented in a different .cpp source file. | CMPLRLLVM-66496 | /home/zippy/smalltests/aurora/xgc42/fails | Tim Williams | Open -- WA available |  |  |
| [2](https://github.com/argonne-lcf/AuroraBugTracking/issues/2) |  |  |  |  |  |  |  |
| A0 | Memory allocation slows down at scale | https://github.com/pmodels/mpich/issues/7333 | In the issue | Ye Luo | Open -- WA available |
| A1 | Bcast gets faster when turning off XPMEM | https://github.com/pmodels/mpich/issues/7334 | In the issue | Ye Luo | Open -- WA available |
| A2 | Lot of H2D copy produce CPU I9 error and incorect value | None | Full QMCPACK | Ye Luo | Open |  X | 
| A3 | Multithreadaed Data-transfer can cause page-fault | None | Full QMCPACK | Ye Luo | Open -- WA available |  X | 

# More Info

## A0

- WA is `MPIR_CVAR_CH4_XPMEM_ENABLE=0` 

## A1

2 WA possible:
 - WA is `MPIR_CVAR_CH4_XPMEM_ENABLE=0`
 - The threshold for this optimization has been increased. (any other solution worked on?)

## A2

A new GPU framework is required. I have been available internally at Intel. ETA? WA is to use less OpenMP thread, so doing less copy.

## A3

WA is to use `zeMallocHost` and not regular `malloc`. (can also use the SYCL extension to register memory)
