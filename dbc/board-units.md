---
description: Also known as Board Units, ECUs, Transmitters/Receivers, Producers/Consumers.
---

# 🎛 Nodes

## Syntax

```
BU_: <Nodes>
```

**`Nodes`**: list of string literals (no quotes), separated by whitespace

Located at the top of the document's **Network area**, with [**Version**](new-symbols.md#version), [**New Symbols**](new-symbols.md#ns\_-new-symbols), and [**Bit Speed**](new-symbols.md#bs\_-bitspeed)**.**

{% hint style="success" %}
#### **Pro Tip:** <a href="#vector-xxx" id="vector-xxx"></a>

Consider adding **`Vector__XXX`** to your list as a fallback **Receiver Node**.
{% endhint %}

### Example

```
BU_: ABS DME DSC EKP KOMBI Vector__XXX
```
