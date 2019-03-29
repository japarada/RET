# Welcome to RET (ROCm Enablement Tool)

RET is a comprehensive checking, set up, installation, testing and benchmarking tool which does carry out the installation of ROCm suite ranging from dependencies, drivers and toolchain to framework and benchmark. 
RET makes the process of carrying out automated ROCm installation incredibly simple and provides a more user friendly and faster installation experience. 

* INSTALL OS
* RUN ret
* TRAIN your own model tensorflow OR run tensorflow benchmark

## Hardware Support and supported GPU
please refer to ROCm main repository
at [https://rocm.github.io/ROCmInstall.html](https://rocm.github.io/ROCmInstall.html).

# Getting started
## Supported OS
  - Ubuntu: 
      - 16.04
      - 18.04
  - RedHat # not yet
  - CentOS # not yet
## Prerequisites
Formatting a hard drive along with the install of a new OS is the best option
after the instllation you will need git to download the RET source
```
  sudo apt -y install git
```

**Note:** DO NOT update and upgrade your system

## Clone repository
```
   git clone https://github.com/rocmsys/RET.git
```
## Usage: 
```
sudo ./ret  <command\> <option>
```
* command:
  *           [install] <package>              : Install ROCm or ML Framework TF/PT
              [remove]  <package>              : Remove ROCm or ML Framework TF/PT
              [update]  <package>              : Update ROCm or ML Framework TF/PT
              [validate]                       : System validation
              [show]                           : Show system HW and SW details

   * packages:
     *            [rocm]                         : ROCm-dkms packages
                  [tensorflow]                : Tensorflow framework
                  [pytorch]                   : Pytorch framework

* Options:
  *            [-h|--help]                     : Show this help message
               [-v|--version]                  : Show version of this package
               [-V|--verbose]                  : Be verbose
               [-b|--benchmark]                : Run benchmark
               [-d|--dryrun]                   : Show what would be happened

## RUN RET:
```
   cd RET
   sudo ./ret install rocm  # to install only ROCm
   or 
   sudo ./ret install tf    # to install ROCm + Tensorflow
```

### Tensorflow's tf_cnn_benchmarks
Details on the tf_cnn_benchmarks can be found at this [link](https://github.com/tensorflow/benchmarks/blob/master/scripts/tf_cnn_benchmarks/README.md).  

Here are the basic instructions:
```
# Grab the repo
cd $HOME
git clone -b cnn_tf_v1.12_compatible https://github.com/tensorflow/benchmarks.git
cd benchmarks

# Run the training benchmark (e.g. ResNet-50)
python3 ./scripts/tf_cnn_benchmarks/tf_cnn_benchmarks.py --model=resnet50 --num_gpus=1 --batch_size=256 --num_batches=50 --use_fp16=True --datasets_use_prefetch=False --display_every=10

```
