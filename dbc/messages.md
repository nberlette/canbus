# Messages

## Symbol

    BO_

Top-level block, no indentation and nothing immediately preceding on the line before it.

Children of messages (signals) must be indented by one space.

## Syntax

    BO_ <CAN-ID> <MessageName>: <Length> <Transmitter>

- `CAN-ID`: `decimal` (**not hex!**). Unique, no repeats.
- `Length`: in `bytes` (**not bits!**).

---

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
