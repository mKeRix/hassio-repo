# room-assistant

room-assistant brings your home automation onto the next level: room automation. It is capable of tracking room occupancy and your location around the house with great accuracy, plus any other sensors you may want to attach. You can pick and choose the parts you need from our flexible software to get all the data you need for writing awesome new automations - room-assistant easily integrates them with your favorite home automation suite.

## Getting started

To get started with room-assistant on Hass.io you need to:

1. Add a new repository with the URL https://github.com/mKeRix/hassio-repo in the Add-on Store tab of the Supervisor panel.
2. Wait for it to refresh, then install room-assistant from the list on the same tab.
3. Change the `instanceName` in the options and configure all integrations that you need. You can find more information about all settings in the [official documentation](https://www.room-assistant.io/guide/configuration).
4. Start the add-on.

The connection to Home Assistant will be established automatically if you use one of the Hass.io MQTT add-ons.

## Known limitations

- On some Hass.io installations the auto-discovery functionality of the cluster may not work. This is primarily the case for manual Hass.io installations. You will see an error about this in the logs. In this case you need to [define the peers manually](https://www.room-assistant.io/guide/cluster#settings).