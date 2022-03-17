---
description: Also known as CAN or the CAN Bus.
cover: >-
  https://images.unsplash.com/photo-1602845686963-0085ac4a8dcd?crop=entropy&cs=srgb&fm=jpg&ixid=MnwxOTcwMjR8MHwxfHNlYXJjaHwxfHxjYW5idXN8ZW58MHx8fHwxNjQ1NTI0MTY0&ixlib=rb-1.2.1&q=85
coverY: 0
---

# Controller Area Network

The **Controller Area Network** (also known as **** the **CAN Bus**, or just **CAN**), is the infrastructure used for internal networking in modern automobiles. It's controlled through a pretty low-level system of _controller_ **Nodes**, in a broadcast-style format.

There are filters built into the **receiver nodes**, but none at the transmitter level. Each **Node** (typically an "ECU" or "module") broadcasts **all of its data** onto the bus. As you can probably imagine, each node&#x20;

It is therefore the responsibility of the _listener nodes_ to filter through the noise, and determine what traffic is relevant to their individual needs/purposes.&#x20;

### About .dbc files

These nodes communicate with each other in a way that is, for the most part, unreadable and otherwise useless to humans in its raw form. Therefore, a semi-standardized format was developed by Vector GmbH to facilitate interpreting and translating the raw Signal values (from sensors and modules), into human-readable values and units (for gauges and data-loggers).

This is the `.dbc` format I'll be focusing on in this **Wiki** and its **** [**accompanying `canbus` repository**](https://github.com/nberlette/canbus)**.**

### How are they created?

Every auto manufacturer has their own proprietary "dictionary" which contains the mappings of their platform's specific adjustment factors/offsets, labels, and units, used to translate the raw sensor values into meaningful data points.

Sometimes these dictionaries (_"databases" or "documents"_) are leaked online, or sold by a disgruntled (former) employee. In most cases, however, enthusiasts such as myself spend countless hours - usually in their own vehicles - reverse-engineering translations into `.dbc` files.

{% hint style="warning" %}
**This is very much a work in progress.** Contributions are always welcome.
{% endhint %}

### Resources

* ****[**Boilerplate `.dbc` Template**](https://github.com/nberlette/canbus/wiki/Boilerplate-Template)****
* [**DBC Language Extension for Visual Studio Code**](https://marketplace.visualstudio.com/items?itemName=lharri73.dbc)****
* ****[**CANpy Original DBC Specification**](https://github.com/stefanhoelzl/CANpy/blob/master/docs/DBC\_Specification.md)****

### References

* [PiSnoop DBC Help](http://pisnoop.s3.amazonaws.com/snoop\_help\_dbc.htm)
* [CAN Format for VBOXII and PRO v4](http://www.racelogic.co.uk/\_downloads/vbox/Application\_Notes/CAN%20Format%20for%20VBOXII%20and%20PRO%20v4.pdf) (pdf)
* [CANtool Manual](http://www.ingenieurbuerobecker.de/downloads/CANtool\_Manual.pdf) (pdf)

***
