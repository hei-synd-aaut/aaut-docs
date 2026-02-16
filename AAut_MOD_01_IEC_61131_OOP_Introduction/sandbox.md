
```iecst
METHOD Method1 : BOOL
VAR_INPUT
    nIn1  : INT;
    bIn2  : BOOL;
END_VAR
VAR_OUTPUT
    fOut1 : REAL;
    sOut2 : STRING;
END_VAR
// <method implementation code>
PROGRAM MAIN
VAR
    fbSample      : FB_Sample;
    bReturnValue  : BOOL;
    nLocalInput1  : INT;
    bLocalInput2  : BOOL;
    fLocalOutput1 : REAL;
    sLocalOutput2 : STRING;
END_VAR

bReturnValue := fbSample.Method1(nIn1  := nLocalInput1,
                                 bIn2  := bLocalInput2,
                                 fOut1 => fLocalOutput1,
                                 sOut2 => sLocalOutput2);
```

```mermaid
    classDiagram
        class FB_Sample {
            BOOL Method1(INT nIn1, BOOL bIn2) : (REAL fOut1, STRING sOut2)
        }

    class MAIN {
        FB_Sample fbSample
        BOOL bReturnValue
        INT nLocalInput1
        BOOL bLocalInput2
        REAL fLocalOutput1
        STRING sLocalOutput2
    }

    MAIN --> FB_Sample : uses
```