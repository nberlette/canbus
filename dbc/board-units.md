---
description: Also known as Board Units, ECUs, Transmitters/Receivers, Producers/Consumers.
---

# 🔉 Nodes (Board Units)

## Syntax

```
BU_: <Nodes>
```

**`Nodes`**: list of string literals (no quotes), separated by whitespace

Located at the top of the document's **Network area**, with [**Version**](version.md), [**New Symbols**](new-symbols.md), and **Bit Speed.**

{% hint style="success" %}
### **Pro Tip** <a href="#vector-xxx" id="vector-xxx"></a>

You might want to include **`Vector__XXX`** in the list, as a fallback **Receiver Node**.
{% endhint %}

### Symbol

```
BU_:
```

### Example

```
BU_: ABS DME DSC EKP KOMBI Vector__XXX
```
