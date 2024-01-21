# Recommended Flatpak Apps
This list tries to filter out recommended Applications for everyday usage on Linux. It focuses on giving advice for Software following good practices.

If a piece Software is actually secure has to be decided per-app though, as it is a very complex task.

### Why this is needed
Flatpak's main purpose is to make every GUI app run on every Linux Distro.

The current state of the Linux Desktop is a mix between old reliable Software like Libreoffice & GIMP, and modern Development that focuses on Permissions, Portals, Wayland and more.

[Flathub](https://flathub.org/apps/collection/popular/1) has started to get a really good security rating system, but that has not arrived in every GUI software store on your Desktop.

Also you can't sort by the rating (yet) or exclude insecure apps.

It can also be a bit overwhelming, as device access may simply be needed for a platform like a browser to be user friendly.

<img src="https://github.com/trytomakeyouprivate/Recommended-Flatpak-Apps/assets/113100745/b0717916-5c9f-4aa7-aa8a-9cb205a48b07"
     width="400"
     height="400" />
     
So this list is a collection of Apps where maybe there is no alternative yet, and/or that follow best practices.

---

## [Web Browsers](https://github.com/trytomakeyouprivate/Recommended-Flatpak-Apps/blob/main/Apps/Browsers.md)
These are not yet recommended as Flatpaks and in general the most complex topic.

So they get an extra page.

## Mail Program: [Thunderbird](https://flathub.org/apps/org.mozilla.Thunderbird)
Thanks to a good campaign Thunderbird is back on track, modernizing their old code and making the App look modern.

Thunderbird is based on Firefox ESR, just like the Torbrowser. This means we can assume it gets all Security Fixes of Firefox, and benefits by the Firefox project a lot.

It is the only feature-complete and widely used Mail program with easy support for [OpenPGP](https://www.openpgp.org/), and I highly recommend you to learn its basics! (A PGP tutorial will be added on time).

Anyways, Thunderbird is not perfectly secure out of the box, so you may want to apply the [Thunderbird hardening settings](https://github.com/HorlogeSkynet/thunderbird-user.js).

This will have some drawbacks, and a middleway is needed, that allows
- Local timezone
- Extension installs
- Calendar Event Adding

This may be possible to apply using an [override](https://github.com/arkenfox/user.js/wiki/3.1-Overrides), or by splitting up the hardening user.js into seperate groups, depending on your use case.

The Hardening configuration is a deviation of the [Arkenfox userjs](https://github.com/arkenfox/user.js), which is a security & privacy Configuration set for Firefox. As a Mail program is often used differently (you only contact people you know and mostly in the same timezone) your requirements may be different.

### Addons
You should not install dozens of Addons, but some are really useful.
- [Thunderbird Conversations](https://addons.thunderbird.net/en-US/thunderbird/addon/gmail-conversation-view): Useful threads for mail exchange with the same person or group. Sometime in the future this will become native to Thunderbird, and this addon obsolete.
- [DKIM Verifier](https://addons.thunderbird.net/en-US/thunderbird/addon/dkim-verifier/): Very important, it shows a Warning if the mail origin may be manipulated.
- [QuickText](https://addons.thunderbird.net/en-US/thunderbird/addon/quicktext): Fill in snippets like greetings or closings
- [Nextcloud Attachments](https://addons.thunderbird.net/en-US/thunderbird/addon/filelink-nextcloud-owncloud): This addon allows to send attachments via your FOSS cloud storage, to work with attachment size limitations and save data. May also support password-protected file sharing (only secure when using PGP!)

Theoretically you can install most Firefox addon files manually. ("Dark Background & Light Text", "Firefox Translations" & Snowflake do not work)

Also: The Fork "Betterbird" is no longer needed for features like the "card view" that got integrated into Thunderbird. It also may be behind on updates.

## Messenger
Most popular messengers are way more secure than Mail, phone calls or SMS. 

### Matrix
Element, Syphon, Fluffychat

### XPP
Dino, Gajim

### Signal, Threema
Signal, Flare, Threema

### Warnings
Mixin, Session, Telegram & Clients

## Image Viewers
### [GNOME Loupe](https://flathub.org/apps/org.gnome.Loupe)
- very secure, sandboxed SVG display, written in Rust
- nearly no features
- unrestricted filesystem access by default, but can use portals
- no saving needed because it can't do any editing
- some lacking view features like "fit image to size"

### [KDE Gwenview](https://flathub.org/apps/org.kde.gwenview)
- written in C++, probably less secure
- unrestricted filesystem access by default, can only open but not save files through the portal
- small amount of editing features you may want
- good viewing settings

## Video Player
### [Celluloid](https://flathub.org/apps/io.github.celluloid_player.Celluloid)
- MPV frontent with Wayland support
- Uses portals for opening files
- Keyboard shortcuts
- some theme issues, opinionated GTK Design

### [VLC](https://flathub.org/apps/org.videolan.VLC)
- not yet official, but very well done
- doesn't use portals, needs broad filesystem access
- 4.x is still in Beta, bringing a new Interface (only install way currently is through the Ubuntu PPA, works through Distrobox flawlessly)
- very complex media suite, not only a player
- very customizable, but most extensions & themes don't work anymore

## Music Player
You may just use your video player. Otherwise:

### [G4Music](https://flathub.org/apps/com.github.neithern.g4music)
- little static permissions
- can use portal for default directory
- supports Pipewire and other outputs
- feature rich, artist view, albums, no playlist support

### [Amberol](https://flathub.org/apps/io.bassi.Amberol)
- Little static filesystem permissions
- uses portals to open more directories or files
- No folders, playlists, ...
- best in combination with a File Manager

### [Strawberry](https://flathub.org/apps/org.strawberrymusicplayer.strawberry)
- old App, static and broad permissions
- very feature rich
- native Wayland support through Qt

## PDF Viewers
### Browser
Your Browser can view and even edit PDFs!
In Firefox when not using Arkenfox / Librewolf make sure

`pdfjs.enableScripting = false` in `about:config`

### KDE Okular
- feature rich PDF viewer
- some editing capabilities
- completely unrestricted filesystem permissions
- Internet Permission
- can use the Portal for opening and saving files without any problems

### GNOMEs Evince
- has filesystem Access by default
- can use the Portal for opening
- also for saving PDFs, but you always need to specify the location.

## System

### [Flatseal](https://flathub.org/apps/com.github.tchx84.Flatseal)
If you are not on KDE, this is an essential tool to manage Flatpak Permissions easily.

### [Mission Center](https://flathub.org/apps/io.missioncenter.MissionCenter)
- Features similar to Windows' Task Manager.
- Only needed permissions

### [Firmware](https://flathub.org/apps/org.gnome.Firmware)
Not needed when using KDE Discover, but useful on other Desktops.

Displays your firmware versions. In the end nothing more than

```
fwupdmgr get-devices
fwupdmgr upgrade
```

### [Inspector](https://flathub.org/apps/io.github.nokse22.inspector)
- shows low-level details about your System and Hardware
- has minimal permissions

## Office
### Handwritten Notes
[RNote](https://flathub.org/apps/com.github.flxzt.rnote)
- pretty modern
- some Filesystem permissions, but works completely without using Portals


[Xournal++](https://flathub.org/apps/com.github.xournalpp.xournalpp)
- permissions get better Flatpak adaption
- no filesystem portal support currently


### Libreoffice
is the only complete Office Suite for easily editing WYSIWYG (what you see is what you get) Documents.
- huge and old codebase
- incompatible with portals currently ([Issue](https://bugs.documentfoundation.org/show_bug.cgi?id=159311)

### Alternative Solutions
#### Text Editing
**[Typst](https://typst.app)**
- Install locally using cargo (Rust package manager)
- Support for [VSCodium](https://flathub.org/apps/com.vscodium.codium) is currently best
- Modern LaTeX alternative, with easier syntax and fancy features like incremental updates

**Markdown**
- Many available Editors, [search on Flathub](https://flathub.org/apps/search?q=markdown)

**LaTeX**
- often old applications
- [Setzer](https://flathub.org/apps/org.cvfosammmm.Setzer) using GTK, [Kile](https://flathub.org/apps/org.kde.kile) using Qt
- both have native Wayland support

**Good general Text Editors**
- [VSCodium](https://flathub.org/apps/com.vscodium.codium) uses a Microsoft codebase but has tracking removed. The Flatpak is unofficial and has limited features
- Kate by KDE, currently only [Kwrite](https://flathub.org/apps/org.kde.kwrite) (a subset of Kate) is on Flathub
- [Lapce](https://flathub.org/apps/dev.lapce.lapce): modern, but work in progress editor, [Website](https://lapce.dev/#)

#### Presentations
You may just use PDFs for presenting, which can open everywhere.

Creating those can be done using Markdown, LaTeX and more. You may want to use [Pandoc](https://pandoc.org), which has no GUI and thus no Flatpak.

#### Calculations
No tool is as complete and easy to use as Libreoffice Calc

#### Draw
- GIMP: legacy application which stuggles to use GTK 3, currently no Wayland or portal support
- Krita: less image editing features than GIMP, focused towards drawing. No Wayland support currently.
- Inkscape: modern application, no portal support because of specific requirements

## File Encryption
### Cryptomator
Tool optimized for encrypting cloud synced files.

You can restrict it's storage permission to the Cloud storage folder you use.

## Password Management
### [GNOME Secrets](https://flathub.org/apps/org.gnome.World.Secrets)
- possible replacement for KeepassXC
- using portals, no permissions except inter-process-communication
- Wayland support

### [KeepassXC](https://flathub.org/apps/org.keepassxc.KeePassXC)
- unrestricted filesystem access, no portals; needs to be modified
- Wayland support
- currently no support for Autotype on Wayland
- The lack of a "native messaging" portal prevents it form autofilling passwords in your browser

### Bitwarden: [Goldwarden](https://flathub.org/apps/com.quexten.Goldwarden)
- no filesystem access
- Wayland support
- written in Go

### OTP Apps
- [OTPClient](https://flathub.org/apps/com.github.paolostivanin.OTPClient)
- [Authenticator](https://flathub.org/apps/com.belmoussaoui.Authenticator): written in Rust, using a Ruby Library
- [Keysmith](https://flathub.org/apps/org.kde.keysmith)

Note: Device Access may be wanted for password managers and OTP Generators, to access hardware keys such as 
- [Nitrokey](https://www.nitrokey.com/)
- [Solokeys](https://leetronics.de/en/shop/)
- [Onlykey](https://onlykey.io/)


## Synchronisation & Backups
### [Syncthingy](https://flathub.org/apps/com.github.zocker_160.SyncThingy)
- Very configurable
- peer-to-peer Synchronisation without a Server!
- unrestricted Filesystem Access, not using Portals: it has to be limited manually

### [Nextcloud Desktop](https://flathub.org/apps/com.nextcloud.desktopclient.nextcloud)
- unrestricted filesystem access, not using Portals: it has to be limited manually
- not an official Flatpak


Notes:
- many local backup Flatpaks need to be configured manually!
- use Cryptomator for encryption if you don't trust your provider

### [Cryptomator](https://flathub.org/apps/org.cryptomator.Cryptomator)
- unrestricted filesystem access, not using Portals: it has to be limited manually
- no Wayland support
- needed directories:

```
~/.local/share/ : create
~/.local/share/Cryptomator/ : read/write

# + any directory where you want your encrypted files
```

## File sharing
### [LocalSend](https://flathub.org/apps/org.localsend.localsend_app)
- great cross-platform tool for filesharing over Wifi
- minimal permissions, static Download folder, no portal usage
- Wayland support

### [Warp](https://flathub.org/apps/app.drey.Warp)
- modern app for filesharing over the internet
- Wayland support
- using portals, download folder access can be removed
- written in Rust

## Screen recording / Streaming
### [OBS Studio](https://flathub.org/apps/com.obsproject.Studio)
- only good screen recording software on Wayland
- screenshare portal support
- filesystem access unrestricted, no portal support

## [Blue Recorder](https://flathub.org/apps/sa.sy.bluerecorder)
- working on Wayland support, currently only X11 support
- default filesystem access unrestricted
- screenshare & filesystem portal
- unofficial Flatpak

## Tools
### [Decoder](https://flathub.org/apps/com.belmoussaoui.Decoder)
Modern QR Code Scanner
- using portals
- written in Rust

Problem: saves history with no off-switch. Fix: Delete the App storage after closing it by editing its Desktop entry:

```
cd ~/.local/share/applications
# copy Desktop Entry
cp /var/lib/flatpak/app/com.belmoussaoui.Decoder/current/active/export/share/applications/com.belmoussaoui.Decoder.desktop ./
# make the App delete its storage after closing
sed -i 's/--command=decoder com.belmoussaoui.Decoder/--command=decoder com.belmoussaoui.Decoder && rm -rf $HOME/.var/app/com.belmoussaoui.Decoder/g' com.belmoussaoui.Decoder.desktop
```

### [Impression](https://flathub.org/apps/io.gitlab.adhami3310.Impression)
An easy tool for flashing ISO images to USB flashdrives
- no filesystem permissions, using portals
- written in Rust, using udisks2 from the freedesktop.org runtime
