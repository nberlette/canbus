# Boilerplate Template (`.dbc`)

**Freebie!** Here's a boilerplate specifically made to help speed up your .dbc creation workflows.

    VERSION "1.0.0"

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

    BS_:

    BU_: Vector__XXX

    BO_ 123 MessageName: 8 Vector__XXX
    SG_ Signal001 : 0|1@1+ (1,0) [0|1] "" Vector__XXX

    VAL_ 123 Signal001  0 "Disabled"  1 "Enabled" ;

    CM_ BO_  123  "Message Comment" ;
    CM_  SG_ 123  Signal001 "Signal Comment" ;

    CM_ "-------------------------------" ;
    CM_ "  ATTRIBUTE DEFINITIONS BELOW  " ;
    CM_ "-------------------------------" ;

    BA_DEF_  "ProtocolType" STRING ;
    BA_DEF_DEF_  "ProtocolType" "CAN";
    BA_ "ProtocolType" "CAN";

    BA_DEF_ BO_  "VFrameFormat" ENUM  "StandardCAN","ExtendedCAN","StandardCAN_FD","ExtendedCAN_FD","J1939PG" ;
    BA_DEF_DEF_  "VFrameFormat" "StandardCAN" ;
    BA_DEF_ BO_  "SystemMessageLongSymbol" STRING ;
    BA_DEF_DEF_  "SystemMessageLongSymbol" "";
    BA_DEF_ SG_  "SystemSignalLongSymbol" STRING ;
    BA_DEF_DEF_  "SystemSignalLongSymbol" "";

    BA_ "VFrameFormat" BO_ 123 0;