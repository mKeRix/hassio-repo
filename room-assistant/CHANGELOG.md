# 1.0.1

A quick hot fix release that fixes some issues with the some configuration environment variables already being used by the system. Should mainly affect people running room-assistant directly with Node.js.

## Bugfixes

* changed configuration environment variables to not clash with system variables
  * `SHELL` is now `SHELL_COMMANDS`
  * `GPIO` is now `GPIO_PINS`

# 1.0.0

room-assistant 1.0 was rewritten from scratch.

If you are upgrading from a 0.x version please review the [upgrade guide](https://github.com/mKeRix/room-assistant/wiki/Upgrade-Guide).