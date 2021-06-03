# DBC: Messages

[DBC Spec](./DBC_Specification.md) &gt; [Messages](./Messages.md)

## Syntax

```
BO_ <CAN-ID> <MessageName>: <MessageLength> <SendingNode>
```

* [CAN-ID]: Always in decimal form, not hex. Must be unique to this message - no repeats allowed in the document.
* [MessageName]: Recommended to use CamelCase. Up to 32 characters long. Must begin with a letter, not a number.
* [MessageLength]: DLC must be between 0-8 bytes for CAN 2.0B, or 0-64 bytes for CAN FD.
* [SendingNode]: Board Unit/Node/ECU that produces this message. Must be in the `BU_` list at beginning of the file.

---

## Message Attributes

The following are some common Message Attributes, along with typical default values and examples of how to implement them. These are widely adopted and understood by a large portion of the interpreters available for DBC files.

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

---

