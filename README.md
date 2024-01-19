# Recommended Flatpak Apps
This list tries to filter out recommended Applications for everyday usage on Linux. It focuses on giving advise for Software following good practices.

If it is actually secure has to be decided per-app though, as it is a very complex task.

### Why this is needed
Flatpaks main purpose is to make every GUI app run on every Linux Distro.

The current state of the Linux Desktop is a mix between old reliable Software like Libreoffice, GIMP, and modern Development that focuses on Permissions, Portals, Wayland and more.

[Flathub](https://flathub.org/apps/collection/popular/1) has started to get a really good security rating system, but that has not arrived everywhere. Also you can't sort by it (yet) or exclude insecure apps. It can also be a bit overwhelming, as device access may simply be needed for a platform like a browser to be user friendly.

<img src="https://github.com/trytomakeyouprivate/Recommended-Flatpak-Apps/assets/113100745/b0717916-5c9f-4aa7-aa8a-9cb205a48b07"
     width="400"
     height="400" />
     
So this list is a collection of Apps that are needed. Maybe there is no alternative yet, that follows best practices. But at least you can get the most secure one of those.

---

## [Web Browser](https://github.com/trytomakeyouprivate/Recommended-Flatpak-Apps/blob/main/Apps/Browsers.md)
These are not yet recommended as Flatpaks and in general the most complex topic.

## Mail Program: [Thunderbird](https://flathub.org/apps/org.mozilla.Thunderbird)
Thanks to a good campaign Thunderbird is back on track, modernizing their old Code and making the App look Modern.

Thunderbird is based on Firefox ESR, just like the Torbrowser. This means we can assume it gets all Security Fixes of Firefox, and benefits by the Firefox Project a lot.

It is the only feature-complete and widely used Mail program with easy support for [OpenPGP](https://www.openpgp.org/), and I highly recommend you to learn its basics! (A PGP tutorial will be added on time).

Anyways, Thunderbird is not perfectly secure out of the box, so you may want to apply the [Thunderbird hardening settings](https://github.com/HorlogeSkynet/thunderbird-user.js).

This will have some drawbacks, and a middleway is needed, that allows
- Local timezone
- Extension installs
- more?

This may be possible to apply using an [override](https://github.com/arkenfox/user.js/wiki/3.1-Overrides), but it is not yet integrated in the project. The Hardening is a deviation of the [Arkenfox](https://github.com/arkenfox/user.js), which is a security & privacy Configuration set for Firefox. As a Mail program is often used differently (you only contact people you know and mostly in the same timezone) the hardening may be too much.

### Addons
You should not pile Addons to any Program, but some are really useful.
- [Thunderbird Conversations](https://addons.thunderbird.net/en-US/thunderbird/addon/gmail-conversation-view): Useful threads for Mail Exchange with the same person. Sometime in the Future this will become native to Thunderbird, and this Addon obsolete.
- [DKIM Verifier](https://addons.thunderbird.net/en-US/thunderbird/addon/dkim-verifier/): Very important, it shows a Warning if the mail origin may be manipulated.
- [Display Mail User Agent](https://addons.thunderbird.net/en-US/thunderbird/addon/display-mail-user-agent-t): Shows more information about the sender if you click on the "i" button.
- [QuickText](https://addons.thunderbird.net/en-US/thunderbird/addon/quicktext): Fill in Snippets like Greetings or Closings
- [Nextcloud Attachments](https://addons.thunderbird.net/en-US/thunderbird/addon/filelink-nextcloud-owncloud): This addons allows to send attachments via your FOSS cloud storage, to work with attachment size limitations and save Data.

Theoretically you can install most Firefox Addon Files manually. (Dark Background Light Text, Translations & Snowflake do not work)

Also: The Fork "Betterbird" is no longer needed for many back then unique features like the "card view". It also may lack behind on Updates.

## Messenger
- Element, Syphon, Fluffychat: Matrix
- Dino, Gajim: XMPP
- Signal, Flare, Theema: closed Ecosystems

Warnings: Mixin, Session, Telegram & Clients

## Image Viewers
- Loupe
- Gwenview
## Video Player
- Celluloid
- VLC

## Music Player

## PDF Programs
- your Browser
- Okular

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
