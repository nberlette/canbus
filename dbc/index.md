# DBC Specification

## Network

### Version

`VERSION "<Number>"`

### Bus Speed

```
BS_: [speed-kbit/s]
```

### Board Units

```
BU_: Node1 Node2 Node3 Node4
```

List of all Board Units (Nodes) in the Network. Also known as NetworkNodes, ECUs, Transmitters/Receivers, Producers/Consumers, SendingNodes/ReceivingNodes, etc.

### Comments

```
CM_ [BU_|BO_|SG_] [Node|CAN-ID] [SignalName] "<Comments>";

CM_  "<Comments>" ;

CM_ BU_  <NodeId> "<Comments>" ;

CM_ BO_  <CAN-ID> "<Comment>" ;

CM_ SG_  <CAN-ID> <SignalName> "<Comment>" ;
```


## More Information

### Format Specification

```markdown
<...> Required field
<A|B> A or B required
[...] Optional field
[A|B] A or B optional
```

### Document Scope

This document doesn't claim to specifiy the complete [Vector DBC standard](http://vector.com/vi_candb_en.html)  

### Sources and Acknowledgements

* [CANpy Original DBC Specification](https://github.com/stefanhoelzl/CANpy/blob/master/docs/DBC_Specification.md)
* [PiSnoop DBC Help](http://pisnoop.s3.amazonaws.com/snoop_help_dbc.htm)
* [CAN Format for VBOXII and PRO v4](http://www.racelogic.co.uk/_downloads/vbox/Application_Notes/CAN%20Format%20for%20VBOXII%20and%20PRO%20v4.pdf) (pdf)
* [J1939 DBC from Haskell.org](https://hackage.haskell.org/package/ecu-0.0.8/src/src/j1939_utf8.dbc) (dbc)
* [CANtool Manual](http://www.ingenieurbuerobecker.de/downloads/CANtool_Manual.pdf) (pdf)
