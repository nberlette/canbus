---
description: >-
  This is our in-depth, color-coded breakdown of the Signals syntax in CAN Bus
  Networks.
---

# 📶 Signals

## Syntax

&#x20;**`SG_`**<mark style="color:green;">**`Name`**</mark>**`:`**<mark style="color:red;">**`Start`**</mark>**`|`**<mark style="color:blue;">**`Size`**</mark>**`@`**<mark style="color:purple;">**`Order`**</mark><mark style="color:orange;">**`+-`**</mark>**`(`**<mark style="color:red;background-color:blue;">**`Slope`**</mark>`,`<mark style="color:green;background-color:blue;">**`Offset`**</mark>**`) [`**<mark style="color:red;background-color:yellow;">**`Min`**</mark>**`|`**<mark style="color:green;background-color:yellow;">**`Max`**</mark>**`]`**<mark style="color:green;">`"Unit"`</mark><mark style="color:yellow;">**`RxN`**</mark>

#### &#x20;Breakdown of Terms & Types

* <mark style="color:green;">**Name**</mark>   **`string`**   ·  _**unique**_ _mnemonic_ name for identifying the signal
* <mark style="color:red;">**Start**</mark>     **`number`**  ·  the bit number (_inclusive_) this signal begins at
* <mark style="color:blue;">**Size**</mark>   **`number`**  ·  total length of bits this signal occupies
* <mark style="color:purple;">**Order**</mark>    **`1`**`or`**`0`**  ·  <mark style="color:purple;">**`1`**</mark>` ``(little-endian/Intel)` or <mark style="color:purple;">**`0`**</mark>` ``(big-endian/Motorola)`
* <mark style="color:orange;">**Sign**</mark>    **   `+`**`or`**`–`**  ·  <mark style="color:orange;">**`+`**</mark>` ``(unsigned)` or <mark style="color:orange;">**`–`**</mark>`(signed)`&#x20;
* &#x20; <mark style="color:red;background-color:purple;">**Slope**</mark>    __  **`decimal`** _·  **multiplied**_  by **original** signal value  `default`<mark style="color:red;">**`1`**</mark>&#x20;
* &#x20;<mark style="color:green;background-color:purple;">**Offset**</mark> <mark style="color:green;background-color:purple;"></mark><mark style="color:green;background-color:purple;"></mark>  **`decimal`** ·  _**added**_  to the **original** signal value   `default`<mark style="color:green;">**`0`**</mark>&#x20;
* &#x20;  <mark style="color:red;background-color:yellow;">**Min.**</mark>**     ** **`decimal`** ·  _**minimum**_  return value, **relative** to  <mark style="color:red;">**`slope`**</mark> and <mark style="color:green;">**`offset`**</mark>
* &#x20;  <mark style="color:green;background-color:yellow;">**Max.**</mark>**   **  **`decimal`** ·  _**maximum**_ return value, **relative** to  <mark style="color:red;">**`slope`**</mark> and <mark style="color:green;">**`offset`**</mark>
* <mark style="color:green;">**Unit**</mark>        **`string`**  ·  _**optional**_  units for the return value (e.g. **`mph`**)
* <mark style="color:yellow;">**RxN**</mark>        **`string`**  ·  space-separated list of <mark style="color:yellow;">**`Receiving Nodes`**</mark> ([`BoardUnit, BU_`](board-units.md))

#### Example

&#x20;**`SG_`` `**<mark style="color:green;">**`Sig1`**</mark>**` ``:`` `**<mark style="color:red;">**`0`**</mark>**`|`**<mark style="color:blue;">**`1`**</mark>**`@`**<mark style="color:purple;">**`0`**</mark><mark style="color:orange;">**`+`**</mark>**`(`**<mark style="color:red;background-color:purple;">**`1`**</mark>**`,`**<mark style="color:green;background-color:purple;">**`0`**</mark>**`) [`**<mark style="color:red;background-color:yellow;">**`0`**</mark>**`|`**<mark style="background-color:yellow;"><mark style="color:green;background-color:yellow;">**`1`**<mark style="color:green;background-color:yellow;"></mark>**`]`` `**<mark style="color:green;">**`""`**</mark>**` `**<mark style="color:yellow;">**`Vector_XXX`**</mark>&#x20;

