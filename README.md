This is a fork of TRPB/vlc-htsp-plugin, which is a fork of ThomasLeister's VLC3.0 version, which is a fork of the original BtbN/vlc-htsp-plugin.

It works with the latest stable VLC version 3.0.16 on GNU/Gentoo Linux and TVHeadend version 4.2.8.

Tested to work on amd64 and aarch64 architectures.

## Install

GNU/Gentoo ebuild is available and pending release.

Make sure you have the lastest VLC 3.0 development libraries installed together with C++ development tools for your system. 

Install dependencies on Fedora Linux:

```
sudo dnf install gcc-c++ vlc-devel libatomic
```

Clone this repository and build the project

```
git clone https://github.com/nkichukov/vlc-htsp-plugin
cd vlc-htsp-plugin
make
strip libhtsp_plugin.so # Optional
sudo cp libhtsp_plugin.so /usr/lib64/vlc/plugins/access/
```

Restart VLC, open the settings in advanced mode and search for "HTSP". Then enter your TVHeadend server's hostname and your login credentials, if required.

## Automatic service discovery

The Service Discovery module is listed under LAN and when selected grabs the channel and recording lists from TVHeadend.

It adds all channels to the 'All channels' category and also groups them in categories by tag. The recordings are added to a category called '\_Recordings' and are ordered by recording start date by default, latest first. The format of the Date field allows VLC to sort by date in the playlist.

## Playback

Playback of channels happens via HTSP protocol.
Playback of recordings happens via HTTP protocol and it supports seeking. If the recordings are in a TS container, there is no overall duration time available but seeking works. If the recordings are in MKV, WEBM, and so on the duration time is available.

## EPG

EPG for channels is available, but can only be seen on current active channel if you go to Tools / Program Guide.

## VLC item list and recordings

Due to lack of appropriate item fields specific to recordings you may find that recordings metadata is spread around unexpected VLC metadata item fields.

## Tips

### Video stuttering while live playback and timeshift

=> Set "Clock synchronisation" to "Disable" in "Input/Codecs"

### Any other problems

=> Start VLC with increased verbosity
```
vlc -vvv
```

## Final words

This has been my favourite TVHeadend integration interface on a computer. I still continue to use other TVHeadend clients depending on the use case but this one just does the job. It is very light-weight, extremely fast and the UI is well structured so you can find everything you need at a glance.
Two last words of appreciation for everybody who has maintained or contributed to the development of this plugin so far. Thank you!
