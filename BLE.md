---
date updated: '2021-10-15T11:14:59+02:00'

---

Topic: #iot #bluetooth #wireless
Tags: #review #pn_2
Links: [[IoT]]
Date Created: 15-10-21

---

# BLE

## BLE in few words

## BLE in details

### BLE History

Designed by Nokia as Wibree, then adopted by the **Bluetooth Special Interest Group** (SIG).
The focus was on a wireless technology

- low power consumption
- low cost
- low bandwidth
- low power
- low complexity

The success of BLE explained itself as

- Apple => approved & invested money
- more demand for connectivity

### What Makes BLE Different

- Small
- Budget friendly (2$ chip in low volume > WiFi, GSM, Zigbee)
- It talks to [[Smartphone]], therefore might be better for user experience
- Easy-to understand data model
- No license cost
- No fees for core specs
- Lean protocol stack

### The Specification

Bluetooth SIG introduced [[BLE]] with version 4.0 of [[Bluetooth]] core specification.

### Based on Count Chip

A Bluetooth device is composed of

- [[Bluetooth - Application]]
- [[Bluetooth - Host]]
- [[Bluetooth - Controller]]

The 3 most common configurations are:

- SoC (system on chip): a single [[IC]] runs the application, the host and the controller
- Dual IC over HCI
  - One IC => [[Bluetooth - Application]] & [[Bluetooth - Host]]
  - One IC => [[Bluetooth - Controller]] => defined by the [[Bluetooth]] specification => more compatibility
- Dual IC with connectivity device
  - One IC => [[Bluetooth - Application]]
  - One IC => [[Bluetooth - Controller]] & [[Bluetooth - Host]]

![[Pasted image 20211015103128.png]]

### Key Limitations

#### Data Throughput

Constant 1Mbps is in reality much lower ~0.125 Mb/s

#### Operating Range

-30 -> 0 dbm transmit power
30 m -> line-of-sight
2~5 m operating range

## References

### Direct References

- [[@townsenkevincuficarlesakibadavidsonrobertGettingStartedBluetooth2014]]

### Parent References

- [[IoT#References]]
