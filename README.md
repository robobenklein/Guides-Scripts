Read Me First
==============

How to build UnityROM-3.2 for OnePlus One

Install your Linux Distro

Setup Build Environment

sudo apt-get install bison build-essential curl flex git gnupg gperf libesd0-dev liblz4-tool libncurses5-dev libsdl1.2-dev libwxgtk2.8-dev libxml2 libxml2-utils lzop openjdk-7-jdk openjdk-7-jre pngcrush schedtool squashfs-tools xsltproc zip zlib1g-dev g++-multilib gcc-multilib lib32ncurses5-dev lib32readline-gplv2-dev lib32z1-dev bison g++-multilib git gperf libxml2-utils make python-networkx zlib1g-dev:i386 zip vlc android-tools-adb android-tools-fastboot && sudo add-apt-repository ppa:webupd8team/java && sudo apt-get update && sudo apt-get install oracle-java7-installer && sudo update-java-alternatives -s java-7-oracle && sudo apt-get install oracle-java7-set-default && cd && mkdir ~/bin && PATH=~/bin:$PATH && mkdir -p ~/android/system && curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo && chmod a+x ~/bin/repo && cd ~/android/system

Setup CM Branch & get the roomservice.xml

git config --global user.email "your@email.com" && git config --global user.name "YourName" && cd ~/android/system && repo init -u git://github.com/CyanogenMod/android.git -b cm-12.1 && mkdir -p ~/android/system/.repo/local_manifests && curl -L -o .repo/local_manifests/roomservice.xml -O -L https://raw.github.com/LiquidSmokeX64/Guides-Scripts/master/roomservice.xml && cd ~/android/system

Sync up the CM Repo

cd ~/android/system && repo sync && cd ~/android/system

UR4 PreMerged Build Fixes...

cd ~/android/cm13/vendor/cm && git fetch http://review.cyanogenmod.org/CyanogenMod/android_vendor_cm refs/changes/36/111336/30 && git cherry-pick FETCH_HEAD && cd ~/android/cm13/device/oneplus/bacon && git fetch http://review.cyanogenmod.org/CyanogenMod/android_device_oneplus_bacon refs/changes/28/117928/1 && git cherry-pick FETCH_HEAD && cd ~/android/cm13/device/oppo/common && git fetch http://review.cyanogenmod.org/CyanogenMod/android_device_oppo_common refs/changes/54/111754/2 && git cherry-pick FETCH_HEAD && cd ~/android/cm13/frameworks/base && git fetch http://review.cyanogenmod.org/CyanogenMod/android_frameworks_base refs/changes/94/114594/1 && git cherry-pick FETCH_HEAD

UnityROM Primary System Commits..