#### Raw:

&#x20;**`SG_ Sig1 : 0|1@0+ (1,0) [0|1] "" Vector_XXX`**&#x20;

### Important

{% hint style="warning" %}
Signals are **all** required **** to meet **strict syntax** standards, including:

* **Must begin** with a **single** whitespace indentation before **`SG_`**
* **Immediately** follows a Message Block (**`BO_`**) or another Signal (**`SG_`**).
* **No padding** with blank lines or whitespace between&#x20;
{% endhint %}



### Real Examples

#### 8 bit (`0-255 decimal`)

```
 SG_ BattVoltage : 0|8@1+ (.1,0) [0|25.5] "volts" Vector__XXX
```

**`0.1`** `(factor) x`` `**`255`** `->` **`25.5`**

#### 12-bit signal (`0-4095 decimal`)

```
 SG_ EngineRPM : 8|12@1+ (0.125,0) [0|512] "" Vector__XXX
```

**`0.125`** `(factor) x`` `**`4095`**`->`**`511.875 ~ 512`**

#### 16-bit signal (`0-65535 decimal`)

```
 SG_ FuelLevel : 8|16@1+ (0.00625,0) [0|41] "liters" Vector__XXX
```

**`0.00625`** `(factor) x`` `**`65535`**`->`**`41 liters`**, or `16.5 gallons`

***

## Multiplexers

If you've gotten this far, you've likely already heard of Multiplexers and Multiplexed Signals.&#x20;

If not - great! Prepare to pull your hair out either way. If it makes you feel any better, explaining them is just as hard as understanding them... so I should be bald here pretty soon.

### What are they?



### Multiplexer Syntax

```
 SG_ <Name> [M|m<M-ID>] : <Start>|<Size>@<Order><Sign> (<slope>,<offset>) [<min>|<max>] "[unit]" [Receivers]
```

* **`M`**: indicates this signal is a multiplex controller
* **`m<ID>`**`:` this definition is only used if the value of the multiplexer signal equals to this value.

***

## Attributes

| Attribute Name         | Definition                                                                    | Default                                              |
| ---------------------- | ----------------------------------------------------------------------------- | ---------------------------------------------------- |
| SigType                | `BA_DEF_ SG_ "SigType" ENUM "Default","Range","RangeSigned","Control","DTC";` | `BA_DEF_DEF_ "SigType" "Default";`                   |
| SystemSignalLongSymbol | `BA_DEF_ SG_ "SystemSignalLongSymbol" STRING;`                                | `BA_DEF_DEF_ "SystemSignalLongSymbol" "";`           |
| GenSigSendType         | `BA_DEF_ SG_ "GenSigSendType" ENUM "none","Cyclic","OnWrite","OnChange";`     | `BA_DEF_DEF_ "GenSigSendType" "none";`               |
| GenSigILSupport        | `BA_DEF_ SG_ "GenSigILSupport" ENUM "Yes","No";`                              | `BA_DEF_DEF_ "GenSigILSupport" "Yes";`               |
| GenSigCycleTime        | `BA_DEF_ SG_ "GenSigCycleTime" INT <min=0> <max=10000> ;`                     | `BA_DEF_DEF_ "GenSigCycleTime" 0;`                   |
| GenSigDelayTime        | `BA_DEF_ SG_ "GenSigDelayTime" INT <min=0> <max=10000> ;`                     | `BA_DEF_DEF_ "GenSigDelayTime" 0;`                   |
| GenSigStartDelayTime   | `BA_DEF_ SG_ "GenSigStartDelayTime" INT <min=0> <max=10000> ;`                | `BA_DEF_DEF_ "GenSigStartDelayTime" 0;`              |
| GenSigStartValue       | `BA_DEF_ SG_ "GenSigStartValue" INT <min=0> <max>;`                           | `BA_DEF_DEF_ "GenSigStartValue" 0;`                  |
| GenSigEVName           | `BA_DEF_ SG_ "GenSigEVName" STRING;`                                          | `BA_DEF_DEF_ "GenSigEVName" "Env@<Node>_@<Signal>";` |
