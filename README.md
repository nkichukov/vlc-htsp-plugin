This is a fork of TRPB/vlc-htsp-plugin, which is a fork of ThomasLeister's VLC3.0 version. It works fine with the latest stable VLC version 3.0.16 on GNU/Gentoo Linux.

## Install

Make sure you have the lastest VLC 3.0 development libraries installed together with C++ development tools for your system. 

Install dependencies on Fedora Linux:

```
sudo dnf install gcc-c++ vlc-devel libatomic
```

Clone this repository and build the project

```
cd vlc-htsp-plugin
make
sudo cp libhtsp_plugin.so /usr/lib64/vlc/plugins/access/
```

Restart VLC, open the settings in advanced mode and search for "HTSP". Then enter your TVHeadend server's hostname and your login credentials. 

The Service Discovery module is listed under LAN and grabs the channel list from TVH.

## Tips

### Video stuttering while live playback and timeshift

=> Set "Clock synchronisation" to "Disable" in "Input/Codecs"
