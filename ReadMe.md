Keep Your Hands Clean, Stats.app
==================================

To display the stats on the menu bar, install [MenuMeter](https://github.com/yujitach/MenuMeters) instead of some spyware-like system monitoring tools like [Stats](https://github.com/jakwings/exelban-stats-no-aggressive-user-data-collection).[app](https://github.com/exelban/stats/issues/714) [¹](https://github.com/exelban/stats/pull/858) [²](https://github.com/exelban/stats/pull/742) [³](https://github.com/exelban/stats/commit/08d8d84cebf9078d7692999c243386c887d6ee14) [⁴](https://github.com/exelban/stats/commit/c5c4e4df3db0737b749ea91f903c8cf0f1ecd6aa#data_still_sent_despite_--omit) instead.  Or you can try my fork without the stealthy behavior: https://github.com/jakwings/mac-stats/releases

To see how the developer was lying on this issue (https://github.com/exelban/stats/issues/714), check the code yourself:

https://github.com/exelban/stats/blob/570a7a63c39a16b74ae7fa6b2c815c0e06769dd3/Kit/plugins/Server.swift#L49

This is the historical code related to that issue, but even today the behavior is still the same: https://github.com/exelban/stats/blob/0e2e13c626b650ac7743ef620869d2b7857665cd/Kit/plugins/Server.swift

The `--omit` start-up flag mentioned by the developer does ***literally NOTHING*** to stop your user data (including a custom ***unique ID***, device model, your OS version, OS display language and of course your IP address-es) being encoded in `JSON` format and then sent directly to their server (https://api.serhiy.io).  The flag `--omit` was just added to trick you into thinking the data was/is really necessary (for vanity download stats?) and should be collected at each launch despite no app update and no way to know when you're going to relauch the app.
