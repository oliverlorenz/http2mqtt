# http2mqtt

This is simple as possible! 

* connects to a MQTT Broker
* Starts a webserver 
* takes http request path as topic and body as payload for MQTT
* Works with GET and POST method
* Prepared to use with Docker 

## usage

Start server:

```
docker run -it --rm -p 9001:9001 oliverlorenz/http2mqtt
```

Connect MQTT client:

```
mosquitto_sub -h test.mosquitto.org -t "my/mqtt/topic"
```

Then open up your browser and type in:

```
http://localhost:9001/my/mqtt/topic
```

You will receive a "null" message in the client because, you don't send a payload. If you send payload, it will be visible there.

### Configuration

You can configure the project by using this environment variables

|| Environment Variable || default ||
|| BROKER_URL| mqtt://test.mosquitto.org |
|| TOPIC_BASE |  |
|| HTTP_PORT | 9001 |
|| MQTT_USERNAME |  |
|| MQTT_PASSWORD |  |


