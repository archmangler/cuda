# CUDA Development Notes on NVIDA JETSON NANO

```
traiano@prometheus:~$ nvcc --version
nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2021 NVIDIA Corporation
Built on Sun_Feb_28_22:34:44_PST_2021
Cuda compilation tools, release 10.2, V10.2.300
Build cuda_10.2_r440.TC440_70.29663091_0
```


# Hardware details

* CPU

```
traiano@prometheus:~$ lscpu
Architecture:         aarch64
Byte Order:           Little Endian
CPU(s):               4
On-line CPU(s) list:  0,1
Off-line CPU(s) list: 2,3
Thread(s) per core:   1
Core(s) per socket:   2
Socket(s):            1
Vendor ID:            ARM
Model:                1
Model name:           Cortex-A57
Stepping:             r1p1
CPU max MHz:          1479,0000
CPU min MHz:          102,0000
BogoMIPS:             38.40
L1d cache:            32K
L1i cache:            48K
L2 cache:             2048K
Flags:                fp asimd evtstrm aes pmull sha1 sha2 crc32
```

* Graphics GPU:

```
traiano@prometheus:~$ dmesg | egrep -i gpu
[    0.212376] Tegra: CPU Speedo ID 9, SoC Speedo ID 0, GPU Speedo ID 2
[    0.212380] Tegra: CPU Process ID 0, SoC Process ID 0, GPU Process ID 0
[    0.212386] Tegra: CPU Speedo Value 2046, SoC Speedo Value 1918, GPU Speedo Value 2036
[    0.212390] Tegra: CPU IDDQ Value 1868, SoC IDDQ Value 2024, GPU IDDQ Value 2470
[    0.455951] iommu: Adding device 57000000.gpu to group 23
[    0.456004] platform 57000000.gpu: domain=ffffffc0f9508c18 allocates as[0]=ffffffc0f9430318
[    0.456042] platform 57000000.gpu: domain=ffffffc0f9508c18 allocates as[1]=ffffffc0f9430380
[    0.456086] platform 57000000.gpu: domain=ffffffc0f9508c18 allocates as[2]=ffffffc0f94303e8
[    0.456145] platform 57000000.gpu: domain=ffffffc0f9508c18 allocates as[3]=ffffffc0f9430450
[    0.691999] thermal thermal_zone2: Registering thermal zone thermal_zone2 for type GPU-therm
[    1.111387] vdd-gpu: applied init 1000000uV constraint
[    1.111397] vdd-gpu: 708 <--> 1323 mV at 997 mV 
[    1.390395] tegra_soctherm 700e2000.soctherm: thermtrip: will shut down when gpu reaches 103000 mC
[    1.390401] tegra_soctherm 700e2000.soctherm: throttrip: will throttle when gpu reaches 101000 mC
[    1.394178] parse_throttle_dt_data: clk=gpu type=4
[    1.514666] tegra_dvfs: GPU-cap: registered
[    1.514727] tegra dvfs: vdd-gpu: nominal 1068mV, offset 708000uV, step 10000uV, scaling enabled
[    1.516196] tegra_dvfs: vdd-gpu-vts: registered
[    2.545052] nvgpu: 57000000.gpu           gm20b_init_clk_setup_sw:1268 [INFO]  GPCPLL initial settings: NA mode, M=1, N=34, P=3 (id = 1)
[    3.873278] gpu-throttle-alert cooling device registered.


```



