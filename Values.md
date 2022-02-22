# Values

Equates to a rudamentary Key-Value (`KV`) map for Signal data. Allows DBC interpreters to output human-readable strings from raw Signal input values.

## Symbol

    VAL_

Usually positioned at the bottom of the document, adjacent to **[Attributes](./Attributes.md)**.

---

## Syntax

    VAL_ <ID> <SignalName>  Key_1 "Val_1" ... Key_N "Val_N";

- `<ID>`: CAN-ID (`decimal`)
- `SignalName`: Mnemonic (**[see signals](./Signals.md)**)
- `Key_N`: Raw signal data (`integer`)
- `Val_N`: Text descriptor (`string`)

> **Note**: multiple pairs of values are permitted. Minimum of 1 pair required.

---

## Examples

### `GearSelector` (`enum`)

    VAL_ 123 GearSelector  0 "P" 1 "R" 2 "N" 3 "D";

> - `0` `->` **`P`** (**park**)
> - `1` `->` **`R`** (**reverse**)
> - `2` `->` **`N`** (**neutral**)
> - `3` `->` **`D`** (**drive**)

### `HandbrakeStatus` (`boolean`)

    VAL_ 456 HandbrakeStatus  0 "Disengaged" 1 "Engaged";

> - `0` = **`Disengaged`**
> - `1` = **`Engaged`**

### `HeadlightStatus` (`boolean`)

    VAL_ 789 HeadlightStatus  0 "Off" 1 "On" ;

> - `0` = **`"Off"`**
> - `1` = **`"On"`**
