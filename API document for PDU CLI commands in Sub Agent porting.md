## API document for PDU CLI commands in Sub Agent porting ##

![logo](https://github.com/daming33/hello-world/SQ_logo.png "SQ ELECTRONICS")

Description: This document is API interface for PDU CLI command in Control4 Sub-Agnet porting. It's available for both simulator and PDU. The difference between simulator and PDU is that PDU will do real command behavior but simulator do nothing except save some parameters and return same value.

#### 1. System cmd API
1.1 `CmdGetVer()`
*******
    #include "pdu_common.h"

    RET_CODE CmdGetVer (char *ver, int32_t len)
*******
###### Summary
This function will get hardware and software version in string.
###### parameters
ver: used to same version string
len: max length could be saved in ver parameter.
###### Return Value
if get the version message from lower level, return RET_OK, otherwise return RET_ERROR.
###### CLI Command
`ver`
###### Notes
None

1.2 `CmdGetDate()`
***
    #include "pdu_common.h"

    RET_CODE CmdGetDate(uint16_t *year, uint8_t *month, uint8_t *day)
***
###### Summary
Get current calendar date
###### parameters
year: year value get from system
month: month value get from system
day: day value get from system
###### Return Value
if get correct date value from system, return RET_OK,otherwise return RET_ERROR.
###### CLI command
`date`
###### Notes
None

1.3 `CmdSetDate()`
***
    #include "pdu_common.h"

    RET_CODE CmdSetDate(uint16_t year, uint8_t month, uint8_t day)
***
###### Summary
Set calendar date to system
###### parameters
year: year value set to system
month: month value set to system
day: day value set to system
###### Return Value
if set date value to system successfully, return RET_OK, Otherwise return RET_ERROR.
###### CLI command
`date`
###### Notes
None

1.4 `CmdGetTime()`
***
    #include "pdu_common.h"

    RET_CODE CmdGetTime(uint8_t *hour, uint8_t *minute, uint8_t *second)
***
###### Summary
Get current Time in 24 hours
###### parameters
hour: hour value get from system
minute: minute value get from system
second: second value get from system
###### Return Value
if get correct time value from system, return RET_OK,otherwise return RET_ERROR.
###### CLI command
`time`
###### Notes
None

1.5 `CmdSetTime()`
***
    #include "pdu_common.h"

    RET_CODE CmdSetTime(uint8_t hour, uint8_t minute, uint8_t second)
***
###### Summary
Set time to system
###### parameters
hour: hour value set to system
minute: minute value set to system
second: second value set to system
###### Return Value
if set time value to system successfully, return RET_OK, Otherwise return RET_ERROR.
###### CLI command
`time`
###### Notes
None

1.6 `CmdGetTemperature()`
***
    #include "pdu_common.h"

    RET_CODE CmdGetTemperature(int32_t *temp)
***
###### Summary
###### parameters
###### Return Value
###### CLI command
`temp`
###### Notes
None

1.7 `CmdGetHumidity()`
***
    #include "pdu_common.h"

    RET_CODE CmdGetHumidity(uint32_t *rh)
***
###### Summary
###### parameters
###### Return Value
###### CLI command
`rh`
###### Notes
None

1.8 `CmdGetCurrent()`
***
    #include "pdu_common.h"

    RET_CODE CmdGetCurrent(uint8_t iterm, uint32_t *current)
***
###### Summary
###### parameters
###### Return Value
###### CLI command
`cura, curb`
###### Notes
None

1.9 `CmdGetSerialNum()`
***
    #include "pdu_common.h"

    RET_CODE CmdGetSerialNum(uint8_t *sn, uint8_t max_len)
***
###### Summary
###### parameters
###### Return Value
###### CLI command
`ssn`
###### Notes
None

1.10 `CmdSetDefaultParam()`
***
    #include "pdu_common.h"

    RET_CODE CmdSetDefaultParam(void)
***
###### Summary
###### parameters
###### Return Value
###### CLI command
`reinit`
###### Notes
Need to reboot system (by call function RebootSystem) to allow all parameters available after call this function


1.11 `CmdRebootSystem()`
***
    #include "pdu_common.h"

    RET_CODE CmdRebootSystem(void)
***
###### Summary
###### parameters
###### Return Value
###### CLI command
`reboot`
###### Notes
None

#### 2. Outlet access API
2.1 `CmdSwitchOutlet()`
***
    #include "pdu_common.h"

    RET_CODE CmdSwitchOutlet(uint8_t outlet, bool switch)
***
###### Summary
###### parameters
switch: true: on; false: off
###### Return Value
###### CLI command
`pset`
###### Notes
None

2.2 `CmdSwitchAllOutlet()`
***
    #include "pdu_common.h"

    RET_CODE CmdSwitchAllOutlet(bool switch)
***
###### Summary
Switch all outlet on or off
###### parameters
switch: true: on; false: off
###### Return Value
###### CLI command
`ps`
###### Notes
None

2.3 `CmdRebootOutlet()`
***
    #include "pdu_common.h"

    RET_CODE CmdRebootOutlet(uint8_t outlet)
***
###### Summary
###### parameters
###### Return Value
###### CLI command
`prb`
###### Notes
None
2.4 `CmdGetOutletState()`
***
    #include "pdu_common.h"

    RET_CODE CmdSwitchOutlet(uint8_t outlet, bool *state)
***
###### Summary
###### parameters
###### Return Value
###### CLI command
`pshow`
###### Notes
None

2.5 `CmdSetOutletName()`
***
    #include "pdu_common.h"

    RET_CODE CmdSetOutletName(uint8_t outlet, char *pName)
***
###### Summary
###### parameters
###### Return Value
###### CLI command
`pname`
###### Notes
None

2.6 `CmdSetOutletPowerOnDelay()`
***
    #include "pdu_common.h"

    RET_CODE CmdSetOutletPowerOnDelay(uint8_t outlet, uint32_t delay)
***
###### Summary
###### parameters
delay: in second
###### Return Value
###### CLI command
`pdelay`
###### Notes
None

#### 3. Network API
3.1 `CmdShowMac()`
***
    #include "pdu_common.h"

    RET_CODE CmdShowMac(uint8_t *mac)
***
###### Summary
###### parameters
mac: mac[0]-mac[5], network byte order
###### Return Value
###### CLI command
`mac`
###### Notes
None

3.2 `CmdGetWebState()`
***
    #include "pdu_common.h"

    RET_CODE CmdGetWebState(bool *en)
***
###### Summary
###### parameters
###### Return Value
###### CLI command
`web`
###### Notes
None
3.3 `CmdWebEnable()`
***
    #include "pdu_common.h"

    RET_CODE CmdWebEnable(bool en)
***
###### Summary
###### parameters
###### Return Value
###### CLI command
`web`
###### Notes
None


3.4 `CmdGetTelnetState()`
***
    #include "pdu_common.h"

    RET_CODE CmdGetTelnetState(bool *en)
***
###### Summary
###### parameters
###### Return Value
###### CLI command
`Telnet`
###### Notes
None
3.5 `CmdTelnetEnable()`
***
    #include "pdu_common.h"

    RET_CODE CmdTelnetEnable(bool en)
***
###### Summary
###### parameters
###### Return Value
###### CLI command
`telnet`
###### Notes
None

3.6 `CmdGetIP()`
***
    #include "pdu_common.h"

    RET_CODE CmdGetIP(uint32_t *ip)
***
###### Summary
###### parameters
ip：network byte order,192.168.1.220 = 0xc0a801dc
###### Return Value
###### CLI command
`telnet`
###### Notes
None
3.7 `CmdSetIP()`
***
    #include "pdu_common.h"

    RET_CODE CmdSetIP(uint32_t ip)
***
###### Summary
###### parameters
ip：network byte order,192.168.1.220 = 0xc0a801dc
###### Return Value
###### CLI command
`ip`
###### Notes
None
3.8 `CmdConfigNetwork()`
***
    #include "pdu_common.h"

    RET_CODE CmdConfigNetwork(NETWORK_CONFIG_ENUM config)
***
###### Summary
###### parameters
config: auto/static/dhcp
###### Return Value
###### CLI command
`ifconfig`
###### Notes
None
