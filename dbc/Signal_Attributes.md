# DBC Specification



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
