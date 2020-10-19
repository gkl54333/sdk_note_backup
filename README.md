# sdk_note_backup

[offical]
sudo add-apt-repository ppa:morphis/anbox-support
sudo apt update
sudo apt install linux-headers-generic anbox-modules-dkms
sudo snap install --devmode --beta anbox

sudo snap stop anbox.container-manager
sudo ANBOX_LOG_LEVEL=debug snap run anbox.container-manager &
ANBOX_LOG_LEVEL=debug anbox session-manager

/run/user/1000/anbox/



adb shell logcat SurfaceFlinger:D hwcomposer:D gralloc_goldfish:D BufferQueueCore:D BufferQueueProducer:D DisplayDevice:D EGL_emulation:D *:S
adb shell logcat hwcomposer:D gralloc_goldfish:D *:S
adb shell logcat AnboxOMXPlugin:V OMXMaster:V ACodec:V MediaCodecList:V OMXNodeInstance:V *:S
adb shell logcat ActivityManager:V *:S
adb shell logcat gralloc_goldfish:D hwcomposer:D *:S

rpm -ivh --force --nodeps /opt/data/anbox-session-1.3.10-1.armv7l.rpm
[custom]
1. ANBOX_LOG_LEVEL=debug sudo anbox container-manager --daemon --privileged --data-path=/var/lib/anbox --android-image=/home/yinpeng/nteam/anbox-work/vendor/anbox/android-houdini.img
2. ANBOX_LOG_LEVEL=debug anbox session-manager --single-window --window-size=1024,768
3. anbox launch --package=org.anbox.appmgr --component=org.anbox.appmgr.AppViewActivity










[tizen_anbox_cmds]
docker exec anbox /system/bin/sh /system/bin/pm install /data/Application-debug.apk
docker exec anbox /system/bin/sh /system/bin/pm install /data/Camera2SlowMotion.apk
docker exec anbox /system/bin/sh /system/bin/pm install /data/Camera2Basic.apk
docker exec anbox /system/bin/sh /system/bin/pm install /data/HdrViewfinder.apk
docker exec anbox /system/bin/sh /system/bin/pm install /data/LightOS_resources_vLight_OS_1.0.1_release.apk
docker exec anbox /system/bin/sh /system/bin/pm install /data/LightOS_appstore_vLight_OS_1.0.1_release.apk
docker exec anbox /system/bin/sh /system/bin/pm install /data/ijkplayer-example-all32-debug.apk
docker exec anbox /system/bin/sh /system/bin/pm install /data/dangbeimarket_4.1.2_znds.apk
docker exec anbox /system/bin/sh /system/bin/pm install /data/ijkplayer-example-all32-debug.apk
docker exec anbox /system/bin/sh /system/bin/pm install /data/gamestick_3.11.1.616_android_20200402125220-reunion-release.apk
docker exec anbox /system/bin/sh /system/bin/pm install /data/AppRTCMobile.apk
docker exec anbox /system/bin/sh /system/bin/pm list package
docker exec anbox /system/bin/sh /system/bin/pm list package
docker exec anbox /system/bin/sh /system/bin/pm grant com.tencent.gamestick android.permission.WRITE_EXTERNAL_STORAGE
docker exec anbox /system/bin/sh /system/bin/pm grant com.tencent.gamestick android.permission.READ_PHONE_STATE
docker exec anbox /system/bin/dumpsys SurfaceFlinger


docker exec anbox /system/bin/sh /system/bin/pm install /data/linegae2.apk
docker exec anbox /system/bin/sh /system/bin/pm install /data/HunanOTT_V5.8.401.200.3.MGTV_TVAPP.0.0_Release.apk
docker exec anbox /system/bin/logcat ActivityManager:V *:S

docker exec anbox /system/bin/ls /system/lib/libstagefrighthw.so
docker exec anbox /system/bin/logcat AnboxOMXPlugin:V  *:S

docker exec anbox /system/bin/logcat OMX:V OMXClient:V OMXMaster:V ACodec:V MediaCodecList:V OMXNodeInstance:V SoftVideoDecoderOMXComponent:V *:S
docker exec anbox /system/bin/logcat OMX:V OMXClient:V OMXMaster:V ACodec:V MediaCodecList:V OMXNodeInstance:V  AnboxOMXPlugin:V *:S
docker exec anbox /system/bin/logcat SurfaceFlinger:D DisplayDevice:D *:S
docker exec anbox /system/bin/logcat AnboxOMXPlugin:V OMXMaster:V *:S

docker exec anbox /system/bin/logcat AndroidRuntime ActivityManager MtaSDK  *:S


docker exec anbox /system/bin/sh /data/ipconfig 109.123.121.71 109.123.111.170 109.123.121.1


rpm -ivh --force --nodeps /opt/data/anbox-session-1.3.10-1.armv7l.rpm

[tizen_anbox_startup]

dockerd --iptables=false&

ANBOX_LOG_LEVEL=debug /usr/apps/vnc/anbox session-manager --single-window --window-size=640,480 --binder=/dev/binder --data-path=/opt/anbox-data/ &

