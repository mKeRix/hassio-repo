# 1.1.1

Made ble service compatible with Node 10. 

# 1.1.0

This release comes with a few added goodies that make room-assistant even more awesome! You do not need to change your configuration unless you were using the prometheus service before or you want to use the new features. More details can be found the [upgrade guide](https://github.com/mKeRix/room-assistant/wiki/Upgrade-Guide#10x-to-11x).

## New features

- [Omron D6T thermal sensors](https://github.com/mKeRix/room-assistant/wiki/Configuration#omron-d6t-sensors) can be used for accurate presence detection now
- [MQTT auto discovery](https://github.com/mKeRix/room-assistant/wiki/Configuration#general) removes the need for changing your Home Assistant configuration (available for gpio, shell and d6t)

## Changes

- general
  - updated dependencies
- ble
  - regex whitelists have been added, which allow you to configure allowable id patterns (as requested in #66)
  - measured power used for distance calculation can be overridden per device id (as requested in #58) 
- prometheus
  - uses framework-native solution now, required config changes are detailed in [upgrade guide](https://github.com/mKeRix/room-assistant/wiki/Upgrade-Guide#10x-to-11x)
- api
  - removed, as it is not needed anymore

# 1.0.1

A quick hot fix release that fixes some issues with the some configuration environment variables already being used by the system. Should mainly affect people running room-assistant directly with Node.js.

## Bugfixes

* changed configuration environment variables to not clash with system variables
  * `SHELL` is now `SHELL_COMMANDS`
  * `GPIO` is now `GPIO_PINS`

# 1.0.0

room-assistant 1.0 was rewritten from scratch.

If you are upgrading from a 0.x version please review the [upgrade guide](https://github.com/mKeRix/room-assistant/wiki/Upgrade-Guide).