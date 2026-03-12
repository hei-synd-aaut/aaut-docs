```iecst
IF unitLoop < 1 THEN
   // Some init here
    ;
END_IF

PRG_MapBox();
PRG_DeviceManager();
PLC_PACK_ABox();

PRG_GetTime_CtrlX();
PRG_PackUpdate();
//
// My first Equipment Module here
//
emRobot(Status_StateCurrent := PackTag.Status.StateCurrent,
        Status_ModeCurrent := PackTag.Status.UnitModeCurrent);

emConveyor(Status_StateCurrent := PackTag.Status.StateCurrent,
          Status_ModeCurrent := PackTag.Status.UnitModeCurrent);
          
// AND of each Equipement Module propery SC          
PLC_PACK_ABox.whatSC := emRobot.SC   AND
                        emConveyor.SC;               
           
```