# Controller Area Network (CAN)

The Controller Area Network, also known as CAN or the CAN Bus, is the infrastructure used for internal networking in modern automobiles. It is controlled through a low level system of controller nodes, each of which broadcast **all of their data** onto the bus. It is therefore the responsibility of the *listener nodes* to filter through the noise, and determine what traffic is relevant to their individual needs/purposes.

These nodes communicate with each other in a way that is, for the most part, unreadable and otherwise useless to humans in its raw form. Therefore, a semi-standardized format was developed by Vector GmbH to facilitate interpreting and translating the raw Signal values (from sensors and modules), into human-readable values and units (for gauges and data-loggers).  

This is the `.dbc` format I'll be focusing on in this Wiki and its [accompanying `canbus` repository](https://github.com/nberlette/canbus).

## How are `.dbc` files created?

Every auto manufacturer has their own proprietary "dictionary" which contains the mappings of their platform's specific adjustment factors/offsets, labels, and units, used to translate the raw sensor values into meaningful data points.  

Sometimes these dictionaries (or "databases", "documents") are leaked online, or sold by a disgruntled (former) employee. In most cases, however, enthusiasts such as myself spend countless hours - usually in their own vehicles - reverse-engineering the translations into `.dbc` files.  

This is very much a work in progress.

---

## DBC Specification

1. **[`VERSION`](./Version)**
2. **[`NS_:` New Symbols](./New-Symbols)**
3. **[`BU_:` Board Units](./Board-Units)**
   - [Syntax](./Board-Units#syntax)
   - [Examples](./Board-Units#examples)
4. **[`BO_:` Messages](./Messages)**
   - [Syntax](./Messages#syntax)
   - [Attributes](./Messages#attributes)
   - [Examples](./Messages#examples)
5. **[`SG_:` Signals](./Signals)**
   - [Syntax](./Signals#syntax)
   - [Multiplexers](./Signals#multiplexers)
   - [Attributes](./Signals#attributes)
6. **[`BA_:` Attributes](./Attributes)**
   - [Syntax](./Attributes#syntax)
   - [Definitions](./Attributes#attribute-definitions-badef)
   - [Defaults](./Attributes#attribute-defaults-badefdef)
7. **[`CM_:` Comments](./Comments)**
   - [Syntax](./Comments#syntax-global)
   - [Syntax (scoped)](./Comments#syntax-scoped)
   - [Board Units](./Comments#board-unitboard-unitsmd)
   - [Messages](./Comments#messagemessagesmd)
   - [Signals](./Comments#signalsignalsmd)
8. **[`VAL_:` Values](./Values)**
   - [Syntax](./Values#syntax)
   - [Examples](./Values#examples)

---  

## Resources and References

- [Boilerplate `.dbc` Template](https://github.com/nberlette/canbus/wiki/Boilerplate-Template)
- [CANpy Original DBC Specification](https://github.com/stefanhoelzl/CANpy/blob/master/docs/DBC_Specification.md)
- [PiSnoop DBC Help](http://pisnoop.s3.amazonaws.com/snoop_help_dbc.htm)
- [CAN Format for VBOXII and PRO v4](http://www.racelogic.co.uk/_downloads/vbox/Application_Notes/CAN%20Format%20for%20VBOXII%20and%20PRO%20v4.pdf) (pdf)
- [J1939 DBC from Haskell.org](https://hackage.haskell.org/package/ecu-0.0.8/src/src/j1939_utf8.dbc) (dbc)
- [CANtool Manual](http://www.ingenieurbuerobecker.de/downloads/CANtool_Manual.pdf) (pdf)

---  

## License

[MIT](https://mit-license.org) © [Nicholas Berlette](https://github.com/nberlette) • [GitHub](https://github.com/nberlette/canbus)
