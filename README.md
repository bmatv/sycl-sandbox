# sycl-sandbox
Initial experimentation and notes on sycl and oneAPI

## Installing on Arch

Installing from Extra's `intel-oneapi-dpcpp-cpp` will require `onnxruntime` which is a version mismatch from what is expected by dpcpp, so best to go with AUR bundle or get from Intel's website.
```
yay -S intel-oneapi-basekit
```
and source the setvars script to setup the environment:
```
source /opt/intel/oneapi/setvars.sh
```

This will only pick up FPGA and CPU. To get the GPU, one needs to install

Intel's oneAPI and openCL driver for GPU:
```
sudo pacman -S intel-compute-runtime
```

## Testing
Calling `sycl-ls` should produce something similar to:
```
[level_zero:gpu][level_zero:0] Intel(R) oneAPI Unified Runtime over Level-Zero, Intel(R) Arc(TM) Graphics 12.71.4 [1.6.34303]
[opencl:fpga][opencl:0] Intel(R) FPGA Emulation Platform for OpenCL(TM), Intel(R) FPGA Emulation Device OpenCL 1.2  [2024.18.12.0.05_160000]
[opencl:cpu][opencl:1] Intel(R) OpenCL, Intel(R) Core(TM) Ultra 7 165H OpenCL 3.0 (Build 0) [2024.18.12.0.05_160000]
[opencl:gpu][opencl:2] Intel(R) OpenCL Graphics, Intel(R) Arc(TM) Graphics OpenCL 3.0 NEO  [25.27.34303]
```
