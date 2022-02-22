# Table of Contents

1. [`VERSION`](./Version)
2. [`NS_:` New Symbols](./New-Symbols)
3. [`BU_:` Board Units](./Board-Units)
   - [Syntax](./Board-Units#syntax)
   - [Examples](./Board-Units#examples)
4. [`BO_:` Messages](./Messages)
   - [Syntax](./Messages#syntax)
   - [Attributes](./Messages#attributes)
   - [Examples](./Messages#examples)
5. [`SG_:` Signals](./Signals)
   - [Syntax](./Signals#syntax)
   - [Multiplexers](./Signals#multiplexers)
   - [Attributes](./Signals#attributes)
6. [`BA_:` Attributes](./Attributes)
   - [Syntax](./Attributes#syntax)
   - [Definitions](./Attributes#attribute-definitions-badef)
   - [Defaults](./Attributes#attribute-defaults-badefdef)
7. [`CM_:` Comments](./Comments)
   - [Syntax](./Comments#syntax-global)
   - [Syntax (scoped)](./Comments#syntax-scoped)
   - [Board Units](./Comments#board-unitboard-unitsmd)
   - [Messages](./Comments#messagemessagesmd)
   - [Signals](./Comments#signalsignalsmd)
8. [`VAL_:` Values](./Values)
   - [Syntax](./Values#syntax)
   - [Examples](./Values#examples)

---

<div align=center>

[![MIT License][badge-license]][url-wiki-license] [![DBC Boilerplate Template][badge-dbc-boilerplate]][url-wiki-boilerplate] [![badge-dbc-e90]][url-dbc-e90] [![badge-dbc-e39]][url-dbc-e39]

</div>

[badge-dbc-boilerplate]: https://img.shields.io/badge/-Boilerplate.dbc-red.svg?style=for-the-badge
[badge-dbc-j1939]: https://img.shields.io/badge/-J1939-gray.svg
[badge-dbc-e90]: https://img.shields.io/badge/-E90.dbc-345.svg?style=for-the-badge&logo=bmw
[badge-dbc-e39]: https://img.shields.io/badge/-E39.dbc-456.svg?style=for-the-badge&logo=bmw
[badge-license]: https://img.shields.io/badge/-MIT-blue.svg?style=for-the-badge
[url-wiki-boilerplate]: https://github.com/nberlette/canbus/wiki/Boilerplate-Template
[url-wiki]: https://github.com/nberlette/canbus/wiki
[url-wiki-version]: https://github.com/nberlette/canbus/wiki/Version
[url-wiki-ns]: https://github.com/nberlette/canbus/wiki/New-Symbols
[url-wiki-bu]: https://github.com/nberlette/canbus/wiki/Board-Units
[url-wiki-bo]: https://github.com/nberlette/canbus/wiki/Messages
[url-wiki-sg]: https://github.com/nberlette/canbus/wiki/Signals
[url-wiki-mul]: https://github.com/nberlette/canbus/wiki/Multiplexers
[url-wiki-ba]: https://github.com/nberlette/canbus/wiki/Attributes
[url-wiki-cm]: https://github.com/nberlette/canbus/wiki/Comments
[url-wiki-val]: https://github.com/nberlette/canbus/wiki/Values
[url-wiki-ack]: https://github.com/nberlette/canbus/wiki/Acknowledgements
[url-wiki-license]: https://github.com/nberlette/canbus/raw/main/license.md
[url-dbc-e90]: https://github.com/nberlette/canbus/raw/main/dbc/bmw-e90.dbc
[url-dbc-e39]: https://github.com/nberlette/canbus/raw/main/dbc/bmw-e39.dbc
[url-dbc-j1939]: https://github.com/nberlette/canbus/raw/main/dbc/j1939.dbc
[url-dbc-obd2]: https://github.com/nberlette/canbus/raw/main/dbc/obd2.dbc
[url-dbc-boilerplate]: https://github.com/nberlette/canbus/raw/main/dbc/boilerplate.dbc
