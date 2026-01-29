# enterflatpak
A shell script to get into the shell of a flatpak.

## Usage Example

Let's see what comes up on my system for freedesktop:

```
$ enterflatpak freedesk
No running instance found for flatpak: freedesk
 1) org.freedesktop.LinuxAudio.Plugins.Calf,25.08,x86_64,system	      15) org.freedesktop.Platform.GL.default,24.08,x86_64,user
 2) org.freedesktop.LinuxAudio.Plugins.LSP,25.08,x86_64,system	      16) org.freedesktop.Platform.GL.default,25.08,aarch64,user
 3) org.freedesktop.LinuxAudio.Plugins.MDA,25.08,x86_64,system	      17) org.freedesktop.Platform.GL.default,25.08-extra,aarch64,user
 4) org.freedesktop.LinuxAudio.Plugins.ZamPlugins,25.08,x86_64,system  18) org.freedesktop.Platform.GL.default,25.08-extra,x86_64,system
 5) org.freedesktop.Platform,24.08,x86_64,system		      19) org.freedesktop.Platform.GL.default,25.08-extra,x86_64,user
 6) org.freedesktop.Platform,24.08,x86_64,user			      20) org.freedesktop.Platform.GL.default,25.08,x86_64,system
 7) org.freedesktop.Platform,25.08,x86_64,system		      21) org.freedesktop.Platform.GL.default,25.08,x86_64,user
 8) org.freedesktop.Platform,25.08,x86_64,user			      22) org.freedesktop.Platform.openh264,2.5.1,x86_64,system
 9) org.freedesktop.Platform.codecs-extra,25.08-extra,aarch64,user     23) org.freedesktop.Platform.openh264,2.5.1,x86_64,user
10) org.freedesktop.Platform.codecs-extra,25.08-extra,x86_64,system    24) org.freedesktop.Sdk,24.08,x86_64,system
11) org.freedesktop.Platform.codecs-extra,25.08-extra,x86_64,user      25) org.freedesktop.Sdk,24.08,x86_64,user
12) org.freedesktop.Platform.GL.default,24.08extra,x86_64,system       26) org.freedesktop.Sdk,25.08,aarch64,user
13) org.freedesktop.Platform.GL.default,24.08extra,x86_64,user	      27) org.freedesktop.Sdk,25.08,x86_64,system
14) org.freedesktop.Platform.GL.default,24.08,x86_64,system	      28) org.freedesktop.Sdk,25.08,x86_64,user
Select flatpak to enter or q to quit: q
```

Note that the output includes multiple choices. What makes the list unique is the application name, its branch, the architecture, and whether or not installed on the system vs the user.

In any event, the output is a bit much, let's narrow it down to the Sdk:

```
$ enterflatpak freedesktop.Sdk
No running instance found for flatpak: freedesktop.Sdk
1) org.freedesktop.Sdk,24.08,x86_64,system  3) org.freedesktop.Sdk,25.08,aarch64,user	5) org.freedesktop.Sdk,25.08,x86_64,user
2) org.freedesktop.Sdk,24.08,x86_64,user    4) org.freedesktop.Sdk,25.08,x86_64,system
Select flatpak to enter or q to quit: 5
Entering flatpak org.freedesktop.Sdk
(Sdk-freedesktop-sdk-25.08.7) $
```

So, now at a shell prompt within the flatpak. In this example, an instance wasn't running, so the script started it.
