# DBC Specification

[DBC Specification](DBC_Specification.md) &gt; [Attributes: Definitions and Defaults](Attributes.md)

## Attributes: Definitions and Defaults

Attributes can be specified for Nodes (BU_), Messages (BO_), and Signals (SG_). The symbols can be pretty confusing, but most attributes have 3 key parts:

1. BA_DEF_: Attribute Definition. Specifies the type `(BU_|BO_|SG_)`, name, data type, and value configuration. [*]**required**
2. BA_DEF_DEF: Attribute Default Definition. Specifies the default value for the attribute if none is given. [*]**advised**
3. BA_: The Attribute. Specifies type, NodeName/CAN-ID/SignalName, and value(s). [*]**required**

### BA_DEF_: Attribute Definitions

`BA_DEF_ [BU_|BO_|SG_] "<AttributeName>" <DataType> [Config];`  

DataType | Description         | Config format
---------|---------------------|----------------
INT      | integer             | `<min> <max>`
FLOAT    | floating point      | `<min> <max>`
STRING   | string              |
ENUM     | enumeration         | `"<Value0>","<Value1>"...`

### BA_DEF_DEF_: Attribute Default Definition

`BA_DEF_DEF_ "<AttributeName>" ["]<DefaultValue>["];`

### BA_: Attributes

`BA_ "<AttributeName>" [BU_|BO_|SG_] [Node|CAN-ID] [SignalName] <AttributeValue>;`

------

## Message Attributes

------

## Signal Attributes

------

Assembled by [Nicholas Berlette](https://github.com/nberlette) &middot; [Acknowledgements](DBC_Specification.md#Acknowledgements) &middot; [License](LICENSE.md)
