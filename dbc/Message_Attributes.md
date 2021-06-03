[DBC Specification](DBC_Specification.md) &gt; [Attributes: Definitions and Defaults](Attributes.md)

---

## Message Attributes

These are common Message Attributes, along with typical default values and examples of how to implement them.

### SystemMessageLongSymbol

```
BA_DEF_ BO_ "SystemMessageLongSymbol" STRING ;
```

### VFrameFormat

```
BA_DEF_ BO_  "VFrameFormat" ENUM  "StandardCAN","ExtendedCAN","StandardFD","ExtendedFD","J1939PG" ;
```

##### Default: `StandardCAN`

```
BA_DEF_DEF_ "VFrameFormat" "StandardCAN" ;
```

### GenMsgSendType

```
BA_DEF_ BO_  "GenMsgSendType" ENUM "cyclic","triggered","cyclicIfActive","none" ;
```

Supported types:

* cyclic  
* triggered  
* cyclicIfActive  
* cyclicAndTriggered  
* cyclicIfActiveAndTriggered  
* none  

##### Default: `none`

```
BA_DEF_DEF_ "GenMsgSendType" "none" ;
```

### GenMsgCycleTime

```
BA_DEF_ BO_  "GenMsgCycleTime" INT <mininum=0> <maximum=10000> ;
```

Message Cycle Time intervals defined in milliseconds.

##### Default: `0`

```
BA_DEF_DEF_  "GenMsgCycleTime" 0 ;
```  

### GenMsgStartDelayTime

```
BA_DEF_ BO_  "GenMsgStartDelayTime" INT <mininum=0> <maximum=10000> ;
```

Time (ms) from startup to delay before sending the first message frame.

##### Default: `0`

```
BA_DEF_DEF_  "GenMsgStartDelayTime" 0 ;
```  

### GenMsgDelayTime

```
BA_DEF_ BO_  "GenMsgDelayTime" INT <mininum=0> <maximum=10000> ;
```

##### Default: `0`

```
BA_DEF_DEF_  "GenMsgDelayTime" 0 ;
```
