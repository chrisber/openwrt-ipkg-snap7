Building snap7 from source

cd ./docker
- make shell
- cd openwrt
- make menuconfig
- select target x86
- select under libraries snap7
- save
- make package/snap7/install

Library should be build to build_dir/i386_...x86/snap-.../libsnap7.so
ipk package path ist bin/i386_...x86/snap-.../snap7.ipk

openwrt files: 
Menu config makefile :
<repository>/data/Makefile

Building standalone:
- copy <repository>/data to <openwrt>/package/snap7
- make menuconfig
- select target x86
- select under libraries snap7
- save
- make package/snap7/install