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
You should not pile Addons to any Program, but some are really useful.
- [Thunderbird Conversations](https://addons.thunderbird.net/en-US/thunderbird/addon/gmail-conversation-view): Useful threads for Mail Exchange with the same person. Sometime in the Future this will become native to Thunderbird, and this Addon obsolete.
- [DKIM Verifier](https://addons.thunderbird.net/en-US/thunderbird/addon/dkim-verifier/): Very important, it shows a Warning if the mail origin may be manipulated.
- [Display Mail User Agent](https://addons.thunderbird.net/en-US/thunderbird/addon/display-mail-user-agent-t): Shows more information about the sender if you click on the "i" button.
- [QuickText](https://addons.thunderbird.net/en-US/thunderbird/addon/quicktext): Fill in Snippets like Greetings or Closings
- [Nextcloud Attachments](https://addons.thunderbird.net/en-US/thunderbird/addon/filelink-nextcloud-owncloud): This addon allows to send attachments via your FOSS cloud storage, to work with attachment size limitations and save data.

Theoretically you can install most Firefox addon files manually. (Dark Background Light Text, Translations & Snowflake do not work)

Also: The Fork "Betterbird" is no longer needed for features like the "card view", that got integrated into Thunderbird. It also may be behind on Updates.

## Messenger

### Matrix
- Element, Syphon, Fluffychat

### XPP
- Dino, Gajim

### Signal, Threema
- Signal, Flare, Threema

### Warnings
Mixin, Session, Telegram & Clients

## Image Viewers
GNOME Loupe
- very secure, sandboxed, written in Rust
- nearly no Features
- some lacking View features like "fit image to size"

KDE Gwenview
- written in C++, probably less secure
- small amount of editing features you may want
- good viewing Settings

## Video Player
Celluloid
- MPV frontent with Wayland Support
- Keyboard shortcuts
- some theme issues, opinionated GTK Design

VLC
- not yet official, but very well done
- 4.x is still in Beta, bringing a new Interface (only install way currently is through the Ubuntu PPA, works through Distrobox flawlessly)
- very complex media suite, not only a Player
- very customizable, but most Extensions & Themes don't work anymore

## Music Player
You may just use your Video Player. Otherwise:

G4Music
- little static permissions
- can use Portal for default directory
- supports Pipewire and other outputs
- feature rich, Artist view, albums, no Playlist support

Amberol
- Little static Filesystem Permissions
- uses Portals to open more Directories or Files
- No Folders, Playlists, ...
- best in combination with a File Manager

Strawberry
- old App, static and broad permissions, no Portal usage
- very feature rich

## PDF Programs
Your Browser can view and even edit PDFs!
In Firefox when not using Arkenfox / Librewolf make sure

`pdfjs.enableScripting = false` in `about:config`

KDE's Okular is a feature rich PDF viewer with some Editing Capabilities. It has completely unrestricted filesystem permissions by default, as well as Internet Permission. But it can use the Portal for opening and saving files without any problems.

GNOME's Evince can be used without any static Filesystem Permissions (opening Files from your Filemanager, from the App using the Portal) but has filesystem Access by default. The portal also works for saving Edits, but you always need to specify the location.

## System

## Office
- Libreoffice

## Education

## Internet

## Synchronisation
- Syncthingy
- LocalSend
- Nextcloud
- Cryptomator

## Development
