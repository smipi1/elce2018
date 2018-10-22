# Open Source MQTT Brokers - Leon Anavi, Konsulko Group

## Brief history

### Intro

* Lightweight pubsub M2M protocol over TCP/IP
* Near real-time comm between clients via broker
* Small source code footprint
* Protocol versions:
** 3.1
** 3.1.1
** 5.0
* MQTT-SN (Sensor Networks): Out-of-scope

### Milestones

* Created 1999
* Roalty free since 2000

### Trends

* Rising Google search since 2014

## Protocol deep-dive

### Operations

* Connect
* Disconnect
* Subscribe
* Unsubscribe
* Publish

### Role of broker

Connect / handle clients

Deliver messages based on topic

### Message

* Topic
* Payload
* QoS
* Retain (True / False)

### QoS

* 0: At most once (no delivery guarantee)
* 1: At least once
* 2: Exactly once

### Retained messgaes

Stores last known good value
Broker relays retained messages to new subscribers
To delete retained message, pub new message w.o. payload

### LWT

Broker will relay on disconnect on behalf of client
Must be Specced on connect

### Topics & Wildcards

* Topic
    home/bedroom/temperature
* Single level wildcards
    home/+/temperature
* Multi-level
    home/#

### Security

* TLS/SSL
* Authentication: username/password
* Authorization: ACL

### Version 5

* Improved provisioning for large scale
* Metadata, user properties
* Req / res
* 0x04 -> 0x05 in header

## Popular OSS Brokers

### Mosquitto

* FOSS broker
* C-based
* 3.1 and 3.1.1
* QoS 0, 1 and 2
* Websockets
* Command-line clients
** `mosquitto_pub`
** `mosquitto_sub`

Pulse:
* Started 2010 by Roger Light
* iot.eclipse.com
* Git since 2014
* Sponsored by Cedalo AG since 2018
* Github: Dual-license: Eclipse Public License / Eclipse Distribution License

### Mosca

* FOSS broker
* node.js
* 3.1 and 3.1.1
* Websockets
* QoS 0 and 1

Pulse:
* Github
* MIT
* Matteo Collina, 2013
* 56 contribs (mostly author)
* 2K downloads / week on npm

### EMQ (emqttd)

* FOSS broker
* 3.1, 3.1.1 and 5.0
* QoS 0, 1, 2

Pulse:
* Github
* Apache 2.0
* Feng Lee, 2012
* Enterprise support

### VerneMQ

* Erlang
* 3.1 - 5.0
* QoS 0, 1, 2
* Websockets

Pulse:
* Github
* Apache 2.0
* 2016, 2 Authors
* Commercial support

### Apache ActiveMQ

* Large number of protocols:
** MQTT
** OpenWirte
** STOMP
** AMQP
** ...
* 3.1
* QoS 0 - 2

Pulse:
* Apache 2.0
* Git
* 2004 - 2007 private
* 2007 - Donated to Apache

### RabitMQ

* Erlang
* Many protocols:
** MQTT
** STOMP
** AMQP
** HTTP
* 3.1
* QoS 0,1

Pulse:
* Github
* Mozilla Public License 1.1
* 2007 - 

### HiveMQ

* Not open-source
* Java
* 3.1, 3.1.1
* Websockets

### Others

* ActiveMQ
* Moquette
* Vertx-mqtt-broker
* ...

## Clients

### Paho

* C/C++
* Jave,
* Javascript,
* Python,
* Go,
* Rust, and
* C#

## Notes, conclusions, discussions

* Excellent protocol for (near) real-time
* Huge variety of high Q FOSS brokers
** Including commercial support
* All brokers highly dependent on authors (remain lead developers)
* Most popular languages for implementing brokers:
** Erlang/OTP
** Java
** C
* All run on GNU/Linux

## Demo

...

