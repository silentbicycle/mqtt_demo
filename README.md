This is a small example using [mosquitto]'s [MQTT] client library.

It creates a client that connects to an MQTT broker at localhost:1883
(if running), then subscribes to the topics `tick`, `control/#{PID}`,
and `control/all`. Every time it gets a `tick` message via the `tick`
topic, it publishes its pid and uptime on `tock/#{PID}`. If the message
`halt` is received on `control/all` or `control/#{PID}`, the client will
free its resources and halt.

Note: If you are running a Linux distribution that uses apt-based
packaging (e.g. Debian or Ubuntu) you may need to install the `-dev`
packages as well as the basic mosquitto packages to get the headers.

[mosquitto]: http://mosquitto.org
[MQTT]: http://mqtt.org/
