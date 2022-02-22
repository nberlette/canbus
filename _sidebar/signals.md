# Signals

## Syntax

```
SG_ <Mnemonic> : <Start>|<Length>@<BOM><Sign> (<factor>,<offset>) [<min>|<max>] "[unit]" [Receivers]
```

* `Mnemonic`: unique mnemonic name identifier for the Signal
* `Start`: Which bit (inclusive) does this signal begin at?
* `Length`: Total length of bits this signal encompasses
* `Sign`: + = unsigned; - = signed
* `BOM`: 1 = little-endian, Intel; 0 = big-endian, Motorola
* `factor`: decimal number multiplied with signal value (default `1`)
* `offset`: decimal number added to signal value (default `0`)
* `[<min>|<max>]`: relative to factor and offset. See below.
* `[unit]`: `string` representation of this value's units (e.g. `mph`)
* `[Receivers]`: space-separated [`BoardUnit` (`BU_`)](board-units.md) consumer list.

### Notes

* Must begin with a single whitespace indentation
* Immediately follows the Parent Message (`BO_`), or another signal (`SG_`).
  * No padding with blank lines between them

***

## Examples

### 8 bit (`0-255 decimal`)

```
 SG_ BattVoltage : 0|8@1+ (.1,0) [0|25.5] "volts" Vector__XXX
```

**`0.1`** `(factor) x`` `**`255`** `->` **`25.5`**

### 12-bit signal (`0-4095 decimal`)

```
 SG_ EngineRPM : 8|12@1+ (0.125,0) [0|512] "" Vector__XXX
```

**`0.125`** `(factor) x`` `**`4095`**`->`**`511.875 ~ 512`**

### 16-bit signal (`0-65535 decimal`)

```
 SG_ FuelLevel : 8|16@1+ (0.00625,0) [0|41] "liters" Vector__XXX
```

**`0.00625`** `(factor) x`` `**`65535`**`->`**`41 liters`**, or `16.5 gallons`

***

## Multiplexers

```
 SG_ <Mnemonic> [M|m<M-ID>] : <Start>|<Length>@<BOM><Sign> (<factor>,<offset>) [<min>|<max>] "[unit]" [Receivers]
```

* `M`: If M than this signals contains a multiplexer identifier.
* `M-ID`: Signal definition is only used if the value of the multiplexer signal equals to this value.

***

## Attributes

| Attribute Name         | Definition                                                                    | Default                                              |
| ---------------------- | ----------------------------------------------------------------------------- | ---------------------------------------------------- |
| SigType                | `BA_DEF_ SG_ "SigType" ENUM "Default","Range","RangeSigned","Control","DTC";` | `BA_DEF_DEF_ "SigType" "Default";`                   |
| SystemSignalLongSymbol | `BA_DEF_ SG_ "SystemSignalLongSymbol" STRING;`                                | `BA_DEF_DEF_ "SystemSignalLongSymbol" "";`           |
| GenSigSendType         | `BA_DEF_ SG_ "GenSigSendType" ENUM "none","Cyclic","OnWrite","OnChange";`     | `BA_DEF_DEF_ "GenSigSendType" "none";`               |
| GenSigILSupport        | `BA_DEF_ SG_ "GenSigILSupport" ENUM "Yes","No";`                              | `BA_DEF_DEF_ "GenSigILSupport" "Yes";`               |
| GenSigCycleTime        | `BA_DEF_ SG_ "GenSigCycleTime" INT <min=0> <max=10000> ;`                     | `BA_DEF_DEF_ "GenSigCycleTime" 0;`                   |
| GenSigDelayTime        | `BA_DEF_ SG_ "GenSigDelayTime" INT <min=0> <max=10000> ;`                     | `BA_DEF_DEF_ "GenSigDelayTime" 0;`                   |
| GenSigStartDelayTime   | `BA_DEF_ SG_ "GenSigStartDelayTime" INT <min=0> <max=10000> ;`                | `BA_DEF_DEF_ "GenSigStartDelayTime" 0;`              |
| GenSigStartValue       | `BA_DEF_ SG_ "GenSigStartValue" INT <min=0> <max>;`                           | `BA_DEF_DEF_ "GenSigStartValue" 0;`                  |
| GenSigEVName           | `BA_DEF_ SG_ "GenSigEVName" STRING;`                                          | `BA_DEF_DEF_ "GenSigEVName" "Env@<Node>_@<Signal>";` |
