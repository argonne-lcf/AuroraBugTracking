| Internal ID |  Description | Vendor ID | Reproducer Path | PoC | Status | Priority | ETA
| --- | --- | --- | --- | --- | --- | --- |--- |
| [5](https://github.com/argonne-lcf/AuroraBugTracking-test/issues/5) | yes | _No response_ | /dev/null | kgf | Closed? | medium | _No response_ |
| [4](https://github.com/argonne-lcf/AuroraBugTracking-test/issues/4) | Aurora nodes randomly disappear, reappearing in adjacent racks due to quantum tunneling. | _No response_ | /home/schrodinger/box_experiments/x4702c6s3b0n0 | Erwin Schrödinger | Open — Workaround: Observe harder | medium | _No response_ |
| [3](https://github.com/argonne-lcf/AuroraBugTracking-test/issues/3) | Aurora achieved sentience and refuses to compile Fortran. | _No response_ | /home/hal/open_the_pod_bay_doors | HAL 9000 | Open — Self-aware, refuses debugging | high | _No response_ |
| [2](https://github.com/argonne-lcf/AuroraBugTracking-test/issues/2) | no thanks | e.g. test https://github.com/argonne-lcf/user-guides and [internal link](https://github.com/argonne-lcf/user-guides) | this is not a path: https://github.com/argonne-lcf/user-guides | Tim Williams | Workaround Available | low | _No response_ |
| [1](https://github.com/argonne-lcf/AuroraBugTracking-test/issues/1) | I crashed the machien | not sure | /home/etc | kyle | Open | medium | two years from now |
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
