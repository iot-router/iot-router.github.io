# IoT-Router Requirements Convention

## Revision History

| **Date**   | **Revision** | **Description**                             |
| ---------- | ------------ | ------------------------------------------- |
| 2019-10-12 | Rev 1.0      | Initial Version of the Requirement Document |

## Requirement types

| **Status** | **Description**                                             |
| ---------- | ----------------------------------------------------------- |
| MUST       | Mandatory requirement.                                      |
| SHOULD     | Requirement which should be met, but which is not absolute. |
| CAN        | Optional requirement which will strengthen the offering.    |

_Note: Please keep in mind that the current SHOULD &amp; CAN requirements may already become MUST in the course of the next tender. For fast-moving consumer goods, up to 2 tenders per year are not unusual._

# Minimal functionality requirements on the hosting device and on/by the Smart Home Container

## Core requirements

| **ID** | **Status** | **Description**                                              |
| ------ | ---------- | ------------------------------------------------------------ |
| G1     | MUST       | Linux platform. ARM or MIPS SoC families supported by OpenWrt Project ([https://openwrt.org](https://openwrt.org/)). |
| G2     | MUST       | Firmware image based on latest stable version of OpenWrt Linux distribution (or OpenWrt embedded in frameworks like prpl) image with LXC enabled, templates and configured namespaces with root accounts.<br /><br />_Note: The current stable version series of OpenWrt is 18.06, with v18.06.4 being the latest service release of the series, released on July 1st 2019._ |
| G3     | MUST       | At least two usable SH namespace processor cores from the CPUs of the host device with sufficient performance. <br /><br />*For comparison: On a gateway with MIPS Single-Core 880 MHz CPU (MT7621S), the utilization by the overall system, i.e. SH application incl. OpenWrt 14.07, etc., is about **30% on average** .* |
| G4     | MUST       | Sufficient free flash memory for the SH namespace.<br /><br />*For comparison: On a gateway with 256MB flash memory, the consumption by the overall system, i.e. SH application incl. OpenWrt 14.07, libs/bins, etc., is currently **around 80MB** . Temporary logs and recordings are not included.* |
| G5     | MUST       | Sufficient free RAM for the SH namespace.<br /><br />_For comparison:_ _On a gateway with 512MB RAM, the consumption by the overall system, i.e. SH application incl._ _OpenWrt_ _14.07, libs/bins, etc., is currently_ **around 208MB** _._ |
| G6     | MUST       | RF-protocol support for:<br /><br />  - Z-Wave Plus EU _(700 series chips PREFERRED, may be 500 series chip EXCEPT ZM5304 module)_<br />  - ZigBee 3.0 <br /><br /> *Note: Can be, although not preferred, a secured external pluggable transceiver module, but must be an integral part of the overall offer.* |
| G7     | MUST       | 2 x SSID Wi-Fi 2.4 GHz + 5 GHz (IEEE 802.11b/g/n and 802.11a/n/ac), but SHOULD be more, while 1 x SSID is exclusive managed by the SH namespace. |
| G8     | MUST       | 5G NR OR 4G LTE Cat.6 (upwards and 3G fallback) with EU bands. |
| G9     | MUST       | Ethernet port(s) automatically switch between LAN and WAN mode. |
| G10    | MUST       | Wi-Fi SSIDs configurable in Client Mode or Access point Mode. |
| G11    | MUST       | Z-Wave Security 2 (S2) framework and Z-Wave SmartStart.      |
| G12    | MUST       | MultipathTCP support for SH namespace VPN, via virtual networking device, to an endpoint in a faster network or Smart Home Cloud backend. |
| G13    | MUST       | Upgrade to newer or later versions of _OpenWrt_, including 19.07, within a maximum of 6 months. |
| G14    | MUST       | The initial board support package must be available at Mainline _OpenWrt_ prior to shipment to the end customer. |

## Support for operation and quality of service

| **ID** | **Status** | **Description**                                              |
| ------ | ---------- | ------------------------------------------------------------ |
| Q1     | MUST       | Perform continuous firmware maintenance (OS, PKG, etc.) and controlled remote updates on new deliveries and in the installed base. |
| Q2     | MUST       | Service procedures for providing or implementing new namespaces, changing the configuration of existing namespaces, and loading or removing associated third-party services. |
| Q3     | MUST       | System Status Info Page with History about each SH namespace in Router&#39;s responsive Web UI, containing min. CPU Load and memory utilization (RAM/Flash). |
| Q4     | MUST       | Reliable WAN failover/failback handling in less than 5 seconds (failover/failback must be used in case MultipathTCP is not in use or not working). |
| Q5     | MUST       | Reliable and automatic connection re-establishment after a mobile network failure. |
| Q6     | MUST       | Globally functioning and automatic logon to the mobile network of an operator (MNO) or virtual operator (MVNO), access parameters derived directly from the inserted SIM card, immediately after switching on. |
| Q7     | MUST       | Fully configured watchdog functionality for important processes/containers on the device, i.e. detect failure of such a component and trigger defined actions. |
| Q8     | MUST       | The hardware and the operating system including its libraries and drivers must not limit the performance of any of the required RF technologies according to their specification at any time. |
| Q9     | MUST       | The power-on time of the device, application case #1, i.e. to put the device into an interactive, usable state, must be less than 60s. |
| Q10    | MUST       | Any software MUST support IPv4 and SHOULD support IPv6 and be able to communicate over both types of networks. |
| Q11    | MUST       | Timely interaction and exchange of bug fixes to and from specific _OpenWrt_ software and features with the project. |
| Q12    | MUST       | Correction of critical security problems within 2 weeks as firmware updates. |
| Q13    | MUST       | Support signed updates to ensure system integrity.           |
| Q14    | SHOULD     | Use of instances on preferred cloud platforms for the cloud functionalities required by the manufacturer as part of the implementation for production operations. Depending on the requirements or suitability, these are e.g. Exoscale ([https://www.exoscale.com/](https://www.exoscale.com/)) or Cumulocity IoT ([https://cumulocity.com)](https://cumulocity.com)). |
| Q15    | SHOULD     | Support for remote management via TR-069 and associated additional TRs. Source code and samples for custom parameter provisioning provided. |

## Hardware and related requirements

| **ID** | **Status**        | **Description**                                              |
| ------ | ----------------- | ------------------------------------------------------------ |
| H1     | MUST              | Attractive and living-room suitable device design.           |
| H2     | MUST              | Min 1 x Gigabit Ethernet, but SHOULD be more.                |
| H3     | MUST              | Min 1 x USB 2.0 port, but SHOULD be higher version.          |
| H4     | MUST              | Status LEDs.                                                 |
| H5     | MUST              | WPS button.                                                  |
| H6     | MUST              | Physical Reset button.                                       |
| H7     | MUST              | EU Power supply.                                             |
| H8     | MUST              | Operating Temperature range -10 to 55 ℃.                     |
| H9     | MUST              | Storage Temperature range -10 to 55 ℃.                       |
| H10    | MUST              | Battery backup. Min. 2 hours of full functionality with monitoring of battery status and battery life cycle including virtual API. DIY battery replacement. |
| H11    | MUST              | Compliance with requirements of latest version Z/IP Gateway SDK.\* |
| H12    | MUST              | Compliance with requirements of latest version ZigBee SDK.\* |
| H13    | MUST/<br />SHOULD | Wi-Fi SoC with exposed channel state information (CSI). **MUST** if ZigBee/Zwave hardware support is provided via an external pluggable transceiver module, otherwise **SHOULD**. |
| H14    | SHOULD            | Tamper switch, which signals access to the battery and SIM card area, e.g., for sabotage detection. |
| H15    | SHOULD            | Embedded SIM (MFF2 eSIM) support.                            |
| H16    | SHOULD            | Built-in siren with min 100dB; adjustable                    |
| H17    | CAN               | Bluetooth 5.x incl. Virtual BT Driver API. \*                |
| H18    | CAN               | HDMI connection with the communication channels: Display Data Channel (DDC), Transition-Minimized Differential Signaling (TMDS), Consumer Electronics Control (CEC), HDMI Ethernet Channel (HEC)and Content protection (HDCP) according to the latest HDMI standard. |
| H19    | CAN               | Audio interfaces such as microphone with hardware kill switch and speaker that meet the requirements of leading voice assistance services. |

## Developer support requirements

| **ID** | **Status** | **Description**                                              |
| ------ | ---------- | ------------------------------------------------------------ |
| D1     | MUST       | Provision of min. 5 fully documented open reference IoT router/cube SDK devices per type/model with unlimited root access and source code for evaluation and verification. |
| D2     | MUST       | Comprehensive SDK with complete documentation, code samples, toolchain, etc. |
| D3     | MUST       | Technical support resource available. Direct contact with engineer. |
| D4     | MUST       | Support for remote troubleshooting and debugging.            |
| D5     | MUST       | Provision of end-user firmware versions corresponding to the functionality of the Reference SDK devices (see D1). |
| D6     | SHOULD     | Virtualized version of platform for easy testing and debugging. |
| D7     | SHOULD     | Remote speedtest tools.                                      |

## Regulatory and other certification requirements

| **ID** | **Status** | **Description**                                              |
| ------ | ---------- | ------------------------------------------------------------ |
| R1     | MUST       | CE, ROHS2 and other mandatory EU/CEE certifications and in the specified regions/countries. |
| R2     | MUST       | Complies with all Z-Wave, Zigbee and RF standards and regulations in the specified regions/countries to be certified or approved. The certifications by testing institutes must be documented if required by the standards. |
| R3     | SHOULD     | Wi-Fi EasyMesh certification.                                |

## Software adaptation requirements

| **ID** | **Status** | **Description**                                              |
| ------ | ---------- | ------------------------------------------------------------ |
| S1     | MUST       | Min. Java 6 / V1.6 (or higher) and Java Reflection support with a small and compact Java Virtual Machine that meets the associated and complete JVM specification. |
| S2     | MUST       | API/support for complete &quot;power cycle reset&quot; of the SH namespace, also in battery operation. |
| S3     | MUST       | Virtual Networking Driver API. \*                            |
| S4     | MUST       | Virtual Mobile Networking Driver API. \*                     |
| S5     | MUST       | Zigbee 3.0 Zigbee Driver API. \*                             |
| S6     | MUST       | Z-Wave Z/IP Driver API. \*                                   |
| S7     | MUST       | Virtual LED Driver API. \*                                   |
| S8     | MUST       | Virtual Hardware button callback API. \*                     |
| S9     | MUST       | Virtual I/O driver for any type of additional equipment. \*  |
| S10    | MUST       | Virtual SH namespace API. \*                                 |
| S11    | SHOULD     | Generic responsive HTML5 user interface for local device administration including CSS compliant support for custom design implementation. |
| S12    | CAN        | Generic, but standardized and/or freely licensable software abstraction layer for decoupling manufacturer-specific hardware components. |
| S13    | CAN        | SDKs or other support for the local integration of Wi-Fi/LAN based Home Automation devices of various third-party platforms or device manufacturers. |

\* Well defined and comprehensive API&#39;s MUST be provided for integration into applications. If existing chip vendor driver APIs are not natively available for _OpenWrt_, the driver APIs from their Linux-based SDKs MUST be ported to _OpenWrt_ by the device vendor. The general provision of all driver APIs is done as an integrated part of the router FW Image/Build.

**References:**

- Z/IP Gateway SDK as part of via SiLabs development tool &quot;Simplicity Studio&quot;; current version 7.11.x
- ZigBee SDK 6.x

\*\* A safe CPU load on the host device of maximum 85% MUST be maintained under the assumption that 3-5 lightweightcontainer apps with a load comparable to the SH client are executed simultaneously.

# Minimal functional requirements on the hosting device due to additional service agents, clients and apps running in a container.

## Monitoring and protection service &quot;M\_namespace&quot;

Basic requirements that apply through a protection service designed for the home network and all connected (IoT) devices.

| **ID** | **Status** | **Description**                                              |
| ------ | ---------- | ------------------------------------------------------------ |
| M1     | MUST       | Requires about 1%-2% of CPU resources in average and 5% in load, based on MIPS MT7621S Single-Core 880 MHz CPU. |
| M2     | MUST       | Requires up to 16 MB of RAM resources.                       |
| M3     | MUST       | Requires up to 20MB, but SHOULD be 25MB, of non-volatile memory. |
| M4     | MUST       | Kernel modules, binaries and iptables extensions to include: Conntrack \| ebtables \| iptables-mod-conntrack-extra \| iptables-mod-ipmark \| iptables-mod-nflog \| iptables-mod-nfqueue \| kmod-br-netfilter \| libopenssl \| ca-certificates \| curl |
| M5     | SHOULD     | APIs or iptables rules to control hardware acceleration.     |
| M6     | SHOULD     | LXC Containers are run in the same Network Space as the HOST for proper traffic steering. |
| M7     | SHOULD     | LXC Containers have to have an ability to run iptables commands. |

## Channel State Information (CSI) service &quot;C\_namespace&quot;

Basic requirements that apply when Channel State Information (CSI) is supported.

| **ID** | **Status** | **Description**                                              |
| ------ | ---------- | ------------------------------------------------------------ |
| C1     | MUST       | Requires about 10%-15% of CPU resources (based on MIPS MT7621S Single-Core 880 MHz CPU). |
| C2     | MUST       | Requires about 2 MB of RAM resources.                        |
| C3     | MUST       | Requires about 1 MB of non-volatile memory.                  |
| C4     | MUST       | Restriction-free Internet access.                            |
| C5     | MUST       | List connected WiFi devices.                                 |
| C6     | MUST       | Get IP Address of WiFi connected devices.                    |
| C7     | MUST       | Send and Receive ICMP packets to/from connected WiFi devices. |
| C8     | MUST       | Access to WiFi statistics of connected devices. See Channel State Information (CSI) requirement table. |

## Channel State Information (CSI) requirement table

Detail requirements that apply when Channel State Information (CSI) is supported.

| **ID** | **Status** | **WiFi Statistic**        | **Description**                                              |
| ------ | ---------- | ------------------------- | ------------------------------------------------------------ |
| I1     | MUST       | CSI                       | CSI for each spatial stream                                  |
| I2     | MUST       | Timestamp                 | Received packet timestamp                                    |
| I3     | MUST       | RSSI                      | RSSI for each received packet                                |
| I4     | MUST       | nTX                       | Number of antennas used to transmit the packet.              |
| I5     | MUST       | nRX                       | Number of antennas that received the packet.                 |
| I6     | MUST       | Channel                   | Channel used to transmit the packet.                         |
| I7     | MUST       | Client MAC                | The MAC Address of the WiFi device that transmitted the packet. |
| I8     | MUST       | Bandwidth                 | The bandwidth used for the packet transmission.              |
| I9     | MUST       | Number of Subcarriers     | Number of subcarriers in the CSI.                            |
| I10    | MUST       | Number of Spacial Streams | Number of Spacial Streams in the CSI.                        |
| I11    | MUST       | Decimation                | Status and level of grouping performed for the CSI estimation. |
| I12    | SHOULD     | CSI calculation error     | Status if there was a calculation error of the CSI.          |
| I13    | SHOULD     | AGC Gain                  | Gain used by AGC applied in baseband                         |
| I14    | SHOULD     | Rate                      | Data rate used for packet transmission. Similar information available with MCS index. |
| I15    | SHOULD     | Beamforming               | Status if beamforming was used for the packet transmission.  |
| I16    | SHOULD     | Error Vector Magnitude    | Error Vector Magnitude for the estimation of the CSI.        |
| I17    | SHOULD     | MCS                       | The MCS index of the transmitted packet. Similar information available with Rate. |
| I18    | SHOULD     | Antenna Permutation       | MUST if possible Antenna Permutation, but depending on driver and manufacturer, there may not be Antenna Permutation. |
| I19    | SHOULD     | CSI for Multi-Devices     | Parallel reporting of WiFi statistics (including CSI) from more than one device connected. Only applies in Access Point mode. |

_Note: Unfortunately, we cannot guarantee that no printing errors have occurred despite careful preparation and checking._
