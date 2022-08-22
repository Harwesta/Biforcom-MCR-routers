# Biforcom-MCR-routers
Openwrt for Biforcom MCR-10x MCR-20x indoor/outdoor routers
Full technical description for MCR-10x https://b4com.tech/?page_id=538

Based on: Orange Pi Zero rev.1.5 board.
CPU: Allwinner H2+ Quad-core Cortex-A7 up to 1.2GHz.
RAM: 512MB DDR3.
Storage: TF card (Max. 32GB) / 2MB Spi-NOR Flash.
Network:
- onboard 10/100M Ethernet RJ45 POE +5V (default off).
- Onboard WiFi 	XR819, IEEE 802.11 b/g/n (default off).

Indoor version MCR-10x:
- on main board 2x SMSC LAN9514 USB hub with Eth 10/100M Ethernet converters (LAN1, LAN2).
- on main board up to 3x Quectel EC25-EU LTE modem Cat.4 (two LCC module and one miniPCIE module).
- one omni antenna is connected to each modem.

Outdoor MCR-10x-O:
- on main board 2x Quectel EC25-EU LTE modem Cat.4 (two LCC module).
- 2x2 MIMO panel antenna.

Additional features :
- hardware watchdog MAX6371KA (resets power supply for Orange Pi Zero).
- real time clock DS3231M i2c (TW0 Orange Pi Zero) bus with backup battery CR2032.
- dedicated DC-DC converters TPS54332 3.3V 3A with GPIO-controlled for each modems.

Power adapter indoor MCR-10x: 12V 3A (5.5mm barrel)
Power adapter outdoor MCR-10x-O: passive PoE 12V 3A
