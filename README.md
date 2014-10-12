Read Me First
==============


How to build UnityROM-2 for Jewel ( HTC Evo 4g LTE )

You do not need to have the device to do it this way.

FIRST RUN ONLY (everything up to dash marks)

Install your Linux Distro ( Ubuntu 14.04.1 LTS x64 for me.)

Setup Build Environment

REMEMBER: CHANGE THE GIT CONFIG TO YOUR INFO FIRST!!! (IF YOU USE SCRIPTS FOR THIS, DO THE SAME TO "CMRepoSetup.sh" BEFORE USING IT OR "EnvironmentSetup.sh")

sudo apt-get install git gnupg flex bison gperf build-essential zip curl libc6-dev libncurses5-dev:i386 x11proto-core-dev libx11-dev:i386 libreadline6-dev:i386 libgl1-mesa-glx:i386 libgl1-mesa-dev g++-multilib mingw32 tofrodos python-markdown libxml2-utils xsltproc zlib1g-dev:i386 bison build-essential curl flex git gnupg gperf libesd0-dev libncurses5-dev libsdl1.2-dev libwxgtk2.8-dev libxml2 libxml2-utils lzop openjdk-7-jdk phablet-tools pngcrush schedtool squashfs-tools xsltproc zip zlib1g-dev g++-multilib gcc-multilib lib32ncurses5-dev lib32readline-gplv2-dev lib32z1-dev && mkdir ~/bin && PATH=~/bin:$PATH && mkdir -p ~/android/system && curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo && chmod a+x ~/bin/repo && git config --global user.email "you@email.com" && git config --global user.name "YourName" && cd ~/android/system && repo init -u git://github.com/LiquidSmokeX64/UnityROM-2-REPO.git -b master

Run initial sync

cd ~/android/system && repo sync

----------------------------------------------------------------------------------------------------
UnityROM 2.5.8 Conversion... This WILL take a minute or two...

