WHAT IS THIS?
=============

Linux Kernel source code for the devices:
* bq aquaris X2 Pro


BUILD INSTRUCTIONS?
===================

Specific sources are separated by releases with it's corresponding number. First, you should
clone the project:

        $ git clone https://github.com/bq/aquaris-X2-Pro.git

After it, choose the release you would like to build:

*Aquaris X2 Pro*

        $ mv aquaris-X2-Pro kernel
        $ cd kernel
        $ git checkout tags/{release}
        $ cd ..

Download a prebuilt gcc:

        $ git clone https://android.googlesource.com/platform/prebuilts/gcc/linux-x86/aarch64/aarch64-linux-android-4.9

Create KERNEL_OUT dir:

        $ mkdir KERNEL_OUT

Your directory tree should look like this:
* kernel
* aarch64-linux-android-4.9
* KERNEL_OUT

Finally, build the kernel according the next table of product names:

| device                    | product                 |
| --------------------------|-------------------------|
| bq aquaris X2 Pro         | zangyapro               |


        $ make -C kernel O=../KERNEL_OUT ARCH=arm64 CROSS_COMPILE=../aarch64-linux-android-4.9 {product}_defconfig
        $ make O=../KERNEL_OUT/ -C kernel ARCH=arm64 CROSS_COMPILE=../aarch64-linux-android-4.9/bin/aarch64-linux-android-

You can specify "-j{CORES}" argument to speed-up your compilation, example:

        $ make O=../KERNEL_OUT/ -C kernel ARCH=arm64 CROSS_COMPILE=../aarch64-linux-android-4.9/bin/aarch64-linux-android- -j8
