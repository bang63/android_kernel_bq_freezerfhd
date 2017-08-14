WHAT IS THIS?
=============

Linux Kernel source code for the devices:
* bq aquaris M10 FHD


BUILD INSTRUCTIONS?
===================

Specific sources are separated by branches and each version is tagged with it's corresponding number. First, you should
clone the project:

        $ git clone https://github.com/bang63/android_kernel_bq_freezerfhd.git

After it, choose the version you would like to build:

* Aquaris M10 FHD *

        $ mv android_kernel_bq_freezerfhd
        $ cd kernel
        $ git checkout cm-13.0

At the same level of the "kernel" directory:

Download a prebuilt gcc:

        $ git clone https://android.googlesource.com/platform/prebuilts/gcc/linux-x86/aarch64/aarch64-linux-android-4.9 -b marshmallow-release 

Create KERNEL_OUT dir:

        $ mkdir KERNEL_OUT   

Your directory tree should look like this:
* kernel
* aarch64-linux-android-4.9
* KERNEL_OUT

Finally, build the kernel according the next table of product names:

| device                    | product                 |
| --------------------------|-------------------------|
| bq aquaris M10 FHD        | freezerfhd              |


        $ make -C kernel  O=../KERNEL_OUT  ARCH=arm64 CROSS_COMPILE=../aarch64-linux-android-4.9/bin/aarch64-linux-android- {product}_defconfig
        $ make O=../KERNEL_OUT/ -C kernel ARCH=arm64  CROSS_COMPILE=../aarch64-linux-android-4.9/bin/aarch64-linux-android-                      
    
You can specify "-j CORES" argument to speed-up your compilation, example:

        $ make O=../KERNEL_OUT/ -C kernel ARCH=arm64  CROSS_COMPILE=../aarch64-linux-android-4.9/bin/aarch64-linux-android- -j 8