/usr/bin/docker/docker run  --network host --rm -d --cap-add ALL \
        --security-opt="apparmor=unconfined" \
        --security-opt="seccomp=unconfined" \
        --device /dev/binder --device /dev/ashmem --device /dev/fuse \0032:google.
        -e PATH=/system/bin:/system/sbin:/system/xbin \
        -e ANDROID_DATA=/data \
        -e ANDROID_ROOT=/system \
        -e ANDROID_ASSETS=/assets \
        -e ASEC_MOUNTPOINT=/mnt/asec \
        -e HOSTNAME=Tizen-TV \
        -e EXTERNAL_STORAGE=/sdcard \
        -e ANDROID_STORAGE=/storage \
        -e TMPDIR=/opt/anbox-data/ \
        --volume /opt/anbox-data/:/data/\
        --volume /run/anbox/sockets/qemu_pipe:/dev/qemu_pipe \
        --volume /run/anbox/sockets/anbox_bridge:/dev/anbox_bridge \
        --volume /run/anbox/sockets/anbox_audio:/dev/anbox_audio \
        --volume  /run/anbox/input/event0:/dev/input/event0 \
        --volume  /run/anbox/input/event1:/dev/input/event1 \
        --volume  /run/anbox/input/event2:/dev/input/event2 \
        --name anbox \
        android \
        /anbox-init.sh&

echo "pm install /data/MgTvLauncher201907080904_gengxin_1565089160663.apk" > /opt/anbox-data/app_install.sh
docker exec anbox cat /data/app_install.sh
docker exec anbox /system/bin/sh /data/app_install.sh





[network]
254 145 35 18 16 113
ifconfig eth0 down
ifconfig eth0 hw ether fe:91:23:12:10:71
ifconfig eth0 109.123.121.71 netmask 255.255.255.0
ifconfig eth0 up
route add default gw 109.123.121.1




scp /home/yinpeng/GBS-ROOT-MUSEM-5.0/local/repos/MAIN2019_MuseM/armv7l/RPMS/anbox-session-1.3.10-1.armv7l.rpm root@109.123.121.71:/opt/data/
ssh -t root@109.123.121.71 "rpm -ivh --force --nodeps /opt/data/anbox-session-1.3.10-1.armv7l.rpm"



[docker image]
sudo unsquashfs android.img
sudo tar -cvf squashfs-root.tar -C squashfs-root/ .



[tizen_mem]
/usr/bin/stability-monitor   改名

[ffplay]
ffplay -f rawvideo -pix_fmt rgba -s 640x480  ~/log/pic_dump_1567586707.283184.rgba


sted) native 


