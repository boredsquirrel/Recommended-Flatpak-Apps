## Thunderbird hardening

This is a slight modification of [the Thunderbird hardening user.js](https://github.com/HorlogeSkynet/thunderbird-user.js).

It may be incomplete, in the end I will add my list of changes and a script to automatically apply them to the upstream user.js to prevent outdated settings.

Load it into your Browser by placing it in your profile folder
- Flatpak: `~/.var/app/org.mozilla.Thunderbird/.thunderbird/xxxx-default-release/`
- Native: `~/.thunderbird/xxxx-default-release/`

Problems:
- Addons not installing, instead prompting a download (they can still be installed from File). Checked:
  - [x] disabled `user_pref("privacy.resistFingerprinting.block_mozAddonManager", false)`
  - [x] disabled RFP 
