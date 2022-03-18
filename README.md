---
description: Also known as the CAN Bus (often stylized CANBUS), or just CAN.
cover: >-
  https://images.unsplash.com/photo-1602845686963-0085ac4a8dcd?crop=entropy&cs=srgb&fm=jpg&ixid=MnwxOTcwMjR8MHwxfHNlYXJjaHwxfHxjYW5idXN8ZW58MHx8fHwxNjQ1NTI0MTY0&ixlib=rb-1.2.1&q=85
coverY: 0
---

# 🚘 Controller Area Network

The **Controller Area Network** (the **CAN Bus**, **CANBUS**, or just **CAN**) is an internationally standardized networking protocol, used by modules in modern automobiles as well as industrial vehicles (think tractors, forklifts, and so on).&#x20;

## Network Summary

It's controlled through a pretty low-level system of _controller_ **Nodes**, in a broadcast-style format.

Unlike other network protocols, with CAN, each **Transmitter Node** (think "**ECU**", "**module**") broadcasts **all of its data** onto the bus, and does not discriminate based on different Nodes listening to it. There are filters built into the **Receiver Nodes**, but none of them are at the transmitter level.&#x20;

It is therefore the responsibility of the ** **_**listener nodes**_** ** (or [**Receivers**](dbc/signals.md#breakdown-of-terms-and-types)) to filter through the noise, and determine what traffic is relevant to their individual needs and purposes.&#x20;

### Characteristics

If you have any experience with other network types, like TCP, this shotgun-style networking might seem like total madness to you.  It's casting a very wide "net", in a sense, but it has proven itself to be reliable in all the areas that matter:

* **very** simple to maintain and service over time
* proven track record of being rock-solid in terms of reliability
* resistant to electrical and magnetic signal interference

Since the primary automotive uses for CAN are monitoring sensitive sensor data, controlling life-saving and crash-safety equipment, and receiving/dispatching engine control signals (in a timely manner), there **is no room for error**.&#x20;

### Physical Structure

The wiring used is often a small gauge, twisted pair, arranged in bus form along a main channel. Each Node is connected to the main channel by a "stub", using the shortest amount of wire possible. The **twisted pair** design negates the need for shielding on the wires, and it resists most electrical interference it might encounter inside the automobile application.

The Nodes connect to and interface with the network via a small **transceiver chip**, usually something like a **TJA1042**, **TJA1050**, or **TJA1051**. These **transceivers** interact with a CAN controller, although sometimes they are built into the same unit together, and translate the messages and control the flow of data, as well as handle errors and "reboots".

## DBC Files

Nodes communicate with each other in a way that is, for the most part, unreadable and otherwise useless to humans in its raw form. Therefore, a semi-standardized format was developed by Vector GmbH to facilitate interpreting and translating the raw Signal values (from sensors and modules), into human-readable values and units (for gauges and data-loggers).

This is the `.dbc` format I'll be focusing on in this **Wiki** and its **** [**accompanying `canbus` repository**](https://github.com/nberlette/canbus)**.**

### How are they written?

Every auto manufacturer has their own proprietary "dictionary" which contains the mappings of their platform's specific adjustment factors/offsets, labels, and units, used to translate the raw sensor values into meaningful data points.

Sometimes these dictionaries (_"databases" or "documents"_) are leaked online, or sold by a disgruntled (former) employee. In most cases, however, enthusiasts such as myself spend countless hours - usually in their own vehicles - reverse-engineering translations into `.dbc` files.

{% hint style="warning" %}
**This is very much a work in progress.** Contributions are always welcome.
{% endhint %}

## DBC Specification

### [ **`VERSION`** ](broken-reference)

### [ **`NS_: NEW SYMBOLS`** ](dbc/new-symbols.md)

### [ **`BS_: BITSPEED`** ](dbc/new-symbols.md)

### [ **`BU_: BOARD UNITS`** ](dbc/board-units.md)

1. [Syntax](dbc/board-units.md#syntax)
2. [Examples](dbc/board-units.md#examples)

### [ **`BO_: MESSAGES`** ](dbc/messages.md)

1. [Syntax](dbc/messages.md#syntax)
2. [Attributes](dbc/messages.md#attributes)

### [ **`SG_: SIGNALS`** ](dbc/signals.md)

1. [Syntax](dbc/signals.md#syntax)
2. [Multiplexers](dbc/signals.md#multiplexers)
3. [Attributes](dbc/signals.md#attributes)

### [ **`BA_: ATTRIBUTES`** ](dbc/attributes.md)

1. [Syntax](dbc/attributes.md#syntax)
2. [Definitions](dbc/attributes.md#attribute-definitions-ba\_def\_)
3. [Defaults](dbc/attributes.md#attribute-defaults-ba\_def\_def\_)

### [ `CM_: COMMENTS` ](dbc/comments.md)

1. [Syntax (global)](dbc/comments.md#syntax-global)
2. [Syntax (scoped)](dbc/comments.md#syntax-scoped)
3. [Board Units](dbc/comments.md#board-unit)
4. [Messages](dbc/comments.md#message)
5. [Signals](dbc/comments.md#signal)

### [ **`VAL_: VALUES`** ](dbc/values.md)

1. [Syntax](dbc/values.md#syntax)
2. [Example](dbc/values.md#examples)
