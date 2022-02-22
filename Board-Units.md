# Board Units

Also known as Nodes, ECUs, Transmitters/Receivers, Producers/Consumers.

## Symbol

    BU_:

## Syntax

    BU_: <NodeNames>

- `<NodeNames>`: list of string literals (no quotes), separated by whitespace
- Usually a good idea to have `Vector__XXX` somewhere in the list, as a fallback Receiver Node.

## Examples

    BU_: ABS DME DSC EKP KOMBI Vector__XXX
