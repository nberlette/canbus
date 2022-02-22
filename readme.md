# Controller Area Network (CAN)

The Controller Area Network, also known as CAN or the CAN Bus, is the infrastructure used for internal networking in modern automobiles. It is controlled through a low level system of controller nodes, each of which broadcast **all of their data** onto the bus. It is therefore the responsibility of the *listener nodes* to filter through the noise, and determine what traffic is relevant to their individual needs/purposes.

These nodes communicate with each other in a way that is, for the most part, unreadable and otherwise useless to humans in its raw form. Therefore, a semi-standardized format was developed by Vector GmbH to facilitate interpreting and translating the raw Signal values (from sensors and modules), into human-readable values and units (for gauges and data-loggers).  

This is the `.dbc` format I'll be focusing on in this repository and its [accompanying Wiki](https://github.com/nberlette/canbus/wiki).

## How are `.dbc` files created?

Every auto manufacturer has their own proprietary "dictionary" which contains the mappings of their platform's specific adjustment factors/offsets, labels, and units, used to translate the raw sensor values into meaningful data points.  

Sometimes these dictionaries (or "databases", "documents") are leaked online, or sold by a disgruntled (former) employee. In most cases, however, enthusiasts such as myself spend countless hours, usually in their own cars, reverse-engineering translations to `.dbc` files.  

This is very much a work in progress. 

---

## [DBC Specification](./wiki)

