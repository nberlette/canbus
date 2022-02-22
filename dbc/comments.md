# Comments

```
CM_ [BU_|BO_|SG_] [Node|CAN-ID] [SignalName] "<Comments>";
```

## Syntax (global)

```
CM_  "<Comments>" ;
```

## Syntax (scoped)

Comments have the ability to be scoped globally (default; meaning it applies to the file as a whole), or directed at one particular section of the file.

### [Board Unit](board-units.md)

```
CM_ BU_  <NodeId> "<Comments>" ;
```

### [Message](messages.md)

```
CM_ BO_  <CAN-ID> "<Comments>" ;
```

### [Signal](signals.md)

```
CM_ SG_  <CAN-ID> <SignalName> "<Comments>" ;
```
