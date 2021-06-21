<a href="https://github.com/nberlette/canbus/wiki" title="Check out the Wiki!"><img src="https://github.com/nberlette/canbus/blob/master/banner.png?raw=true" alt="Controller Area Network (CAN): reference and resources" style="max-width: 600px; margin: 30px auto;"/></a>

# [DBC Specification: Table of Contents][url-wiki]

### [NS_: New Symbols][url-wiki-ns]
### [BU_: Board Units][url-wiki-bu]
### [BO_: Messages][url-wiki-bo]
### [SG_: Signals][url-wiki-sg]
### [MUL_: Multiplexers][url-wiki-mul]
### [BA_: Attributes][url-wiki-ba]
### [CM_: Comments][url-wiki-cm]
### [VAL_: Values][url-wiki-val]
---


## `.dbc downloadable files`

[![J1939 DBC][badge-dbc-j1939]][url-dbc-j1939] [![BMW-E90.dbc][badge-dbc-e90]][url-dbc-e90] [![BMW-E39.dbc][badge-dbc-e39]][url-dbc-e39]

Vehicle | File Name | Version | Author
--------|-----------|---------|--------
**Boilerplate Template** | [![DBC Boilerplate Template][badge-dbc-boilerplate]][url-dbc-boilerplate]| `1.0.0` | [@nberlette](https://github.com/nberlette)
**BMW E90** | [`bmw-e90.dbc`][url-dbc-e90] ([raw](dbc/bmw-e90.dbc?raw=true)) | `2021.6.8` | [@nberlette](https://github.com/nberlette)
**BMW E39** | [`bmw-e39.dbc`][url-dbc-e39] ([raw](dbc/bmw-e39.dbc?raw=true)) | `2021.6.6` | [.kcd by @kmalinich](https://github.com/kmalinich/node-bmw-interface/blob/master/can-definitions/bmw-e39.kcd), translated by @nberlette
**Mazda (2017)** | [`mazda_2017.dbc`][url-dbc-mazda-2017] | `--` | [@commaai/opendbc](https://github.com/commaai/opendbc)
**Lexus RX350** | [`lexus_rx350.dbc`][url-dbc-lexus-rx350] | `--` | [@commaai/opendbc](https://github.com/commaai/opendbc)
**Tesla Model 3** | [`tesla_model3.dbc`][url-dbc-tesla] | `2020.40.1` | [@johnmccalla](https://github.com/johnmccalla), part of [@onyx-m2 project](https://github.com/onyx-m2)
**OBD2 (universal)** | [`obd2.dbc`][url-dbc-obd2] ([raw](dbc/obd2.dbc?raw=true)) | `0.0.1` | [csselectronics.com](https://csselectronics.com)
**J1939 (universal)** | [`j1939.dbc`][url-dbc-j1939] ([raw](dbc/j1939.dbc?raw=true)) | `7.6` | Unknown, from [haskell.org](https://haskell.org)

## Other Resources

* [@commaai/opendbc project - open source DBC project](https://github.com/commaai/opendbc)
* [@kmalinich/node-bmw-ref - BMW KCAN / KBUS / IBUS reference](https://github.com/kmalinich/node-bmw-ref)
* [loopybunny.co.uk - BMW K-CAN documentation](https://www.loopybunny.co.uk/CarPC/k_can.html)
* [canmatrix - translate .dbc files to other filetypes](https://github.com/ebroecker/canmatrix)

- - - 

[![Acknowledgements][badge-ack]][url-ack] [![MIT License][badge-license]][url-license] [![made-with-Markdown][badge-markdown]][url-markdown] [![Maintained by nberlette][badge-maintainer]][url-maintainer]

<!-- 

  references 

-->

<!-- badges -->
[badge-ack]: https://img.shields.io/badge/-Acknowledgements-gray.svg
[badge-license]: https://img.shields.io/badge/-MIT&nbsp;License-gray.svg
[badge-maintainer]: https://img.shields.io/badge/Maintained%20by-Nicholas%20Berlette-red.svg
[badge-markdown]: https://img.shields.io/badge/Made%20with-Markdown-1f425f.svg
[badge-dbc-j1939]: https://img.shields.io/badge/-J1939&nbsp;&#128668;-gray.svg
[badge-dbc-e90]: https://img.shields.io/badge/-BMW&nbsp;E90&nbsp;&#128663;-blue.svg
[badge-dbc-e39]: https://img.shields.io/badge/-BMW&nbsp;E39-8dddff.svg
[badge-dbc-boilerplate]: https://img.shields.io/badge/Universal-Boilerplate.dbc-red.svg

<!-- repo/wiki info urls -->
[url-ack]: https://github.com/nberlette/canbus/wiki/Acknowledgements
[url-license]: https://github.com/nberlette/canbus/blob/master/LICENSE
[url-maintainer]: https://github.com/nberlette/
[url-markdown]: http://commonmark.org

<!-- dbc file urls -->
[url-dbc-boilerplate]: https://github.com/nberlette/canbus/blob/master/dbc/boilerplate.dbc
[url-dbc-j1939]: https://github.com/nberlette/canbus/blob/master/dbc/j1939.dbc
[url-dbc-e90]: https://github.com/nberlette/canbus/blob/master/dbc/bmw-e90.dbc
[url-dbc-e39]: https://github.com/nberlette/canbus/blob/master/dbc/bmw-e39.dbc
[url-dbc-obd2]: https://github.com/nberlette/canbus/blob/master/dbc/obd2.dbc
[url-dbc-lexus-rx350]: https://github.com/commaai/opendbc/blob/master/lexus_rx_350_2016_pt_generated.dbc
[url-dbc-mazda-2017]: https://github.com/commaai/opendbc/blob/master/mazda_2017.dbc
[url-dbc-tesla]: https://github.com/onyx-m2/onyx-m2-dbc/blob/main/tesla_model3.dbc

<!-- wiki table of contents urls (dbc spec) -->
[url-wiki-boilerplate]: https://github.com/nberlette/canbus/wiki/Boilerplate-Template
[url-wiki]: https://github.com/nberlette/canbus/wiki
[url-wiki-ns]: https://github.com/nberlette/canbus/wiki/New-Symbols
[url-wiki-bu]: https://github.com/nberlette/canbus/wiki/Board-Units
[url-wiki-bo]: https://github.com/nberlette/canbus/wiki/Messages
[url-wiki-sg]: https://github.com/nberlette/canbus/wiki/Signals
[url-wiki-mul]: https://github.com/nberlette/canbus/wiki/Multiplexers
[url-wiki-ba]: https://github.com/nberlette/canbus/wiki/Attributes
[url-wiki-cm]: https://github.com/nberlette/canbus/wiki/Comments
[url-wiki-val]: https://github.com/nberlette/canbus/wiki/Values