cd ~/android/system/build/ && git fetch https://github.com/LiquidSmokeX64/android_build cm-12.1 && git cherry-pick ac579d70677a5a14ab0c353c0b5ce0ad35f52ae4 
cd ~/android/system/packages/apps/Settings && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Settings stable/cm-12.1-YOG7D && git cherry-pick 5e693f776e8e8fbb380db13f5615129e2bf069cd
cd ~/android/system/packages/apps/Settings && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Settings stable/cm-12.1-YOG7D && git cherry-pick 44d92e28defdfe5c68453e1758d247157b05f732
cd ~/android/system/packages/apps/Settings && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Settings stable/cm-12.1-YOG7D && git cherry-pick e36d5cc5b1e52f5fa6654d152995d62fc74246ac
cd ~/android/system/vendor/cm && git fetch https://github.com/LiquidSmokeX64/android_vendor_cm cm-12.1 && git cherry-pick 5d24ac0f83e1d0fc5171e89229074d3909f16bee
cd ~/android/system/vendor/cm && git fetch https://github.com/LiquidSmokeX64/android_vendor_cm cm-12.1 && git cherry-pick bd1f31942f8b3b4bda8f16694ba601b68c36f1a9
cd ~/android/system/system/core/ && git fetch https://github.com/LiquidSmokeX64/android_system_core cm-12.1 && git cherry-pick 71ac988dd5311eeea6b5d343344f6d752434aed2
cd ~/android/system/bionic/ && git fetch https://github.com/LiquidSmokeX64/android_bionic cm-12.1 && git cherry-pick 9b547c4ded74b015e6a283c5c6290c7d7271e00f
cd ~/android/system/frameworks/av/ && git fetch https://github.com/ResurrectionRemix-Devices/android_frameworks_av cm-12.1 && git cherry-pick 5e61bd3311f03222f8a690dc1d97729aba0f183b 
cd ~/android/system/frameworks/base && git fetch https://github.com/sultanxda/android_frameworks_base cm-12.1 && git cherry-pick 0cbd4a88767d78640b7dd391674575f7d5e517e6
cd ~/android/system/device/oneplus/bacon && git fetch https://github.com/LiquidSmokeX64/android_device_oneplus_bacon stable/cm-12.1-YOG7D && git cherry-pick 56d06d74bde004213c19151db34e822f7c71c429 
cd ~/android/system/device/oneplus/bacon && git fetch https://github.com/LiquidSmokeX64/android_device_oneplus_bacon stable/cm-12.1-YOG7D && git cherry-pick 926d71dd1e282eefd5bd79e2c27097c85d0914c7 
cd ~/android/system/packages/apps/Mms && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Mms-caf stable/cm-12.1-YOG7D && git cherry-pick ae1066039ca3e07dc4520d0fc482e801c5d775c0 
cd ~/android/system/packages/apps/Settings && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Settings stable/cm-12.1-YOG7D && git cherry-pick bd6a95ca49af69b6d9e02905c470d6c6792dfcce 
cd ~/android/system/packages/apps/PackageInstaller && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_PackageInstaller stable/cm-12.1-YOG7D && git cherry-pick a507aef9a853b74a10916856307149a2eb66af51 
cd ~/android/system/packages/apps/Gallery2 && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Gallery2 stable/cm-12.1-YOG7D && git cherry-pick c179f154bc1e4be8a7243c8c6f3ad9704efd17be 
cd ~/android/system/packages/apps/InCallUI && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_InCallUI stable/cm-12.1-YOG7D && git cherry-pick 60758f414a34121d5bc6de28b3a5a21930d2cc28 
cd ~/android/system/packages/apps/TvSettings && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_TvSettings stable/cm-12.1-YOG7D && git cherry-pick 55556fd611d5b3211367a1a66e10e4f56addd2b0 
cd ~/android/system/packages/apps/TvSettings && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_TvSettings stable/cm-12.1-YOG7D && git cherry-pick 39ab10d1a17c0599b8ae73808c1af2a3f2b17b78 
cd ~/android/system/packages/apps/ThemeChooser && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_ThemeChooser stable/cm-12.1-YOG7D && git cherry-pick 6bd89725516e3b57db32e833ce1f5bfaee2c1c69  
cd ~/android/system/packages/apps/BluetoothExt && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_BluetoothExt stable/cm-12.1-YOG7D && git cherry-pick 3827c6673f2fcf9e809e24b7089a2cbf455751a8  
cd ~/android/system/packages/apps/Contacts && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Contacts stable/cm-12.1-YOG7D && git cherry-pick 296f3f4d00b04bb3617647e1b6641666586e953c  
cd ~/android/system/packages/apps/Eleven && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Eleven stable/cm-12.1-YOG7D && git cherry-pick dbb4411c06efbf650bd9b1c94a703040c904c133  
cd ~/android/system/packages/apps/CMFileManager && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_CMFileManager stable/cm-12.1-YOG7D && git cherry-pick 4f4d459cb2bfb5e69778a5b2f0b5e2fe15b3dd3d  
cd ~/android/system/packages/apps/DeskClock && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_DeskClock stable/cm-12.1-YOG7D && git cherry-pick 78fb1a1f20201d162bac00e487a899c725bbfb11  
cd ~/android/system/packages/apps/SetupWizard && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_SetupWizard stable/cm-12.1-YOG7D && git cherry-pick 92e682d8a5158de40e18c6b8e5edaba74f238336  
cd ~/android/system/packages/apps/CMBugReport && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_CMBugreport stable/cm-12.1-YOG7D && git cherry-pick 54e1b6b960e1ae9f4f640be12c0d733f4b80a4ea  
cd ~/android/system/packages/apps/Trebuchet && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Trebuchet stable/cm-12.1-YOG7D && git cherry-pick 567c52bbe964d3f34c76387863d4791616c82ce3 
cd ~/android/system/packages/apps/Camera2 && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Camera2 stable/cm-12.1-YOG7D && git cherry-pick 23b415293f2db0197e9d604c24771c2c133e697a 
cd ~/android/system/packages/apps/LockClock && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_LockClock stable/cm-12.1-YOG7D && git cherry-pick 59f7c5ae198424aff92613a4d49dc68d2440d5dc 
cd ~/android/system/packages/apps/Email && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Email stable/cm-12.1-YOG7D && git cherry-pick 1a0dd079b5b77406d225fee62fd1456bb6b3112b 
cd ~/android/system/packages/apps/UnifiedEmail && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_UnifiedEmail stable/cm-12.1-YOG7D && git cherry-pick 077cb491ea7c8588948a7a389c3bb0a5fdd63441 
cd ~/android/system/packages/apps/Calculator && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Calculator stable/cm-12.1-YOG7D && git cherry-pick 5f3017e9d67f76029770a4a94f5e1c4f3698dac0 
cd ~/android/system/packages/apps/Browser && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Browser stable/cm-12.1-YOG7D && git cherry-pick 7885e0084687e685e9ec71ce483ef6b43b1c093b 
cd ~/android/system/packages/apps/Stk && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Stk stable/cm-12.1-YOG7D && git cherry-pick 5db817726f4006b1defe0aaed4138de6da9b85a6 
cd ~/android/system/packages/apps/Dialer && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Dialer stable/cm-12.1-YOG7D && git cherry-pick 9831f2dcff7a3987ef6f311c0ce93c36f3667fae 
cd ~/android/system/packages/apps/Bluetooth && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Bluetooth stable/cm-12.1-YOG7D && git cherry-pick 6b2470d3621a63e36d0e87d0543bad3e7b143e38 
cd ~/android/system/packages/apps/Calendar && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Calendar stable/cm-12.1-YOG7D && git cherry-pick f953a4f15e572c560e5a2e82ab8910b3cc55bd48 
cd ~/android/system/packages/apps/AudioFX && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_AudioFX stable/cm-12.1-YOG7D && git cherry-pick a97b7320371b1bc55b726b568af1c0edb10e5c03 
cd ~/android/system/packages/apps/Exchange && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Exchange stable/cm-12.1-YOG7D && git cherry-pick 658ab5ae9a301e732489639a091c5ee63aec0497 
cd ~/android/system/packages/apps/Nfc && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Nfc stable/cm-12.1-YOG7D && git cherry-pick bd7a41e9871feb8b2956288f2d65a08ced4190e5 
cd ~/android/system/packages/apps/Profiles && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Profiles stable/cm-12.1-YOG7D && git cherry-pick 8af478951ab8f4242a97e8ef192013bafd574551 
cd ~/android/system/packages/apps/ContactsCommon && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_ContactsCommon stable/cm-12.1-YOG7D && git cherry-pick 6658f1d737895505561bdc706c3bfbb4dfb0f69f 
cd ~/android/system/packages/apps/SoundRecorder && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_SoundRecorder stable/cm-12.1-YOG7D && git cherry-pick 7775426d04be56ff1bbe7e4576403a47fe97253b 
cd ~/android/system/packages/apps/PhoneCommon && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_PhoneCommon stable/cm-12.1-YOG7D && git cherry-pick 5eb4f6480754e82f3579c2cea7e83b3f7e2b6cde 
cd ~/android/system/packages/apps/Terminal && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Terminal stable/cm-12.1-YOG7D && git cherry-pick 601e163e2d3998a3c4f1f773289dabf0eeeb9c12 
cd ~/android/system/packages/apps/CellBroadcastReceiver && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_CellBroadcastReceiver stable/cm-12.1-YOG7D && git cherry-pick 52778f15b29f2abd0742b1c282ac4f40f165abeb 
cd ~/android/system/packages/apps/CMWallpapers && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_CMWallpapers stable/cm-12.1-YOG7D && git cherry-pick ead775153d0691df70685cdca8971e54a92d3b44 
cd ~/android/system/packages/apps/CMAccount && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_CMAccount stable/cm-12.1-YOG7D && git cherry-pick 0abfb7e162b533b4773b6639068d11420c236344 
cd ~/android/system/packages/apps/ManagedProvisioning && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_ManagedProvisioning stable/cm-12.1-YOG7D && git cherry-pick 043bddd3ff7b6ff226d4fe7ec6728b2c40cbd316 
cd ~/android/system/packages/apps/Tag && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Tag stable/cm-12.1-YOG7D && git cherry-pick 504cae282e6c3c1a6cf89fff66ba4418974a190e 
cd ~/android/system/packages/apps/SpeechRecorder && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_SpeechRecorder stable/cm-12.1-YOG7D && git cherry-pick 4a11b4837a2572e54d87708563369dde20cacca6 
cd ~/android/system/packages/apps/SmartCardService && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_SmartCardService stable/cm-12.1-YOG7D && git cherry-pick 01ffba3f2246d2d7e93f692af3a75fe26a5cd7c0 
cd ~/android/system/packages/apps/Provision && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_Provision stable/cm-12.1-YOG7D && git cherry-pick 3eb99b87018d4d6f4d7345e64c4ec9024c22a1e5 
cd ~/android/system/packages/apps/KeyChain && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_KeyChain stable/cm-12.1-YOG7D && git cherry-pick f57f2b10493cc308a13f7f1462494f9fb44ad42a 
cd ~/android/system/packages/apps/HTMLViewer && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_HTMLViewer stable/cm-12.1-YOG7D && git cherry-pick d83b5b91045b3a3b9cc4a1f62d2b37fc628879ba 
cd ~/android/system/packages/apps/CertInstaller && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_CertInstaller stable/cm-12.1-YOG7D && git cherry-pick 0d8c4bcbee73a914307ceaf4c66a38f120821e75 
cd ~/android/system/packages/apps/BasicSmsReceiver && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_BasicSmsReceiver stable/cm-12.1-YOG7D && git cherry-pick e4acf67c57d39606b9233d2558353af04b88677c 
cd ~/android/system/packages/apps/OneTimeInitializer && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_OneTimeInitializer staging/cm-12.0 && git cherry-pick fcc355e30c171b0a954c5aa0b0309b8ee4ce323a 
cd ~/android/system/packages/apps/CMUpdater && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_CMUpdater stable/cm-12.1-YOG7D && git cherry-pick 056e71b4e102c749ef3441ae13bdf4c349e49a44
cd ~/android/system/packages/apps/CMUpdater && git fetch https://github.com/LiquidSmokeX64/android_packages_apps_CMUpdater cm-12.1 && git cherry-pick 8b8fedcb9aef31694d8d0a5ac858a788b3993995

Build ROM and/or Kernel NOW

cd ~/android/system && make clean && export USE_CCACHE=1 && source build/envsetup.sh && breakfast bacon && croot && make bootimage
cd ~/android/system && make clean && export USE_CCACHE=1 && source build/envsetup.sh && breakfast bacon && croot && brunch bacon

ENJOY.
