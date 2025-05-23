# PowMr 10.2kW Inverter confirmed registers map

### Read registers
- 4501 : Output Source Priority *(Returns index with offset. I'd prefer to use register 4537)* `settings`
    * `0` Mode 0 `measurement`
    * `1` Mode 1 `measurement`
    * `2` Standby Mode (Charging Battery) `measurement`
    * `3` Battery Mode `measurement`
    * `4` Line Mode (Bypass) `measurement`
    * `11` Standby Mode, Charging `measurement`
- 4502 : Grid Voltage `measurement`
- 4503 : Grid Frequency `measurement`
- 4504 : PV1 Voltage `measurement`
- 4505 : PV1 Power `measurement`
- 4506 : Battery Voltage `measurement`
- 4507 : Battery SoC `measurement`
- 4508 : Battery Charge Current `measurement`
- 4509 : Battery Discharge Current `measurement`
- 4510 : Load Voltage `measurement`
- 4511 : Load Frequency `measurement`
- 4512 : Load Apparent Power `measurement`
- 4513 : Load Active Power `measurement`
- 4514 : Load Percent `measurement`
- 4515 : Load Percent `measurement`
- 4516 : Load Percent 2 `measurement`
- 4517 : Dual-channel Load CutOff Voltage `measurement`
- 4518 : Main CPU Version `settings`
- 4519 : Battery Equalization `settings`
- 4520 : battery_configuration `settings`
- 4521 : Nominal Load Power VA (Device Maximal Power)
- 4522 : Nominal Load Power (Device Maximal Power)
- 4523 : Nominal Grid Voltage (Target Voltage)
- 4524 : Nominal Grid Current `measurement`
- 4525 : Nominal Battery Voltage `measurement`
- 4526 : Nominal Load Voltage `measurement`
- 4527 : Nominal Load Frequency`measurement`
- 4528 : Nominal Load Current `measurement`
- 4529 : Inverter Faults `measurement`
- 4530 : Error Code
    * `0x0000` No warning or error `measurement`
    * `0x0020` PV energy is low `measurement`
- 4531 : Reserved value 5535 `unclear significance`
- 4532 : Reserved value 5535 `unclear significance`
- 4533 : Reserved value 5535 `unclear significance`
- 4534 : Reserved value 55 `unclear significance`
- 4535 : Settings flags `binary_flags`
    * `0x0001` Record Fault Code `settings`
    * `0x0002` Battery Equalization `settings`
    * `0x0004` Equalization Activated Immediately `settings`
    * `0x0008` `unclear significance`
    * `0x0010` `unclear significance`
    * `0x0020` `unclear significance`
    * `0x0040` `unclear significance`
    * `0x0080` `unclear significance`
    * `0x0100` Alarm `settings`
    * `0x0200` `unclear significance`
    * `0x0400` Backlight `settings`
    * `0x0800` Restart On Overload `settings`
    * `0x1000` Restart On Overheat `settings`
    * `0x2000` Beep On Primary Source Fail `settings`
    * `0x4000` Return To Default Screen `settings`
    * `0x8000` Overload Bypass `settings`
- 4536 : Charger Source Priority `settings`
- 4537 : Output Source Priority `settings`
- 4538 : AC Input Voltage Range `settings`
- 4539 : stable value 2
- 4540 : Target Output Frequency `settings`
    * `0x0000` 50 Hz `settings`
    * `0x0001` 60 Hz `settings`
- 4541 : Max Total Charging Current `settings`
- 4542 : Target Output Voltage `settings`
- 4543 : Max Utility Charging Current `settings`
- 4544 : Back To Utility Source Voltage `settings`
- 4545 : Back To Battery Source Voltage `settings`
- 4546 : Bulk Charging Voltage `settings`
- 4547 : Floating Charging Voltage `settings`
- 4548 : Low CutOff Voltage `settings`
- 4549 : Battery Equalization Voltage `settings`
- 4550 : Battery Equalized Time `settings`
- 4551 : Battery Equalized Timeout `settings`
- 4552 : Equalization Interval `settings`
- 4553 : Binary flags `binary_flags`
    * `0x0010` PV Active `measurement`
    * `0x0100` Battery Discharge `measurement`
    * `0x0200` Battery Charge `measurement`
    * `0x2000` Grid Active `measurement`
    * `0x4000` Load Enabled `measurement`
- 4554 : Binary flags `binary_flags`
    * `0x0001` On Battery `measurement`
    * `0x0100` AC Active `measurement`
    * `0x8000` Grid Active `measurement`
- 4555 : Charger Status *(0 - Off, 1 - Idle, 2 - Active)*
    * `0x000A` Discharging `measurement`
    * `0x000B` Charging `measurement`
    * `0x000C` Idle `measurement`
    * `0x000D` Fully charged `measurement`
- 4556 : Status, reflects register 4555 in states 0x0B, 0x0C, 0x0D, but 0x00 instead of 0x0A `measurement`
- 4557 : Internal temperature sensor `measurement`
- 4558 : stable value 0 `unclear significance`
- 4559 : Grid-tie Operation `settings`
- 4560 : Grid-tie Current `measurement`
- 4561 : LED Pattern Light `settings`
- 4562 : Battery Equalization Activated Immediately Status `settings`
- 4563 : PV2 Voltage `measurement`
- 4564 : PV2 Power `measurement`


### Write registers
*( [+] means tested )*

| Register | Description                                                                         | HVM10.2M |
|----------|-------------------------------------------------------------------------------------|----------|
| 5002     | Buzzer Alarm (range 0-1, settings menu 18)                                          | +        |
| 5003     | Power saving mode (range 0-1,)                                                      |          |
| 5004     | Backlight control (range 0-1, settings menu 20)                                     | +        |
| 5005     | Auto restart when overload occurs (range 0-1, settings menu 6)                      | +        |
| 5006     | Auto restart when over temperature occurs (range 0-1, settings menu 7)              | +        |
| 5007     | Beep On Primary Source Fail (range 0-1, settings menu 22)                           | +        |
| 5008     | Auto return to default display screen (range 0-1, settings menu 19)                 | +        |
| 5009     | Overload Bypass (range 0-1, settings menu 23)                                       | +        |
| 5010     | Record fault code (range 0-1, settings menu 25)                                     | +        |
| 5011     | Battery Equalization (range 0-1, settings menu 30)                                  | +        |
| 5012     | Battery Equalization activated immediately (range 0-1, settings menu 36)            | +        |
| 5013     | Reserve 1  Added functionality to write the full unit serial number                 |          |
| 5014     | Reserve 2  Added functionality to write the full unit serial number                 |          |
| 5015     | Reserve 3  Added functionality to write the full unit serial number                 |          |
| 5016     | Restore Factory Defaults (range 0-1, settings menu 00)                              | +        |
| 5017     | Charger Source Priority (range 0-2 (CSO, SNU, OSO), settings menu 16)               | +        |
| 5018     | Output Source Priority (range 0-3 (USB, SUB, SBU, MKS), settings menu 1)            | +        |
| 5019     | AC input voltage range (range 0-1 (90-280VAC, 170-280VAC), settings menu 3)         | +        |
| 5020     | Battery type (range 0-5 (AGM, USE, LIB, LIC, LIP, LIL), settings menu 5)            | +        |
| 5021     | Output frequency (range 0-1 (50 Hz, 60 Hz), settings menu 9)                        | +        |
| 5022     | Max Total Charge Current (range 10-160 (step 10), settings menu 2)                  | +        |
| 5023     | Output voltage (range 220, 230, 240, settings menu 10)                              | +        |
| 5024     | Utility Charge Current (range 2, 10 - 140 (step 10), settings menu 11)              | +        |
| 5025     | Comeback Utility Mode Voltage (SBU) (0.5 Volts step, settings menu 12)              | +        |
| 5026     | Comeback Battery Mode Voltage (SBU) (0.5 Volts step, settings menu 13)              | +        |
| 5027     | Bulk charging voltage (settings menu 26)                                            | +        |
| 5028     | Floating charging voltage (settings menu 27)                                        | +        |
| 5029     | Low DC cut-off voltage (settings menu 29)                                           | +        |
| 5030     | Battery equalization voltage (settings menu 31)                                     | +        |
| 5031     | Battery equalized time (settings menu 33)                                           | +        |
| 5032     | Battery equalized timeout (settings menu 34)                                        | +        |
| 5033     | Equalization interval (settings menu 35)                                            | +        |
| 5034     | GRID-tie operation (settings menu 37)                                               | +        |
| 5035     | GRID-tie current (range 2-30, 0.2 Volts step, settings menu 38)                     | +        |
| 5036     | LED Pattern Light (settings menu 39)                                                | +        |
| 5037     | Dual Output (settings menu 410)                                                     | +        |
| 5038     | Exit The Dual Output Voltage Point (range 40-52, 0.1 Volts step, settings menu 42)  | +        |
| 50xx     | bms communication address (settings menu 43)                                        |          |
| 50xx     | delayed grid connection (settings menu 44)                                          |          |
| 50xx     | battery soc percentage disconnection voltage (settings menu 45)                     |          |