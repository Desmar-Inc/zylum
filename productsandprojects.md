---
layout: page
title: Products and Projects
subtitle: A (short) list of our recent accomplishments
---

![zeppylin](/assets/img/steampunk-airship-20230608.png)
### Zeppylin *(Product)*
Zepplyin is a flexibly licensed, collaborative [Web Of Things](https://www.w3.org/WoT/) platform, designed to bridge the gap between purely cloud based offerings like [Amazon Sidewalk](https://aws.amazon.com/iot-core/sidewalk/) and the (largely) fragmented mix of open and closed source offerings like [chirpstack](https://www.chirpstack.io/) and [tago](https://tago.io/).

It is designed to be equally comfortable in the **cloud** (running inside an [EC2 Instance](https://aws.amazon.com/ec2/instance-types/) for example) or on the  **edge** (inside a  [Raspberry Pi](https://www.raspberrypi.org/) device).

----

![bdd](/assets/img/bdd_steampunk.png)
### Behavior-driven Development (BDD) for IOT *(Project)*       
A large US Based manufacturer of sensors/actuator that uses both proprietary and open [LPWAN](https://datatracker.ietf.org/doc/html/rfc8376) protocols in the field needed a way to validate the firmware that was running on their devices in an **end to end** fashion. They had already standardized on the [Behave](https://behave.readthedocs.io/en/latest/) Python Framework, as a way to add [BDD](https://en.wikipedia.org/wiki/Behavior-driven_development) to their existing [CI/CD](https://en.wikipedia.org/wiki/CI/CD) pipeline.

The team built and delivered a set of Behave Feature based Test [Scenarios](https://behave.readthedocs.io/en/stable/api.html?highlight=scenarios#behave.model.Feature.scenarios), that utilize both a client (which in turn connects to the hardware device via a USB/Serial Interface) and a server (which has both HTTP and Websocket interfaces).

----

![lora](/assets/img/steampunk-radio.png)
### Custom Lora implementation *(Project)*
The same US based manufacturer needed to move a custom [LoRa](https://www.semtech.com/lora/what-is-lora) implementation from an expensive 64-channel custom built by [Tektelic](https://tektelic.com/), built using 8 parallel [Sx1302](https://www.semtech.com/products/wireless-rf/lora-core/sx1302) transceivers, and costing over USD 10K, to more cost effective solution. 

The team refactored the legacy C code to run on a single [Corecell](https://www.semtech.com/products/wireless-rf/lora-core/sx1302cxxxgw1) device, bringing the cost down by a factor of at least 5X.

----

![lifecycle](/assets/img/robotic-animal-lifecycle.png)
### Firmware Lifecycle Management for [Helium](https://www.helium.com/) Gateways *(Product)*
> This work was carried out in part while the team was fully employed at a large Helium Gateway Fleet Operator.

One of the largest private fleet operators of Helium Gateways in the US was looking for a better way to provision and deploy Helium LoRaWan [Gateways](https://www.helium.com/lorawan).

The traditional model required that each device be unboxed, plugged in and then manually activated via a mobile app. This process was time consuming and error prone (not to mention expensive).

The team created a rust based low footprint client, which runs inside a balena container, which itself is part of a Balena firmware image. The image is set up to automatically connect and auto provision itself with a Balena Fleet.

The team also built a basic REST API (based on the python [fastAPI](https://fastapi.tiangolo.com/lo/) framework) for (pre) provisioning the devices, as well as also a simple Command Line Interface (CLI) which would enable the manufacturing partners to quickly and easily download the latest fleet firmware from the repository.
 
----

![building](/assets/img/steampunk-building.png)
### Fleet Management for Building IOT Gateways *(Project)*

A successful building management solutions company needed a way to better manage the way their Building Management IOT Gateways were managed. The Gateways were custom built by [phytec](https://www.phytec.com/), and ran a custom distribution of linux known as [phylinux](https://www.phytec.eu/en/leistungen/phybsp/phyline-sources/).

The team created a [yocto](https://www.yoctoproject.org/) workbench, which was used to (re)build the custom firmware image from sources. A set of new layers (and patches) were added to the build tree (to enable additional opkg based packages to be added to the base image). 

The team also leveraged the [rauc](https://rauc.io/) firmware OTA update framework, to enable the devices to be updated in the field. The [Bosch IOT Rollouts](https://bosch-iot-suite.com/service/rollouts/) framework was set up to manage and deploy full OS updates (using an A/B partitioning scheme) and the [barebox](https://www.barebox.org/) bootloader.

----

![factory](/assets/img/steel-pipe-factory.png)
### BLE Based Indoor Positioning System *(Product)*

A large steel pipe manufacturer needed a cost effective way to track employees on the factory floor. The system needed to be precise (sub 3 m accuracy), easy to deploy, unobtrusive and cost effective.

The team sourced BLE beacons from [blueup](https://www.blueupbeacons.com/) a leading manufacturer of BLE beacons, and then built a custom [Raspberry Pi](https://www.raspberrypi.org/) based gateway, which was then deployed in the factory. 

In addition, the team also deployed indoor BLE antennae from [Quuppa](https://quuppa.com/), which were used to triangulate the position of the beacons. 

The data was then sent to a custom [AWS](https://aws.amazon.com/) based cloud solution, which was then used to display the location of the employees on a custom [React](https://reactjs.org/) based dashboard.

----