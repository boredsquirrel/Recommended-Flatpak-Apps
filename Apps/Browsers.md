## Web Browsers
are the only exception of this list. [The Situation is complex](https://discuss.privacyguides.net/t/does-flatpak-weaken-chromium-firefoxs-sandbox/13373/1) [but currently Flatpak Browsers are less secure](https://seirdy.one/notes/2022/06/12/flatpak-and-web-browsers/).

The Flatpak Sandbox restricts the Browsers abilities to isolate the processes from another, and also valuable internal data like your history or passwords.

So, if your Distribution has updated packages, use the repositories version. This does not count for Debian or other "stable" Distros, as these packages are all outdated and not all bugfixes can be backported.

Web Browsers have a security vs. Privacy problem. Chromium is assumed more secure, while Firefox grants more user Freedom and Privacy (especially in the Manifest v3 Future). There are many different opinions here though, Firefox has core components rewritten in Rust, while Chromium focuses on sandboxing or processes.

Both Firefox and Chromium support Wayland natively now, which took Chromium way too long but this makes them even.

### Firefox
Firefox is most likely preinstalled on your System. It is mostly untouched though, and not a privacy browser out of the box.
It is reasonably secure for most users, and using some tweaks in the graphical settings and the Addons
[UBlock Origin](https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/), [NoScript](https://addons.mozilla.org/en-US/firefox/addon/noscript/), as well as more specialized ones like
[Canvas Fingerprint Defender](https://addons.mozilla.org/en-US/firefox/addon/canvas-fingerprint-defender/), [WebGL Fingerprint Defender](https://addons.mozilla.org/en-US/firefox/addon/webgl-fingerprint-defender/) and [User Agent Switcher](https://addons.mozilla.org/en-US/firefox/addon/uaswitcher/) in "random" mode can help to mimic Braves random Fingerprint abilities.

Securitywise, Firefox is okay, probably. With v121 they are Wayland by default, and it can use portals. But regularly you have to trust it a lot, especially as Flatpaks are probably less secure, no matter if their Flatpak is officially supported.

If your Distro does not have updated packages, you can simply download the Firefox Archive and create your own Desktop entry. It will update itself and be optimized to run on Linux.

If you want to harden Firefox yourself, to reduce its attack surface a bit and improve privacy a lot, use [Arkenfox](https://github.com/arkenfox/user.js).

[This project](https://github.com/trytomakeyouprivate/Arkenfox-softening/) makes it easy to download and apply your own changes, but it needs testing!

#### [Librewolf](https://librewolf.net/installation/)
This is the best Fork of Firefox currently. It is available as Flatpak, but you should use a native package, which are available for many distros, and as a universal binary!

Librewolf adds nice graphical additions for privacy settings, and out of the box it is a private Browser.

#### Mullvad Browser
Not being a bad Browser, having the fingerprint protection of TorBrowser, it uses private Browsing just like it,
while not using the Tor Proxy. So it is not anonymous, but just as unconvenient as TorBrowser.

Just use Librewolf.

### [TorBrowser](https://www.torproject.org/download)
While this is also available as a Flatpak, you may want to install the official Archive.

The Torbrowser is based on Firefox ESR for stability reasons. ESR gets all security bugs backported, you may argue that not every bug is correctly labelled as security sensitive though.

Torbrowser has a strong focus on privacy, but the enforced "Private Browsing" makes it very user friendly, as it deletes everything you do.
Disabling "private Browsing" can be detected, so do not do it!

You can install [UBlock Origin](https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/) on the Browser, as well as [Add Custom Search Engine](https://addons.mozilla.org/en-US/firefox/addon/add-custom-search-engine/) (which is probably okay) and [add a few search engines!](https://github.com/trytomakeyouprivate/Search-Engines/blob/main/Tor-Search-Engines.md)

Be aware that adding region-specific Filterlists may be detectable, and do not install "privacy addons" on the Browser, as its goal is a small and unified fingerprint, not randomization.

#### Installation

[First download the Signature, then the Archive from this website.]

![Screenshot of Download Page](...)

You need to verify the download using these commands:
```
gpg --auto-key-locate nodefault,wkd --locate-keys torbrowser@torproject.org
gpg --verify /home/user/Programs/Browser/tor-browser-linux-x86_64-x.x.x.tar.xz.asc
```

if you get this output, you can proceed:

```
gpg: assuming signed data in 'tor-browser-linux-x86_64-13.0.8.tar.xz'
gpg: Signature made Thu 21 Dec 2023 02:29:32 PM CET
gpg:                using RSA key 613188FC5BE2176E3ED54901E53D989A9E2D47BF
gpg: Good signature from "Tor Browser Developers (signing key) <torbrowser@torproject.org>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
```

The important part is the "Good Signature". Now unpack the Archive, delete it and go into it, where you see the folder "Browser" and the File "start-tor-browser.desktop".

Open a Terminal here and run `./start-tor-browser.desktop --register-app`. Now the Brower will appear in your App Menu.

### Chromium
Chromium may come from your repositories and thus automatically updates (something nonexisting on Windows!). The updates may not be on time though, and there is no official binary repository by Google.

Also, Chromium is a rolling release, being upstream of Chrome, so it has to be considered as "testing" and versioning is a task of the packagers or downstream projects like Chome, Edge, Brave or Vivaldi.

Ungoogled Chromium is a variant that actually removes telemitry and tracking by Google. Chromium lacks many features of Chrome, but still sends loads of Data to Google.

Chromium is not optimized at all to protect against Website Fingerprinting. There are different stands on the topic, and a general "unified vs. randomized" debate.

There are some ways to download the latest binaries
- [One-Click Website](https://download-chromium.appspot.com/?platform=Linux_x64)
- [Download and run Script](https://github.com/scheib/chromium-latest-linux)
- [Woolyss' Website, seems to be ungoogled Chromium](https://chromium.woolyss.com/#linux)

To run certain packages of Chromium through Wayland you may need to add `--ozone-platform=wayland` at the end of its `Exec=` line like this:

```
cp /usr/share/applications/chromium.desktop ~/.local/share/applications/chromium.desktop
$EDITOR ~/.local/share/applications/chromium.desktop
```

The local Desktop Entry will display instead of the system one. This should not be necessary anymore though, as Wayland is now officially supported.

### Brave
Brave is a fork of Chromium, that adds many privacy optimizations.
It is often critizised for some "bloat" it brings, like
- BAT (Brave Attention Token) system
- Crypto Wallet Builtin
- Brave News
- non-local Translations, still having popups
- Leo AI integration
- Dependency on the Chromium Web Store

But similar to Firefox, these Features can be disabled, and you can use policies and config files to preset `brave://flags`. This is not well documented on Linux though, we can hope that this improves.

It seems that Brave reads `/etc/chromium/` if `/etc/brave/` is missing.

Its strengths are
- builtin Adblocking
- accountless E2EE (end to end encrypted) synchronisation
- Randomization of User Identifiers for Anonymity
- Builtin IPFS, Tor and Bittorrent support
- continued support for Manifest v2 Addons (allows Addons to download Data, e.g. Adblock/Malware Filterlists)

Brave has [repositories for many Distros](https://brave.com/linux/#release-channel-installation), which is the recommended way of installing.

The Flatpak is currently very insecure, using [zypak](https://github.com/refi64/zypak) to replace the tab isolation Sandbox, weakening it.

Brave is a deviation of Chromium. It may lack behind on security features, where especially Edge with its "[Super Duper Secure Mode](https://microsoftedge.github.io/edgevr/posts/Super-Duper-Secure-Mode/)" made some hardening like disabling WebAssembly JIT compilation very accessible.

You can disable JIT compilation in Brave by adding `--js-flags=--jitless` to its `Exec=` line, similar to the general Chromium override.
