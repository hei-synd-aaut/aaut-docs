<h1 align="left">
  <br>
  <img src="./img/hei-en.png" alt="HEI-Vs Logo" width="350">
  <br>
  HEI-Vs Engineering School <h2>AAut Advanced Automation</h2>
  <br>
</h1>

[Cédric Lenoir](mailto:cedric.lenoir@hevs.ch)

# AAut Module 06 /  Some CtrlX Help

<p style="color:red; font-weight:bold;">For information only, futur use</p>

## Error Code, ``ENUM``

| Name                   | Initial | Comment                          |
|------------------------|---------|----------------------------------|
| NONE_ERROR             | 16#0    | No error code available          |
| INPUT_INVALID_ERROR    | 16#1    | Invalid input                    |
| COMMUNICATION_ERROR    | 16#2    | Error while communication        |
| RESOURCE_ERROR         | 16#3    | Resource error                   |
| ACCESS_ERROR           | 16#4    | Access error                     |
| STATE_MACHINE_ERROR    | 16#5    | Invalid state State - Machine    |
| INPUT_RANGE_ERROR      | 16#6    | Error because Input out of range |
| CALCULATION_ERROR      | 16#7    | Error while calculation          |
| DEVICE_ERROR           | 16#8    | Device Error occurred            |
| OTHER_ERROR            | 16#7FFE | Undefined Error                  |
| SYSTEM_ERROR           | 16#7FFF | System error occurred            |


### IEC 61131-3 Enum Definition

```iecst
TYPE ERROR_CODE :
(
    NONE_ERROR          := 16#0,
    INPUT_INVALID_ERROR := 16#1,
    COMMUNICATION_ERROR := 16#2,
    RESOURCE_ERROR      := 16#3,
    ACCESS_ERROR        := 16#4,
    STATE_MACHINE_ERROR := 16#5,
    INPUT_RANGE_ERROR   := 16#6,
    CALCULATION_ERROR   := 16#7,
    DEVICE_ERROR        := 16#8,
    OTHER_ERROR         := 16#7FFE,
    SYSTEM_ERROR        := 16#7FFF
) := NONE_ERROR;
END_TYPE
```

## TYPE ERROR_STRUCT ``STRUCT``

| Name                     | Type  | Comment                     |
|--------------------------|-------|-----------------------------|
| ERROR_TABLE              | Table | Additional diagnosis table  |
| Additional1              | DWORD | Additional diagnosis number1|
| Additional2              | DWORD | Additional diagnosis number2|

```iecst
TYPE ERROR_STRUCT :
STRUCT
	table		    : ERROR_TABLE;
	Additional1		: DWORD;
	Additional2		: DWORD;
END_STRUCT
END_TYPE
```

## ERROR_TABLE ``ENUM``

| Name          | Initial | Comment          |
|---------------|---------|------------------|
| NO_TABLE_USED | 16#0    | reserved         |
| CXA_TABLE     | 16#1    | ctrlX AUTOMATION |
| SERCOS_TABLE  | 16#10   | Sercos Error     |
| USER1_TABLE   | 16#1000 | free User Table  |
| USER2_TABLE   | 16#1001 | free User Table  |
| USER3_TABLE   | 16#1002 | free User Table  |
| USER4_TABLE   | 16#1003 | free User Table  |
| USER5_TABLE   | 16#1004 | free User Table  |
| USER6_TABLE   | 16#1005 | free User Table  |
| USER7_TABLE   | 16#1006 | free User Table  |
| USER8_TABLE   | 16#1007 | free User Table  |
| USER9_TABLE   | 16#1008 | free User Table  |
| USER10_TABLE  | 16#1009 | free User Table  |

### IEC 61131-3 Enum Definition

```iecst
TYPE ERROR_TABLE :
(
    NO_TABLE_USED := 16#0,
    CXA_TABLE     := 16#1,
    SERCOS_TABLE  := 16#10,
    USER1_TABLE   := 16#1000,
    USER2_TABLE   := 16#1001,
    USER3_TABLE   := 16#1002,
    USER4_TABLE   := 16#1003,
    USER5_TABLE   := 16#1004,
    USER6_TABLE   := 16#1005,
    USER7_TABLE   := 16#1006,
    USER8_TABLE   := 16#1007,
    USER9_TABLE   := 16#1008,
    USER10_TABLE  := 16#1009
) := NO_TABLE_USED;
END_TYPE
```