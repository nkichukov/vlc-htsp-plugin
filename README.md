This is a fork ofd ThomasLeister's VLC3.0 version that works with current nightlies [As of 15/10/2016]

## Install

Make sure you have the lastest VLC 3.0 development libraries installed together with C++ development tools for your system. 

Install dependencies on Fedora Linux:

```
sudo dnf install gcc-c++ vlc-devel libatomic
```

Download, configure, make and install plugin file

```
wget https://github.com/ThomasLeister/vlc-htsp-plugin/archive/master.zip
unzip master.zip
cd vlc-htsp-plugin-master
make
sudo cp libhtsp_plugin.so /lib64/vlc/plugins/access/
```

Restart VLC, open the settings in advanced mode and search for "HTSP". Then enter your TVHeadend server's hostname and your login credentials. 

URL format is htsp://{username{:password}@}server{:port}/channelId
The Service Discovery module is listed under LAN and grabs the channel list from TVH.

## Tips

### Video stuttering while live playback and timeshift

=> Set "Clock synchronisation" to "Disable" in "Input/Codecs"