1. **[`VERSION`](./wiki/Version)**
2. **[`NS_:` New Symbols](./wiki/New-Symbols)**
3. **[`BU_:` Board Units](./wiki/Board-Units)**
   - [Syntax](./wiki/Board-Units#syntax)
   - [Examples](./wiki/Board-Units#examples)
4. **[`BO_:` Messages](./wiki/Messages)**
   - [Syntax](./wiki/Messages#syntax)
   - [Attributes](./wiki/Messages#attributes)
   - [Examples](./wiki/Messages#examples)
5. **[`SG_:` Signals](./wiki/Signals)**
   - [Syntax](./wiki/Signals#syntax)
   - [Multiplexers](./wiki/Signals#multiplexers)
   - [Attributes](./wiki/Signals#attributes)
6. **[`BA_:` Attributes](./wiki/Attributes)**
   - [Syntax](./wiki/Attributes#syntax)
   - [Definitions](./wiki/Attributes#attribute-definitions-badef)
   - [Defaults](./wiki/Attributes#attribute-defaults-badefdef)
7. **[`CM_:` Comments](./wiki/Comments)**
   - [Syntax](./wiki/Comments#syntax-global)
   - [Syntax (scoped)](./wiki/Comments#syntax-scoped)
   - [Board Units](./wiki/Comments#board-unitboard-unitsmd)
   - [Messages](./wiki/Comments#messagemessagesmd)
   - [Signals](./wiki/Comments#signalsignalsmd)
8. **[`VAL_:` Values](./wiki/Values)**
   - [Syntax](./wiki/Values#syntax)
   - [Examples](./wiki/Values#examples)


---


## Downloadable .dbc files

| Vehicle | File Name | Version | Author |
| :-----: | :-------- | :------ | :----: |
| **BMW E90** | [`bmw-e90.dbc`](dbc/bmw-e90.dbc) ([raw](dbc/bmw-e90.dbc?raw=true)) | `2021.6.8` | [@nberlette](https://github.com/nberlette) |
| **BMW E39** | [`bmw-e39.dbc`](dbc/bmw-e39.dbc) ([raw](dbc/bmw-e39.dbc?raw=true)) | `2021.6.6` | translated from [`.kcd` by @kmalinich](https://github.com/kmalinich/node-bmw-interface/blob/master/can-definitions/bmw-e39.kcd) |
| **Mazda (2017)** | [`mazda_2017.dbc`][url-dbc-mazda-2017] | `--` | [@commaai/opendbc](https://github.com/commaai/opendbc) |
| **Lexus RX350** | [`lexus_rx350.dbc`][url-dbc-lexus-rx350] | `--` | [@commaai/opendbc](https://github.com/commaai/opendbc) |
| **Tesla Model 3** | [`tesla_model3.dbc`][url-dbc-tesla] | `2020.40.1` | [@johnmccalla](https://github.com/johnmccalla) and [@onyx-m2 project](https://github.com/onyx-m2) |
| **OBD2 (universal)** | [`obd2.dbc`](dbc/obd2.dbc) ([raw .dbc](dbc/obd2.dbc?raw=true)) | `0.0.1` | [csselectronics.com](https://csselectronics.com) |
| **J1939 (universal)** | [`j1939.dbc`](dbc/j1939.dbc) ([raw .dbc](dbc/j1939.dbc?raw=true)) | `7.6` | Unknown, from [haskell.org](https://haskell.org) |


---  

## Resources

- [Boilerplate `.dbc` Template](https://github.com/nberlette/canbus/wiki/Boilerplate-Template)
- [CANpy Original DBC Specification](https://github.com/stefanhoelzl/CANpy/blob/master/docs/DBC_Specification.md)
- [@commaai/opendbc project - open source DBC project](https://github.com/commaai/opendbc)
- [@kmalinich/node-bmw-ref - BMW KCAN / KBUS / IBUS reference](https://github.com/kmalinich/node-bmw-ref)
- [loopybunny.co.uk - BMW K-CAN documentation](https://www.loopybunny.co.uk/CarPC/k_can.html)
- [canmatrix - translate .dbc files to other filetypes](https://github.com/ebroecker/canmatrix)

---  

## References

- [PiSnoop DBC Help](http://pisnoop.s3.amazonaws.com/snoop_help_dbc.htm)
- [CAN Format for VBOXII and PRO v4](http://www.racelogic.co.uk/_downloads/vbox/Application_Notes/CAN%20Format%20for%20VBOXII%20and%20PRO%20v4.pdf) (pdf)
- [J1939 DBC from Haskell.org](https://hackage.haskell.org/package/ecu-0.0.8/src/src/j1939_utf8.dbc) (dbc)
- [CANtool Manual](http://www.ingenieurbuerobecker.de/downloads/CANtool_Manual.pdf) (pdf)


[url-wiki]: https://github.com/nberlette/canbus/wiki
[url-wiki-ns]: https://github.com/nberlette/canbus/wiki/New-Symbols
[url-wiki-bu]: https://github.com/nberlette/canbus/wiki/Board-Units
[url-wiki-bo]: https://github.com/nberlette/canbus/wiki/Messages
[url-wiki-sg]: https://github.com/nberlette/canbus/wiki/Signals
[url-wiki-ba]: https://github.com/nberlette/canbus/wiki/Attributes
[url-wiki-cm]: https://github.com/nberlette/canbus/wiki/Comments
[url-wiki-val]: https://github.com/nberlette/canbus/wiki/Values
[url-wiki-boilerplate]: https://github.com/nberlette/canbus/wiki/Boilerplate-Template
[url-license]: https://github.com/nberlette/canbus/blob/main/license.md
[url-maintainer]: https://github.com/nberlette
[url-markdown]: http://commonmark.org
[url-dbc-boilerplate]: https://github.com/nberlette/canbus/blob/main/dbc/boilerplate.dbc
[url-dbc-j1939]: https://github.com/nberlette/canbus/blob/main/dbc/j1939.dbc
[url-dbc-e90]: https://github.com/nberlette/canbus/blob/main/dbc/bmw-e90.dbc
[url-dbc-e39]: https://github.com/nberlette/canbus/blob/main/dbc/bmw-e39.dbc
[url-dbc-obd2]: https://github.com/nberlette/canbus/blob/main/dbc/obd2.dbc
[url-dbc-lexus-rx350]: https://github.com/commaai/opendbc/blob/master/lexus_rx_350_2016_pt_generated.dbc
[url-dbc-mazda-2017]: https://github.com/commaai/opendbc/blob/master/mazda_2017.dbc
[url-dbc-tesla]: https://github.com/onyx-m2/onyx-m2-dbc/blob/main/tesla_model3.dbc
[badge-license]: https://img.shields.io/badge/-MIT&nbsp;License-gray.svg
[badge-maintainer]: https://img.shields.io/badge/Maintained%20by-Nicholas%20Berlette-red.svg
[badge-markdown]: https://img.shields.io/badge/Made%20with-Markdown-1f425f.svg
[badge-dbc-j1939]: https://img.shields.io/badge/-J1939&nbsp;&#128668;-gray.svg
[badge-dbc-e90]: https://img.shields.io/badge/-BMW&nbsp;E90&nbsp;&#128663;-blue.svg
[badge-dbc-e39]: https://img.shields.io/badge/-BMW&nbsp;E39-8dddff.svg
[badge-dbc-boilerplate]: https://img.shields.io/badge/CAN%20Bus-Boilerplate.dbc-red.svg
