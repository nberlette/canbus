# Attributes

## Symbol

    BA_:

_Typically_ located at the bottom of the document, after the messages and signals have been defined.

## Syntax

    BA_ "<AttributeName>" [BU_|BO_|SG_] [Node|CAN-ID] [Mnemonic] <Value>;

- `BA_`: The Attribute. Specifies type, NodeName/CAN-ID/SignalName, and value(s).
- `AttributeName` must have a corresponding definition to be considered valid (see below)

---

## Differentiate: `BA_`, `BA_DEF`, `BA_DEF_DEF`?

Attributes can be specified for [Nodes/Board Units](./Board-Units.md) (`BU_`), [Messages](./Messages.md) (`BO_`), and [Signals](./Signals.md) (`SG_`).

While the symbols are somewhat ambiguous, most attributes have 3 key parts.

---

### Attribute Definitions (`BA_DEF_`)

    BA_DEF_ [BU_|BO_|SG_] "<AttributeName>" <DataType> [Config];

- `BA_DEF_`: Attribute Definition. Specifies the type `(BU_|BO_|SG_)`, name, data type, and value configuration.

| DataType | Description    | Config format              |
| -------- | -------------- | -------------------------- |
| INT      | integer        | `<min> <max>`              |
| FLOAT    | floating point | `<min> <max>`              |
| STRING   | string         |
| ENUM     | enumeration    | `"<Value0>","<Value1>"...` |

### Attribute Defaults (`BA_DEF_DEF_`)

    BA_DEF_DEF_ "<AttributeName>" ["]<DefaultValue>["];

- `BA_DEF_DEF_`: Attribute Default Definition. Specifies the default value for the attribute if none is given.
