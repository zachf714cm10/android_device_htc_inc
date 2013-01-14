CM10.1 for the Droid Incredible

## Info
[**XDA Discussion thread**](http://forum.xda-developers.com/showthread.php?t=1882918)

### Initialize
[Setup Linux/OS X](http://source.android.com/source/initializing.html) - Please note: it must be sun-java-6, not openjdk

### Prepare to download sources
```bash
mkdir ~/BAKED
mkdir ~/bin
cd ~/BAKED/
curl https://dl-ssl.google.com/dl/googlesource/git-repo/repo > ~/bin/repo
chmod a+x ~/bin/repo
repo init -u https://github.com/TeamBAKED/platform_manifest.git -b jb-4.2
```

### Finish setting up repo
```bash
wget -O .repo/local_manifest.xml https://raw.github.com/zachf714cm10/android_device_htc_inc/cm-10.1/Manifest/local_manifest.xml
```

### Download the source
```bash
cd ~/BAKED
repo sync 
```
NOTE: This WILL take a long time.

### Build
Make sure we're in ~/BAkED...
```bash
cd ~/BAKED
```
Pull in the prebuilts, like (currently only self-added GooManager)...
```bash
./vendor/cm/get-prebuilts
```
And build!
```bash
. build/envsetup.sh && time brunch inc
```

