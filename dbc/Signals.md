# DBC: Signals

[DBC Specification](./DBC_Specification.md) &gt; [Signals](./Signals.md)

--- 

## Syntax

```
 SG_ <name> : <Start>|<Length>@<ByteOrder><+|-> (<factor>,<offset>) [<min>|<max>] "[unit]" [Rx]
```

* min,max: proportional to `factor`, eg: a 16-bit max 65535 becomes 655.35 with .01 offset
* Length: in bits.  
* Signed: + = unsigned; - = signed  
* ByteOrder (endianness): 1 = little-endian, Intel; 0 = big-endian, Motorola 

### Multiplexed Signals

```
 SG_ <name> [M|m<M-ID>] : <Start>|<Length>@<ByteOrder><+|-> (<factor>,<offset>) [<min>|<max>] "[unit]" [Rx]
```

* M: If M than this signals contains a multiplexer identifier.  
* M-ID: Signal definition is only used if the value of the multiplexer signal equals to this value.  

## Examples

```
BO_ 760 EngineData: 8 TransmitterNode
 SG_ EngineCoolantTemp_C : 0|8@1+ (1,-48) [0|207] "degC" Vector__XXX
 SG_ EngineOilTemp_C : 8|8@1+ (1,-48) [0|207] "degC" Vector__XXX
```

#### Signal Values

```
VAL_ <CAN-ID> <SignalsName> <Name|Definition> ;

VAL_TABLE_ <Name> <Definition> ;
```

#### Value Table

List of `IntValue "StringValue"` pairs, separated by whitespaces

---

## Signal Attributes

Commonly used Signal Attributes, with default values and examples of how to implement them.

### SystemSignalLongSymbol

```
BA_DEF_ SG_ "SystemSignalLongSymbol" STRING ;
```

### SigType

```
BA_DEF_ SG_ "SigType" ENUM "Default","Range","RangeSigned","ASCII","Discrete","Control","DTC" ;
```

##### Default: `Default`

```
BA_DEF_DEF_ "SigType" "Default" ;
```

### GenSigSendType

```
BA_DEF_ SG_  "GenSigSendType" ENUM "none","Cyclic","OnWrite","OnChange","NoSigSendType" ;
```

##### Default: `none`

```
BA_DEF_DEF_ "GenSigSendType" "none" ;
```

### GenSigILSupport

```
BA_DEF_ SG_ "GenSigILSupport" ENUM "Yes","No" ;
```

##### Default: `Yes`

```
BA_DEF_DEF_  "GenSigILSupport"  "Yes" ;
```

### GenSigCycleTime

```
BA_DEF_ SG_ "GenSigCycleTime" INT <minimum=0> <maximum=0> ;
```

##### Default: `0`

```
BA_DEF_DEF_ "GenSigCycleTime" 0 ;
```

### GenSigDelayTime

```
BA_DEF_ SG_ "GenSigDelayTime" INT <minimum=0> <maximum=0> ;
```

##### Default: `0`

```
BA_DEF_DEF_ "GenSigDelayTime" 0 ;
```

### GenSigStartDelayTime

```
BA_DEF_ SG_ "GenSigStartDelayTime" INT <minimum=0> <maximum=0> ;
```

##### Default: `0`

```
BA_DEF_DEF_ "GenSigStartDelayTime" 0 ;
```

### GenSigStartValue

```
BA_DEF_ SG_  "GenSigStartValue" INT <mininum=0> <maximum=0> ;
```

Defines the value as long as no value is set/received for this signal.

##### Default: `0`

```
BA_DEF_DEF_  "GenSigStartValue" 0 ;
```

### GenSigEVName

```
BA_DEF_ SG_  "GenSigEVName" STRING ;
```

##### Default: `Env@<NodeName>_@<SigName>`

```
BA_DEF_DEF_  "GenSigEVName" "Env@<NodeName>_@<SigName>" ;
```
