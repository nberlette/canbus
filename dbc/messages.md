# 📨 Messages

## Syntax

```diff
BO_ <CAN-ID> <MessageName>: <Length> <Transmitter>
```

* [x] `CAN-ID` — `decimal` (not ** **_**hexa**_decimal). Must be **unique** to this message only.
* [x] `Length` — `bytes` , not **bits!**&#x20;
  1. &#x20;On `CAN 2.0` systems, value can be  `1-8`
  2. On `CAN FD` systems, value must be `1-64`

{% hint style="warning" %}
#### Important

* Top-level block. **No indentation**, nothing on the line immediately before it.
* **Children** of messages ([**signals**](signals.md)) **must be indented** by one space.
{% endhint %}

## Attributes

These are commonly used Message Attributes, which are widely accepted by industry software.

| Attribute Name          | Definition                                                                               | Default Value                               |
| ----------------------- | ---------------------------------------------------------------------------------------- | ------------------------------------------- |
| VFrameFormat            | `BA_DEF_ BO_ "VFrameFormat" ENUM "StandardCAN","ExtendedCAN","StandardFD","ExtendedFD";` | `BA_DEF_DEF_ "VFrameFormat" "StandardCAN";` |
| SystemMessageLongSymbol | `BA_DEF_ BO_ "SystemMessageLongSymbol" STRING;`                                          | `BA_DEF_DEF_ "SystemMessageLongSymbol";`    |
| GenMsgCycleTime         | `BA_DEF_ BO_ "GenMsgCycleTime" INT 0 10000;`                                             | `BA_DEF_DEF_ "GenMsgCycleTime" 0;`          |
| GenMsgStartDelayTime    | `BA_DEF_ BO_ "GenMsgStartDelayTime" INT <min=0> <max=10000>;`                            | `BA_DEF_DEF_ "GenMsgStartDelayTime" 0;`     |
| GenMsgDelayTime         | `BA_DEF_ BO_ "GenMsgDelayTime" INT <min=0> <max=10000>;`                                 | `BA_DEF_DEF_ "GenMsgDelayTime" 0;`          |
| GenMsgSendType          | `BA_DEF_ BO_ "GenMsgSendType" ENUM "cyclic","triggered","cyclicAndTriggered","none";`    | `BA_DEF_DEF_ "GenMsgSendType" "none";`      |