[#Set MAC Address]
        20102011 - 20089999
        8 - 1 - 3 - 1 - 2
        /**
        8 : SP / SA Debug Menu
        1 : SystemPlatform debug
        3 : libeeprom-map
        1 : EEPROM
        2.eeprom_write


        Please Enter Eeprom Write Address(in hex):
        $> 1e04
        Please Enter Eeprom Write Size(in dec):
        $> 6
        Do you want to send NULL pointer (0/1):
        0: for normal operation

        $> 0
        Please Enter Eeprom Write values:
        $> 254 145 35 18 16 113   (FE-91-23-12-10-71)
        $> 254 145 35 9 144 147   (FE-91-23-09-90-93)
        API calling successful
        
        然后用 5 (eeprom_read_mac) 来验证MAC Address是否正确



254 145 35 18 33 51   (FE-91-23-12-21-33)
(98-83-89-dd-be-a8)



[cloud_android]
1.	docker
https://docs.docker.com/install/linux/docker-ce/ubuntu/#set-up-the-repository

2.	ashmem,binder
sudo add-apt-repository ppa:morphis/anbox-support
sudo apt update
sudo apt install anbox-modules-dkms

sudo modprobe ashmem_linux
sudo modprobe binder_linux num_devices=10

3.	docker image
docker load  -i android_latest.tar

4.	run docker image
./run 0

ps: make docker imagedockerd --iptables=false&
sudo unmksquashfs android.img
sudo tar -C squashfs-root/ -c . | docker import - android:latest

sudo mksquashfs squashfs-root/ android-houdini.img -noappend -asted) native lways-use-fragments

docker exec anbox /system/bin/am start -a android.intent.action.VIEW -d  http://www.google.cn/
docker exec anbox /system/bin/am start -a android.intent.action.VIEW -d https://test-cloud-gaming.myqcloud.com/cloud_gaming_static/demo/mobile.html?gameid=11&userid=test_1589005687575&appid=2020032401&debug=9
am start -n com.wandoujia.phoenix2/com.pp.assistant.activity.PPMainActivity
am start -n com.sup.android.superb/.SplashActivity
docker exec anbox /system/bin/am start -n com.android.settings/com.android.settings.Settings
docker exec anbox /system/bin/sh /system/bin/pm

docker exec anbox /system/bin/logcat AnboxOMXPlugin:V *:S &
dlogutil TIZEN_N_PLAYER MM_PLAYER GST_LOG &
docker exec anbox /system/bin/am start -n com.mgtv.tv/.launcher.LauncherActivity 

docker exec anbox /system/bin/am kill com.mgtv.tv

rpm -ivh --force --nodeps /opt/data/anbox-session-1.3.10-1.armv7l.rpm




adb shell input tap 240 750

docker exec anbox /system/bin/sh /system/bin/input keyevent 4
docker exec anbox /system/bin/sh /system/bin/input keyevent 22



docker exec anbox /system/bin/sh /system/bin/input tap 10 10
docker exec anbox /system/bin/sh /system/bin/input tap 640 670

docker exec anbox /system/bin/sh /system/bin/input tap 1920 300
docker exec anbox /system/bin/sh /system/bin/input tap 80 750
docker exec anbox /system/bin/sh /system/bin/input tap 900 1000

docker exec anbox /system/bin/sh /system/bin/input tap 1060 1000

g++ network.cpp -o network_test -I/usr/local/include/boost/ -L/usr/local/lib -lboost_system


docker exec anbox /system/bin/logcat OMX:V OMXClient:V OMXMaster:V ACodec:V MediaCodecList:V OMXNodeInstance:V  AnboxOMXPlugin:V BufferQueueProducer:V BufferQueueCore:V gralloc_goldfish:V *:S &

docker exec anbox /system/bin/logcat OMX:V OMXClient:V OMXMaster:V ACodec:V MediaCodecList:V OMXNodeInstance:V  AnboxOMXPlugin:V  MediaCodec:V *:S SoftVideoDecoderOMXComponent:V SimpleSoftOMXComponent:V SoftOMXComponent:V *:S &

docker exec anbox /system/bin/logcat OMX:V OMXClient:V OMXMaster:V ACodec:V MediaCodecList:V OMXNodeInstance:V  AnboxOMXPlugin:V MediaCodec:V *:S &

docker exec anbox /system/bin/logcat Anboxd:I Channel:I *:S &

docker exec anbox /system/bin/logcat Anboxd:W MessageProcessor:W Channel:W *:S &

docker exec anbox /system/bin/logcat  SoftVideoDecoderOMXComponent:V SimpleSoftOMXComponent:V SoftOMXComponent *:S &

docker exec anbox /data/ip_config 109.123.121.71 109.123.111.170 109.123.121.1


ifconfig eth0 down
ifconfig eth0 hw ether 98:83:89:dd:be:a8
ifconfig eth0 109.123.100.138 netmask 255.255.255.0
ifconfig eth0 up
route add default gw 109.123.100.1

echo "/data/ip_config 109.123.121.71 109.123.111.170 109.123.121.1" > /opt/anbox-data/ip_set.sh


enlightenment_info -topwins

dlogutil -v threadtime ANBOX_CAMERA &

docker exec anbox /system/bin/logcat OMX:V OMXClient:V OMXMaster:V ACodec:V MediaCodecList:V OMXNodeInstance:V  AnboxOMXPlugin:I MediaCodec:V *:S &

docker exec anbox /system/bin/logcat  AnboxOMXPlugin:I Channel:I *:S &
docker exec anbox /system/bin/logcat  ACodec:I AnboxOMXPlugin:I NuPlayerRenderer:V NuPlayerDecoder:V MediaCodec:V *:S OMX:V &
docker exec anbox /system/bin/logcat NuPlayerRenderer:V AnboxOMXPlugin:I *:S &
docker exec anbox /system/bin/logcat NuPlayerRenderer:V ACodec:W OMXNodeInstance:W  *:S &
docker exec anbox /system/bin/logcat  AnboxOMXPlugin:I *:S ACodec:I &
docker exec anbox /system/bin/logcat *:S OMX:V OMXNodeInstance:I  AnboxOMXPlugin:D SoftOMXComponent:I &
docker exec anbox /system/bin/logcat *:S ACodec:I &

docker exec anbox /system/bin/logcat  OMXNodeInstance:V AnboxOMXPlugin:V SoftVideoDecoderOMXComponent:D SimpleSoftOMXComponent:D SoftOMXComponent:V *:S &

docker exec anbox /system/bin/logcat NuPlayerRenderer:V MediaClock:D  AudioSink:V AudioSystem:V AudioFlinger:D AudioTrack:D *:S MediaSync:D &

docker exec anbox /system/bin/logcat NuPlayerRenderer:V MediaPlayerService:V AudioSink:V AudioSystem:V APM_AudioPolicyManager:V AudioPolicyInterfaceImpl:V *:S &

docker exec anbox /system/bin/logcat audio_hw_generic:V *:S &

docker exec anbox /system/bin/logcat NuPlayerRenderer:D MediaClock:D ACodec:I OMX:W OMXNodeInstance:W  *:S &


docker exec anbox /system/bin/logcat NuPlayerRenderer:D MediaClock:D VideoFrameScheduler:V *:S &


docker exec anbox /system/bin/logcat NuPlayerRenderer:D MediaClock:D AnboxOMXPlugin:I ACodec:D NuPlayerDecoder:D *:S&


docker exec anbox /system/bin/logcat MediaPlayerService:V MediaPlayer:V NuPlayer:V NuPlayerDriver:V ACodec:V HTTPLiveSource:V LiveSession:V GenericSource:V *:S AnotherPacketSource:D PlaylistFetcher:V HTTPDownloader:V &

docker exec anbox /system/bin/logcat NuPlayerRenderer:D ACodec:D *:S &


docker exec anbox /system/bin/logcat ActivityManager:V *:S &

docker exec anbox /system/bin/logcat -v threadtime MediaPlayerService:V mediaserver:E NuPlayerRenderer:D NuPlayer:E NuPlayerDecoder:D ACodec:D  MediaCodec:D ALooper:I AnboxOMXPlugin:V MediaPlayer:V *:S &

docker exec anbox /system/bin/logcat *:V &

docker exec anbox /data/mplayer /data/60fps_new.mp4

docker exec anbox /system/bin/logcat AnboxOMXPlugin:I ACodec:D mediacodec:V OMXClient:V OMX:V MediaCodecList:V OMXNodeInstance:V *:E &
docker exec anbox /system/bin/logcat NuPlayerRenderer:V NuPlayerDecoder:V ACodec:V AnboxOMXPlugin:V MediaCodec:V *:S &
docker exec anbox /system/bin/logcat ACodec:V NuPlayerRenderer:V  MediaCodec:V AnboxOMXPlugin:V OMXNodeInstance:V mediacodec:V OMXClient:V OMX:V MediaCodecList:V MediaCodecService:V OMX:V IOMX:V  SoftVideoDecoderOMXComponent:V SimpleSoftOMXComponent:V SoftOMXComponent:V mediaserver:D SurfaceFlinger:V gralloc_goldfish:V *:W &

docker exec anbox /system/bin/logcat ACodec:V NuPlayerRenderer:V  MediaCodec:V AnboxOMXPlugin:V OMXNodeInstance:V mediacodec:V OMXClient:V OMX:V MediaCodecList:V MediaCodecService:V OMX:V IOMX:V mediaserver:D OMXMaster:V *:S &

docker exec anbox /system/bin/logcat ACodec:V NuPlayerRenderer:V  MediaCodec:V AnboxOMXPlugin:V OMXNodeInstance:V mediacodec:V OMXClient:V OMX:V MediaCodecList:V MediaCodecService:V OMX:V IOMX:V mediaserver:D OMXMaster:V *:S &

docker exec anbox /data/mplayer /data/1920x1080.mp4

docker exec anbox /system/bin/logcat hwcomposer:S *:E


docker exec anbox /system/bin/logcat AnboxOMXPlugin:I *:S &
docker exec anbox /system/bin/logcat ACodec:D AnboxOMXPlugin:D *:S &

docker exec anbox /system/bin/logcat ACodec:D SSOMX:V *:S &

docker exec anbox /system/bin/logcat ACodec:D *:S &

docker exec anbox /system/bin/logcat ACodec:V NuPlayerRenderer:D AnboxOMXPlugin:I MediaCodec:V *:S &
docker exec anbox /system/bin/logcat MediaCodecList:V ACodec:V SSOMX:V *:S &
docker exec anbox /system/bin/logcat MediaCodecList:V ACodec:V *:S &

docker exec anbox /system/bin/logcat ACodec:D SurfaceFlinger:D DispSync:D DispSyncThread:D *:S &

docker exec anbox /system/bin/logcat SurfaceFlinger:I gralloc_goldfish:D *:E &

docker exec anbox /system/bin/logcat MyTest:V *:S &
docker exec anbox /system/bin/sh /system/bin/input keyevent 4
docker exec anbox /system/bin/sh /system/bin/input tap 1900 600


docker exec anbox /system/bin/logcat PTHREAD_TEST:I *:S &
docker exec anbox /system/bin/chrt
docker exec anbox /system/bin/ps | grep pthread
docker exec anbox /system/bin/nice -n -20 /data/pthread_test
docker exec anbox /data/pthread_test

ps -aux | grep pthread

docker exec anbox /system/bin/am start -a android.intent.action.VIEW -d "https://test.webrtc.org/"
docker exec anbox /system/bin/am start -a android.intent.action.VIEW -d "https://www.baidu.com/"

docker exec anbox /system/bin/am start -a android.intent.action.VIEW -d "https://test.webrtc.org/"
chrt -p -f 10 


docker exec anbox /system/bin/logcat NuPlayerRenderer:V MediaClock:D  AudioSink:V AudioSystem:V AudioFlinger:D AudioTrack:D *:S &
docker exec anbox /system/bin/logcat NuPlayerRenderer:V SoftAAC2:V MediaClock:D *:S &

docker exec anbox /system/bin/logcat NuPlayerRenderer:V MediaCodec:V ACodec:V  OMXNodeInstance:V  AnboxOMXPlugin:D am *:S &

docker exec anbox /system/bin/logcat SurfaceFlinger:V *:E &
docker exec anbox /system/bin/logcat mediaserver:E SurfaceFlinger:E mediacodec:E *:S &

docker exec anbox /system/bin/logcat mediaserver:D  MediaPlayerService:V MediaPlayer:V IMediaPlayer:V *:S &

docker exec anbox /system/bin/logcat ActivityManager:V *:S
docker exec anbox /system/bin/logcat audio_hw_generic:V *:S

docker exec anbox /system/bin/logcat org.webrtc.Logging:V TcgSdk:V MediaCodecList:V *:S


docker exec anbox /system/bin/logcat UsbService:V UsbManager:V SystemServer:V *:S

docker exec anbox /data/mplayer /data/60fps_new.mp4
docker exec anbox /data/mplayer /data/framedrop_with_audio.mp4
docker exec anbox /data/mplayer /data/1920x1080.mp4
/usr/apps/org.tizen.tv-viewer/bin


docker exec anbox /system/bin/logcat ALooper:D libutils.threads:W *:S &
docker exec anbox /system/bin/getprop ro.build.version.sdk
cat /sys/kernel/debug/dri/0/gem_info

systemctl status session-manager
systemctl status anbox-container

dockerd --iptables=false&


docker exec anbox /system/bin/logcat AnboxOMXPlugin:D *:S &

dlogutil ANBOX CLOUDUI_VDI OMX_C OMX_V &
dlogutil CLOUDUI_VDI &
dlogutil ANBOX &
dlogutil AUDIO_HAL SECAUDIO GET_LOG PLUSPLAYER &
dlogutil PLUSPLAYER
dlogutil AUDIO_HAL_INTF AUDIO_HAL ALSA OMX_A &
dlogutil AUDIO_HAL &

dlogutil MM_PLAYER GST_LOG &
dlogutil AUDIO_SINK PLUSPLAYER &
dlogutil AUDIO_SINK PLUSPLAYER ESPLAYER MMPLAYER &
dlogutil AUDIO_SINK &
dlogutil GST_LOG &

dlogutil AVOC-API &

amixer -c 0 controls
amixer -c 0 cget iface=MIXER,name='speaker out gain'
amixer -c 0 cset iface=MIXER,name='main out gain' 100
amixer -c 0 cget iface=MIXER,name='main out gain'

dlogutil ANBOX CLOUDUI_VDI OMX_A OMX_V OMX_C DOV_VERIFIER &
dlogutil OMX_A

dlogutil TCOMP &


/root/.local/share/applications/anbox
109.123.99.93    fe:91:23:09:90:93
109.123.100.20   98:90:96:A6:43:B6
109.123.121.184  fe:91:23:12:11:84

/usr/apps/vnc/anbox session-manager --use-system-dbus --single-window --binder=/dev/binder --data-path=/opt/anbox-data &



systemctl start anbox-container
enlightenment_info -topwins

export FrameworkPathOverride=



gst-launch-1.0 filesrc location=/media/USBDriveA/1920x1080.mp4  ! qtdemux name=demux demux.audio_0 ! queue ! ffdec_aac ! autoaudiosink demux.video_0 ! queue ! ffdec_h264 ! directvideosink

gst-launch-1.0 filesrc location=/opt/data/123.wav ! wavparse  ! alsasink

gst-launch-1.0 filesrc location=/opt/data/123.mp3 ! omx_tz_mp3dec ! autoaudiosink

gst-launch-1.0 filesrc location=/opt/data/123.mp3 ! ffdemux_mp3 ! omx_mp3dec ! autoaudiosink
gst-launch-1.0 filesrc location=/opt/data/123.mp3 ! mpegaudioparse ! omx_mp3dec ! alsasink-tv



export GST_DEBUG=*:3,directvideosink:9
gst-launch-1.0 filesrc location=/opt/data/123.mp3 ! ffdemux_mp3 ! omx_mp3dec ! mmaudiosink

gst-launch-1.0 filesrc location=/media/USBDriveA/1920x1080.mp4 ! qtdemux name=demux demux.audio_0 ! queue ! aacparse ! omx_aacdec ! autoaudiosink demux.video_0 ! queue ! h264parse ! omx_tz_h264dec ! directvideosink




docker exec anbox /data/tcpdump -s0 host 49.232.73.109 or 129.204.73.105 or 129.204.88.158 or 152.136.27.202 or 152.136.218.199 -w /data/dump0520_5.pcap

docker exec anbox /data/tcpdump -s0 port 19302 or port 3478  -w /data/dump0602_0.pcap

docker exec anbox /data/tcpdump -s0 host 212.64.122.46 -w /data/dump0602_1.pcap

docker exec anbox /data/tcpdump -s0 host 192.168.1.102 -w /data/dump1.pcap

docker exec anbox /data/tcpdump -s0 -w /data/dump0602_3.pcap

export PATH="$PATH:/home/yinpeng/2020/depot_tools"


gn gen out/Default

target_os="android"
is_debug=false
is_official_build=true
is_chrome_branded=false
use_official_google_api_keys=false
exclude_unwind_tables=true
enable_resource_whitelist_generation=true
ffmpeg_branding="Chrome"
proprietary_codecs=true
enable_remoting=true


autoninja -C out/Default system_webview_apk



docker exec anbox /system/bin/logcat org.webrtc.Logging:V TcgSdk:V ACodec:V MediaCodecList:V MediaCodecInfo:V MediaCodec:V  TCGWebView:V TcgSdkWrapper:V WEBRTC:V chromium:S EGL_emulation:S SoftVideoDecoderOMXComponent:D SimpleSoftOMXComponent:D IOMX:V  OMXNodeInstance:V mediacodec:V OMXClient:V OMX:V MediaCodecList:V MediaCodecService:V OMX:V IOMX:V mediaserver:D OMXMaster:V SoftAVC:V OMX_V:V *:S &

docker exec anbox /system/bin/logcat org.webrtc.Logging:V TcgSdk:V TCGWebView:V TcgSdkWrapper:V  *:S &

docker exec anbox /system/bin/logcat android_network_monitor.cc:V network_monitor.cc:V physical_socket_server.cc:V basic_packet_socket_factory.cc:V turn_port.cc:V stun_port.cc:V network.cc:V async_socket.cc:V basic_port_allocator.cc:V TcgSdk:V org.webrtc.Logging:V *:S &

docker exec anbox /system/bin/logcat android_network_monitor.cc:V *:S V

docker exec anbox /data/tcpdump -s0 port 19302 or port 3478  -w /data/dump0528_2.pcap &

docker exec anbox /system/bin/find / -name "libjingle_peerconnection_so.so"
docker exec anbox /system/bin/logcat WEBRTC:V *:S &




docker exec anbox /system/bin/ifconfig


docker exec anbox /system/bin/am start -a android.intent.action.VIEW -d "https://test.webrtc.org/"

docker exec anbox /system/bin/am start -a android.intent.action.VIEW -d "https://www.baidu.com/"

docker exec anbox /system/bin/am start -a android.intent.action.VIEW -d "https://test-cloud-gaming.myqcloud.com/cloud_gaming_static/demo/demo.html?appid=2020032401&gameid=5&userid=aoc_test&debug=1"

# remount filesystem as rw
mount -o rw,remount /
echo "mount -o rw,remount /" > /root/.bashrc





dlogutil SECVIDEODISP GST_LOG  &




dlogutil -v threadtime ANBOX_CAMERA &

docker exec anbox /system/bin/sh /system/bin/input keyevent 4




[qt]
./configure -qt-xcb -no-openssl -opensource -no-compile-examples -skip qtwebengine 

export PKG_CONFIG_PATH=$PKG_CONFIG_PATH:/usr/local/Qt-5.6.0/lib/pkgconfig
export PATH=$PATH:/usr/local/Qt-5.6.0/bin/

export QT_SELECT=5.6.0





docker exec anbox /system/bin/am start -a android.intent.action.VIEW -d  http://www.google.cn/
docker exec anbox /system/bin/am start -a android.intent.action.VIEW -d  http://www.baidu.com/

docker exec anbox /system/bin/sh /system/bin/input tap 10 10
docker exec anbox /system/bin/sh /system/bin/input tap 980 1050
docker exec anbox /system/bin/sh /system/bin/input tap 850 1050

docker exec anbox /system/bin/sh /system/bin/input tap 1050 1050

docker exec anbox /system/bin/sh /system/bin/pm install /data/58452c9afee70471bfb8b2ba34714389.apk
docker exec anbox /system/bin/sh /system/bin/pm install /data/IP\ Webcam_v1.5_apkpure.com.apk

docker exec anbox /system/bin/sh /system/bin/pm  uninstall com.android.example.camera2.basic
docker exec anbox /system/bin/sh /system/bin/pm  install /data/Camera2Basic.apk

docker exec anbox /system/bin/sh /system/bin/pm  uninstall com.example.android.hdrviewfinder
docker exec anbox /system/bin/sh /system/bin/pm  install /data/HdrViewfinder.apk

docker exec anbox /system/bin/sh /system/bin/pm  uninstall com.microsoft.teams
docker exec anbox /system/bin/sh /system/bin/pm  install /data/58452c9afee70471bfb8b2ba34714389.apk

docker exec anbox /system/bin/sh /system/bin/pm  uninstall com.skype.raider
docker exec anbox /system/bin/sh /system/bin/pm  install /data/com.skype.raider_8.62.0.85-1250094176_minAPI23\(armeabi-v7a\)\(nodpi\)_apkmirror.com.apk
docker exec anbox /system/bin/sh /system/bin/pm  install /data/com.skype.raider_7.46.0.596-120455764_minAPI15\(armeabi-v7a\)\(nodpi\)_apkmirror.com.apk

docker exec anbox /system/bin/sh /system/bin/pm  install /data/WhatsApp\ Messenger_v2.20.195.17_apkpure.com.apk

docker exec anbox /system/bin/sh /system/bin/pm  install /data/Skype\ Lite\ Free\ Video\ Call\ Chat_v1.84.76.1_apkpure.com.apk

docker exec anbox /system/bin/sh /system/bin/pm  install /data/Messager.apk
docker exec anbox /system/bin/sh /system/bin/pm  install /data/discord.apk
docker exec anbox /system/bin/sh /system/bin/pm  install /data/momo_8.26.1_c1.apk.apk
docker exec anbox /system/bin/sh /system/bin/pm  install /data/Wandoujia.apk
docker exec anbox /system/bin/sh /system/bin/pm  install /data/qqhd_5.8.4_dangbei.apk

docker exec anbox /system/bin/sh /system/bin/pm install /data/webrtc_android.apk

docker exec anbox /system/bin/sh /system/bin/pm  uninstall com.wdliveuctv.android.ActiveMeeting7
docker exec anbox /system/bin/sh /system/bin/pm list package

docker exec anbox /system/bin/logcat Camera-Device:V EmulatedCamera_QemuDevice:V CameraService:V DefaultCameraHAL:V V4L2CameraHAL:V HAL:V *:S

docker exec anbox /system/bin/logcat CameraService:V  V4L2CameraHAL:V Camera:V Camera3-Device:V Camera2ClientBase:V CameraDeviceClient:V CameraModule:V CameraTraces:V Camera2-Parameters:V Camera3-OutputStream:V CameraBasic:V *:S &

docker exec anbox /system/bin/logcat CameraService:V  Camera:V Camera3-Device:V HAL:V Camera2ClientBase:V CameraDeviceClient:V CameraModule:V CameraTraces:V Camera2-Parameters:V Camera3-OutputStream:V CameraBasic:V  *:S &

docker exec anbox /system/bin/logcat Camera2-Parameters:V Camera3-OutputStream:V Camera3-BufferManager:V gralloc_goldfish:V V4L2CameraHAL:V audio_hw_generic:V *:S &
docker exec anbox /system/bin/logcat Calling:V audio_hw_generic:V *:S

docker exec anbox /system/bin/logcat CameraService:V  Camera:V Camera3-Device:V  Camera3-OutputStream:V Camera3-Stream:V gralloc_goldfish:V *:S



docker exec anbox /system/bin/logcat CameraService:V  Camera:V Camera3-Device:V Camera2ClientBase:V CameraDeviceClient:V CameraModule:V CameraTraces:V Camera2-Parameters:V Camera3-OutputStream:V CameraBasic:V StaticProperties:V V4L2CameraHAL:V  Camera2-StreamingProcessor:V Camera2-CallbackProcessor:V *:S &


docker exec anbox /system/bin/logcat V4L2CameraHAL:V   *:S
docker exec anbox /system/bin/logcat CameraService:V *:S &

docker exec anbox /system/bin/logcat *:E &

docker exec anbox /system/bin/logcat -b radio &

docker exec anbox /system/bin/logcat ADB:V *:S &

docker exec anbox /system/bin/cp /data/adbd /sbin/
docker exec anbox /system/bin/cp /data/camera.v4l2.so /system/lib/hw/
docker exec anbox /system/bin/cp /data/libcameraservice.so /system/lib/
docker exec anbox /system/bin/cp /data/gralloc.goldfish.so /system/lib/hw/
docker exec anbox /system/bin/cp /data/rild /system/bin/
docker exec anbox /system/bin/ls /system/lib/hw/ -l

[spice and spice proxy]
1. start http server at spice-html5 directory
2. start tizen emulator with spice server enabled
3. enter websockify directory and start websockify: ./run 5988 0.0.0.0:5901  (proxy port + spice server ip:port)
4. chrome open 0.0.0.0:8080

systemctl status session-manager
systemctl status anbox-container

./dma_test_2 -i /dev/video0 -f YUYV -S 640,480 -s 1920,1080@0,0 -M 123 -o 38:20:1920x1080 -F YUYV -t 1920,1080@0,0 -b 1



docker exec anbox /system/bin/setprop service.adb.tcp.port 5555
docker exec anbox /system/bin/setprop persist.adb.trace_mask 0

docker exec anbox /system/bin/setprop ctl.stop adbd

docker exec anbox /system/bin/getprop init.svc.adbd


/usr/apps/vnc/anbox session-manager --use-system-dbus --single-window --binder=/dev/binder --data-path=/opt/anbox-data/ &

dlogutil -v threadtime ANBOX_EXT MALI-DDK &
dlogutil -v threadtime ANBOX ANBOX_EXT COREGL &

docker exec anbox /system/bin/logcat EglRenderer *:S &
docker exec anbox /system/bin/logcat org.webrtc.Logging:E AndroidRuntime:E EglRenderer *:S &


docker exec anbox /system/bin/cp /data/libGLESv2_enc.so /system/lib/

docker exec anbox /system/bin/cp /data/ethernet-service.jar /system/framework/

export COREGL_TRACE_API=1
dlogutil COREGL &
dlogutil -v threadtime ANBOX &



scp yinpeng@109.123.100.20:/home/yinpeng/GBS-ROOT-MUSEM-5.0/local/repos/MAIN2019_MuseM/armv7l/RPMS/anbox-session-1.3.10-1.armv7l.rpm /opt/data/

docker exec anbox /system/bin/logcat EthernetNetworkFactory:V *:S


docker exec anbox /system/bin/logcat Netd:V *:S
scp /home/yinpeng/2020/anbox-work/out/target/product/armv7-a-neon/system/bin/netd root@109.123.99.93:/opt/anbox-data/
docker exec anbox /system/bin/stop netd
docker exec anbox /system/bin/cp /data/netd /system/bin/






[webrtc]

<build opensource webrtc>
gn gen out/x86 --args='target_os="android" target_cpu="x86" rtc_include_tests=false rtc_build_tools=false rtc_build_examples=false'
autoninja -C out/x86

<set tizen brower privilege>
/usr/sbin/cyad -s --bucket="MANIFESTS_GLOBAL" --client="User::Pkg::org.tizen.browser" --user="*" --privilege="http://tizen.org/privilege/camera" --type=0xFFFF

<launch browser>
launch_app org.tizen.browser __APP_SVC_URI__  "https://109.123.123.28:8080/videoroomtest.html?simulcast=true"
launch_app org.tizen.browser __APP_SVC_URI__  "http://duo.google.com/?web&noredirect&forceGroupCalling"
launch_app org.tizen.browser __APP_SVC_URI__  "http://duo.google.com"
launch_app org.tizen.browser __APP_SVC_URI__  "https://duo.google.com"
launch_app org.tizen.browser __APP_SVC_URI__ "https://duo.app.goo.gl/3Jlb1HiC7I5TT1sFLFG9jB"

launch_app org.tizen.browser __APP_SVC_URI__  "http://www.enhanceie.com/ua.aspx"

v4l2-ctl --list-formats-ext
ffmpeg -f v4l2 -input_format yuyv422 -video_size 800x600 -i /dev/video250 -c:v copy -pix_fmt yuyv422 /opt/data/800x600
ffmpeg -f v4l2 -input_format mjpeg -video_size 800x600 -i /dev/video250 -c:v copy -pix_fmt mjpeg /opt/data/800x600.mjpeg
ffmpeg -f v4l2 -input_format yuyv422 -video_size 800x600 -i /dev/video250 -c:v copy -f null /dev/null

ffmpeg -f v4l2 -input_format yuyv422 -video_size 800x600 -i /dev/video250 -c:v rawvideo -filter:v scale=960:540 -pix_fmt yuyv422 /opt/data/output.avi
ffmpeg -f v4l2 -input_format yuyv422 -video_size 800x600 -i /dev/video250 -c:v rawvideo -filter:v scale=960:540 -f null /dev/null

ffmpeg -f v4l2 -input_format yuyv422 -video_size 800x600 -i /dev/video250 -c:v libvpx -filter:v scale=960:540 -deadline realtime -threads 4 -f null /dev/null
ffmpeg -f v4l2 -input_format yuyv422 -video_size 800x600 -i /dev/video250 -c:v libvpx -filter:v scale=960:540 /opt/data/output.avi

ffmpeg -f rawvideo -video_size 800x600 -i /opt/data/800x600.yuv -c:v libvpx -deadline realtime -threads 4 -f null /dev/null
ffmpeg -f rawvideo -video_size 960x540 -i /opt/data/960x540.yuv -c:v libvpx -deadline realtime -threads 4 -f null /dev/null
ffmpeg -f mjpeg -i /opt/data/800x600.mjpeg -c:v libvpx -threads 4 -deadline realtime -f null /dev/null

ffmpeg -f v4l2 -input_format yuyv422 -video_size 800x600 -i /dev/video250 -c:v libvpx -deadline realtime -threads 4 /opt/data/800x600.yuv



ffmpeg -f v4l2 -input_format yuyv422 -video_size 640x480 -i /dev/video250 -c:v libvpx -threads 4 -f null /dev/null
ffmpeg -f v4l2 -input_format yuyv422 -video_size 800x600 -i /dev/video250 -c:v libvpx -deadline realtime -threads 4 /opt/data/800x600.webm

ffmpeg -f v4l2 -input_format mjpeg -video_size 800x600 -i /dev/video250 -c:v libvpx -threads 4 -deadline realtime -f null /dev/null
ffmpeg -f v4l2 -input_format yuyv422 -video_size 800x600 -i /dev/video250 -c:v libvpx -threads 4 -deadline realtime -f null /dev/null

ffmpeg -f rawvideo -video_size 800x600 -i /opt/data/800x600.webm -c:v libvpx -threads 4 -deadline realtime -f null /dev/null




ffmpeg -f v4l2 -input_format yuyv422 -video_size 640x360 -i /dev/video250 -c:v libvpx -filter:v scale=960:540 -deadline realtime -threads 4 -f null /dev/null
ffmpeg -f v4l2 -input_format yuyv422 -video_size 800x600 -i /dev/video250 -c:v libvpx -filter:v scale=960:540 -deadline realtime -threads 4 -f null /dev/null





ffmpeg -f v4l2 -input_format yuyv422 -video_size 800x600 -i /dev/video250 -c:v copy -pix_fmt yuyv422 /opt/data/800x600

launch_app org.tizen.browser __APP_SVC_URI__  "https://109.123.123.28:8080/videoroomtest.html?simulcast%3Dtrue"
launch_app org.tizen.browser __APP_SVC_URI__  "https://duo.google.com"
dlogutil -v threadtime CHROMIUM-WEBRTC CHROMIUM &

dlogutil -v threadtime CHROMIUM-WEBRTC | grep GetVideoReceiverInfo
dlogutil -v threadtime CHROMIUM-WEBRTC | grep GetVideoSenderInfo
dlogutil -v threadtime CHROMIUM PLUSPLAYER ESPLAYER MMPLAYER &

sed -i '2c export GST_DEBUG=2,*ff*:9,*omx*:9,*ai*:9,*sink*:9' /etc/profile.d/gstreamer.sh
sed -i '15c gstparam1=--gst-debug=\*:2,*ff*:9,*omx*:9,*ai*:9,*sink*:9' /etc/multimedia/mused.conf
chsmack -a "_" /etc/multimedia/mused.conf

dlogutil -c;
logger-mgr --filter PLUSPLAYER AIFW_API GST_LOG;
dlogutil -r 10000000 PLUSPLAYER AIFW_API GST_LOG:D -v kerneltime -f /tmp/ai.log&



dlogutil -c
logger-mgr --filter PLUSPLAYER CHROMIUM;
dlogutil  -r 10000000  CHROMIUM PLUSPLAYER -v kerneltime -f /tmp/6.log &
