---
description: List of New Symbol definitions to be expected in the document.
---

# 🌐 Network

## &#x20;**`VERSION`**&#x20;

```
VERSION "[major].[minor].[patch][-<pre>.<id>]"
```

This is quite often left blank, but it is **highly recommended** to follow **** [**semantic versioning**](https://semver.org)**,** or _**semver**_, to keep track of your changes and progression between versions and releases. In that same aspect, I recommend you always make use of a **version control system** like [**Git**](https://git-scm.org).

#### Examples

```
VERSION "2021.06.08"
VERSION "3.11.0"
VERSION "0.1.1-beta.1"
VERSION "1.0.0-rc.10"
```

## &#x20;**`NS_: NEW SYMBOLS`**&#x20;

Located at the very top of the document, just after [**`VERSION`**](new-symbols.md#version).

This doesn't change much between documents, so I tend to use the same block in all of mine. Some of the symbols listed, such as `CAT_` are now deprecated and will not be included or examined in this specification.

#### Example of a common New Symbols block:

```
NS_ :
  NS_DESC_
  BO_TX_BU_
  BA_DEF_DEF_
  BA_DEF_
  BA_
  CM_
  VAL_
  VAL_TABLE_
  SGTYPE_
  SGTYPE_VAL_
  SG_MUL_VAL_
  SIG_VALTYPE_
  SIGTYPE_VALTYPE_
  SIG_GROUP_
  CAT_DEF_
  CAT_
  FILTER
  EV_DATA_
  ENVVAR_DATA_
  SIG_TYPE_REF_
  BA_REL_
  BA_SGTYPE_
  BA_DEF_REL_
  BA_DEF_SGTYPE_
  BA_DEF_DEF_REL_
  BU_SG_REL_
  BU_EV_REL_
  BU_BO_REL_
```

## &#x20;**`BS_: BITSPEED`**&#x20;

### Syntax

```
BS_: <[:digit:] kbps>
```

{% hint style="info" %}
**`BS_: 100000`** ( or`1e3`)  indicates a network speed of **`100kb`** per second.
{% endhint %}

## [ **`BU_: NODES (BOARD UNITS)`** ](board-units.md)

## [ **`BO_: MESSAGES`** ](messages.md)

## [ **`SG_: SIGNALS`** ](signals.md)

## [ **`BA_: ATTRIBUTES`** ](attributes.md#syntax)

## [ `CM_: COMMENTS` ](comments.md#syntax-global)
