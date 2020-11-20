# Make Esc great again

On my 2018 MacBook there's no Escape key, only touchbar, however using Apple's built-in [`hidutil`](https://developer.apple.com/library/archive/technotes/tn2450/_index.html) there's a way to change that, wiping useless `§` key out of existence in the process.

All that needs to be done is to add key mapping from `0x700000064` (`§`) to `0x700000029` (`Esc`).

Persistence is achieved using [`launchd`](https://www.launchd.info/), adding `local.EscKeyMapping.plist` to `~/Library/LaunchAgents`.

To restore default mappings remove `UserKeyMapping.plist` file from `~/Library/LaunchAgents` and run `hidutil property --set '{"UserKeyMapping":[]}'`.