cd && cd ~/android/system/build/ && git fetch https://github.com/LiquidSmokeX64/android_build cm-11.0 && git cherry-pick 71c8b8c0c93e25b9c5400a7d3b5119cdd5eec2c0 && cd ~/android/system/device/htc/jewel/ && git fetch https://github.com/LiquidSmokeX64/android_device_htc_jewel cm-11.0 && git cherry-pick 667f6db6f3892f50584439eb5980029b184ea3d9 && cd ~/android/system/device/htc/m7-common && git fetch https://github.com/LiquidSmokeX64/android_device_htc_m7-common cm-11.0 && git cherry-pick 2a8b684d49e45817a2fcfb38275d2f541fa5ae04 && cd ~/android/system/device/htc/m7spr/ && git fetch https://github.com/LiquidSmokeX64/android_device_htc_m7spr cm-11.0 && git cherry-pick 46e53a71ef4b292e2a22fd15e6f0840f1a11d09c && cd ~/android/system/device/htc/s4-common/ && git fetch https://github.com/LiquidSmokeX64/android_device_htc_s4-common cm-11.0 && git cherry-pick 2c056a81fe727350563c62e3acc8d758f0e3b08c && cd ~/android/system/external/bash/ && git fetch https://github.com/LiquidSmokeX64/android_external_bash cm-11.0 && git cherry-pick e9c4906f149a2b87c0acc5b43f2aaabe3163587d && cd ~/android/system/system/vold/ && git fetch https://github.com/LiquidSmokeX64/android_system_vold cm-11.0 && git cherry-pick bb288fb00f63b2c37038f8cf07d59143a30120b6 && cd ~/android/system/kernel/htc/msm8960/ && git fetch https://github.com/LiquidSmokeX64/android_kernel_htc_msm8960 cm-11.0 && git cherry-pick ffe3def1b2b466bf77179f0837aa96e90412501d && cd ~/android/system/external/oprofile/ && git fetch https://github.com/LiquidSmokeX64/android_external_oprofile cm-11.0 && git cherry-pick cfc8c2d0ed64d141ed7d39d7f3a6b9ad9366e941 && cd ~/android/system/vendor/cm/ && git fetch https://github.com/LiquidSmokeX64/android_vendor_cm cm-11.0 && git cherry-pick 29140dc6cef539f90d6c28338b0891eff68023d7 && cd ~/android/system/external/e2fsprogs/ && git fetch https://github.com/LiquidSmokeX64/android_external_e2fsprogs tachyon-2.0 && git cherry-pick 75088ae111d6c09fb1a5fdf2eccacbeb54d1b76c && cd ~/android/system/bionic/ && git fetch https://github.com/LiquidSmokeX64/android_bionic tachyon-2.0 && git cherry-pick f071fb6eef62cc4928d0521460599fab04b9969f && cd ~/android/system/dalvik/ && git fetch https://github.com/LiquidSmokeX64/android_dalvik tachyon-2.0 && git cherry-pick fe1966fabfc44b18a14850d04f97512a2d602843 && cd ~/android/system/external/stlport/ && git fetch https://github.com/LiquidSmokeX64/android_external_stlport tachyon-2.0 && git cherry-pick f164acdbbbdfef50bf0aa374607b56d243a18938 && cd ~/android/system/external/clang/ && git fetch https://github.com/LiquidSmokeX64/android_external_clang tachyon-2.0 && git cherry-pick e41d99927139ba9afd3c76ebbaac9cd582396424 && cd ~/android/system/external/dnsmasq/ && git fetch https://github.com/LiquidSmokeX64/android_external_dnsmasq tachyon-2.0 && git cherry-pick 50676d05317cc2b0cdbe6f24ddb991c53483fd57 && cd ~/android/system/frameworks/compile/slang/ && git fetch https://github.com/LiquidSmokeX64/android_frameworks_compile_slang tachyon-2.0 && git cherry-pick 01cd0efe7e9da2e4b91ac76f3da0281f9245b30b && cd ~/android/system/external/iputils/ && git fetch https://github.com/LiquidSmokeX64/android_external_iputils tachyon-2.0 && git cherry-pick 87c334c3fb0fac0ee92be50c24563f612b70973d && cd ~/android/system/external/openssh/ && git fetch https://github.com/LiquidSmokeX64/android_external_openssh tachyon-2.0 && git cherry-pick 7a152c43552233bbf611c206c611e62a39b17656 && cd ~/android/system/frameworks/rs/ && git fetch https://github.com/LiquidSmokeX64/android_frameworks_rs tachyon-2.0 && git cherry-pick c54f191fddec7089b8c8eb1b66d38a10f75c4eb5 && cd ~/android/system/frameworks/native/ && git fetch https://github.com/LiquidSmokeX64/android_frameworks_native tachyon-2.0 && git cherry-pick 9570c494e5b18afd670542d90b8c85cb8e347aa4 && cd ~/android/system/device/generic/goldfish/ && git fetch https://github.com/LiquidSmokeX64/android_device_generic_goldfish tachyon-2.0 && git cherry-pick fa6c45a973752922be36de28cfe526e7b8a3af03 && cd ~/android/system/libcore/ && git fetch https://github.com/LiquidSmokeX64/android_libcore tachyon-2.0 && git cherry-pick c8e1d82487c016b3e13b1d3b7d1f3fef84784219 && cd ~/android/system/frameworks/opt/net/voip/ && git fetch https://github.com/LiquidSmokeX64/android_frameworks_opt_net_voip tachyon-2.0 && git cherry-pick 9c2ce1fc56ad08ee0b3c8279d257b5c5ded7be32 && cd ~/android/system/frameworks/wilhelm/ && git fetch https://github.com/LiquidSmokeX64/android_frameworks_wilhelm tachyon-2.0 && git cherry-pick ef9ec68e2011b9f4290c27f90082ddf218866625 && cd ~/android/system/hardware/qcom/gps/ && git fetch https://github.com/LiquidSmokeX64/android_hardware_qcom_gps tachyon-2.0 && git cherry-pick 4bf8441c46cddcdc9f604d1a012166e05530744c && cd ~/android/system/external/lsof/ && git fetch https://github.com/LiquidSmokeX64/android_external_lsof tachyon-2.0 && git cherry-pick 44e30c310ed2f0c0ac4e8488fd37d51f91f933bf && cd ~/android/system/external/chromium/ && git fetch https://github.com/LiquidSmokeX64/android_external_chromium tachyon-2.0 && git cherry-pick 6dae14a200d444fc7e834bc2369437d37851d376 && cd ~/android/system/frameworks/ex/ && git fetch https://github.com/LiquidSmokeX64/android_frameworks_ex tachyon-2.0 && git cherry-pick a59bcbaa97ad8d62bd2e5d06d25f411c4aa06253 && cd ~/android/system/build/ && git fetch https://github.com/LiquidSmokeX64/android_build cm-11.0 && git cherry-pick 182559bc9559762b784319c2976381532c51d49b && cd ~/android/system/frameworks/base/ && git fetch https://github.com/LiquidSmokeX64/android_frameworks_base cm-11.0 && git cherry-pick 99c4ea1c5b3c8cbf1672e7906a31e4f8b6df6dca && cd ~/android/system/hardware/qcom/audio-caf/ && git fetch https://github.com/LiquidSmokeX64/android_hardware_qcom_audio-caf cm-11.0 && git cherry-pick 558eb083ad41f652d242056d2592057005ef611f && cd ~/android/system/packages/apps/DSPManager/ && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_DSPManager cm-11.0 && git cherry-pick f2fb4dc8ed6c09826a96f7faf80d8df3fcdc34e7 && cd ~/android/system/vendor/cm/ && git fetch https://github.com/LiquidSmokeX64/android_vendor_cm cm-11.0 && git cherry-pick 103048363f6a377e9836ef8351fa249412429fcf && cd ~/android/system/kernel/htc/msm8960/ && git fetch https://github.com/LiquidSmokeX64/android_kernel_htc_msm8960 cm-11.0 && git cherry-pick 3af8b117cbb281eb6446cc38b1a66544d315ea38 && cd ~/android/system/vendor/cm/ && git fetch https://github.com/LiquidSmokeX64/android_vendor_cm cm-11.0 && git cherry-pick edd47cf7560e7206bfcfda452877d5524f23e11b && cd ~/android/system/build/ && git fetch https://github.com/LiquidSmokeX64/android_build cm-11.0 && git cherry-pick 8c04b15e56aaed75342a740a8795062a583810b3 && cd ~/android/system/frameworks/av/ && git fetch https://github.com/LiquidSmokeX64/android_frameworks_av cm-11.0 && git cherry-pick 572c32c467de58b8ca4218d245e88e7530956b3c && cd ~/android/system/frameworks/av/ && git fetch https://github.com/LiquidSmokeX64/android_frameworks_av cm-11.0 && git cherry-pick c00fb0094985d0986b21fa8ff87303e412429198 && cd ~/android/system/frameworks/av/ && git fetch https://github.com/LiquidSmokeX64/android_frameworks_av cm-11.0 && git cherry-pick 304c6c5e351e98e8d871bb949f6d996663357375 && cd ~/android/system/frameworks/av/ && git fetch https://github.com/LiquidSmokeX64/android_frameworks_av cm-11.0 && git cherry-pick 42ec24cc377b9f1b3d90be3a31b880e49fe484b5 && cd ~/android/system/frameworks/av/ && git fetch https://github.com/LiquidSmokeX64/android_frameworks_av cm-11.0 && git cherry-pick 84ec68a6f5c12c253aadc122844f81a6bd650d3a && cd ~/android/system/hardware/qcom/media-caf/ && git fetch https://github.com/LiquidSmokeX64/android_hardware_qcom_media-caf cm-11.0 && git cherry-pick 31600f987663979f69067001e46c41dc5e686f96 && cd ~/android/system/hardware/qcom/media-caf/ && git fetch https://github.com/LiquidSmokeX64/android_hardware_qcom_media-caf cm-11.0 && git cherry-pick b93ebe4fe18f583bd54e88c0f3c77aee9fa4920f && cd ~/android/system/hardware/qcom/media-caf/ && git fetch https://github.com/LiquidSmokeX64/android_hardware_qcom_media-caf cm-11.0 && git cherry-pick 6611cef335b378b6647cdedf2f33c56121f9a305 && cd ~/android/system/kernel/htc/msm8960/ && git fetch https://github.com/LiquidSmokeX64/android_kernel_htc_msm8960 cm-11.0 && git cherry-pick 9e63ef4bb111396528e01cb4aebc2512b68d86ba && cd ~/android/system/kernel/htc/msm8960/ && git fetch https://github.com/LiquidSmokeX64/android_kernel_htc_msm8960 cm-11.0 && git cherry-pick 2e0e4af4cfa3e331dfec49320346e9a2669a457c && cd ~/android/system/external/koush/Superuser/ && git fetch https://github.com/LiquidSmokeX64/Superuser cm-11.0 && git cherry-pick 34afa8d1f993e2cc56fba6aa7f8437ffdab03616 && cd ~/android/system/packages/apps/Settings/ && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Settings cm-11.0 && git cherry-pick d4b59e6544dc636efab79d9368f4f49e27c48065 && cd ~/android/system/vendor/cm/ && git fetch https://github.com/LiquidSmokeX64/android_vendor_cm cm-11.0 && git cherry-pick e4e83f34a229da164f9474b3bd94c2551d10edff && cd ~/android/system/kernel/htc/msm8960/ && git fetch https://github.com/LiquidSmokeX64/android_kernel_htc_msm8960 cm-11.0 && git cherry-pick d9b2eb396c641d47b355903513657672180dafaa && cd ~/android/system/kernel/htc/msm8960/ && git fetch https://github.com/LiquidSmokeX64/android_kernel_htc_msm8960 cm-11.0 && git cherry-pick 087b273dcf88325291b11c95f730931b79672ae1 && cd ~/android/system/kernel/htc/msm8960/ && git fetch https://github.com/LiquidSmokeX64/android_kernel_htc_msm8960 cm-11.0 && git cherry-pick f461040264b76e0cf84fefcd663f5ab424f6a84e && cd ~/android/system/kernel/htc/msm8960/ && git fetch https://github.com/LiquidSmokeX64/android_kernel_htc_msm8960 cm-11.0 && git cherry-pick 1b1a6bd3ee2549db23c1b4283e5ce5fdc2f0ccbc && cd ~/android/system/kernel/htc/msm8960/ && git fetch https://github.com/LiquidSmokeX64/android_kernel_htc_msm8960 cm-11.0 && git cherry-pick 55049ded277ae2a741a2739c86a177c4d9d4d4d8 && cd ~/android/system/kernel/htc/msm8960/ && git fetch https://github.com/LiquidSmokeX64/android_kernel_htc_msm8960 cm-11.0 && git cherry-pick b3689e4a9894cd1bd01ba651d1697a218780f84b && cd ~/android/system/kernel/htc/msm8960/ && git fetch https://github.com/LiquidSmokeX64/android_kernel_htc_msm8960 cm-11.0 && git cherry-pick 02381befa7e034fcc57f6c52110b14b603faba73 && cd ~/android/system/vendor/cm/ && git fetch https://github.com/LiquidSmokeX64/android_vendor_cm cm-11.0 && git cherry-pick 5c49ea3e276e95faeb8b5e1f9f8b3196561472cf && cd ~/android/system/build/ && git fetch https://github.com/LiquidSmokeX64/android_build cm-11.0 && git cherry-pick 4c746bbbb308d46eca24298c3fb484c5fc9532f7 && cd ~/android/system/build/ && git fetch https://github.com/LiquidSmokeX64/android_build cm-11.0 && git cherry-pick 22697112c03ccf12f65e1174ea1a322885593dc5 && cd ~/android/system/kernel/htc/msm8960/ && git fetch https://github.com/LiquidSmokeX64/android_kernel_htc_msm8960 cm-11.0 && git cherry-pick cec598cc3e9ccc8f83b7c3fcf4804cec9bc5c571 && cd ~/android/system/kernel/htc/msm8960/ && git fetch https://github.com/LiquidSmokeX64/android_kernel_htc_msm8960 cm-11.0 && git cherry-pick 4d659962d32cc4f285b51882be1b182b54258b00 && cd ~/android/system/vendor/cm/ && git fetch https://github.com/LiquidSmokeX64/android_vendor_cm cm-11.0 && git cherry-pick abf62527f43aa0a4230c2cd53398ae36fdcd25dc && cd



Build ROM NOW

cd ~/android/system/vendor/cm && ./get-prebuilts && cd ~/android/system && repo sync && source build/envsetup.sh && breakfast jewel && croot && brunch jewel

Note: In some cases if you attempt to build for a device you do not have all dependencies set in roomservice.xml, it will notice this and attempt to download them automatically. 

If you want to add my personal commits for UnityROM Conversion to your build you will need the additional cherrypick commands before building but after RepoSync.

THAT'S IT!

If you choose to use my build scripts instead. place them all in your Home folder, open a terminal, then "chmod 755 SetPerms.sh". Then Run SetPerms.sh to set the executable permissions on all the rest of the sripts automatically.

Some scripts are linked to each other to create a single command for multiple things.

The Main ones you will call on (though you still need the rest) are EnvironmentSetup.sh, RepoSync.sh, Cleanup.sh, GetCommits.sh, and BuildCM-jewel.sh. 

ENJOY.

