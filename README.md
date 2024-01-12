# Biforcom-MCR-routers
Openwrt for Biforcom MCR-10x MCR-20x indoor/outdoor routers

# Biforcom MCR-10x
Full technical description for MCR-10x https://b4com.tech/?page_id=538.

Based on: Orange Pi Zero rev 1.4/1.5 board.

CPU: Allwinner H2+ Quad-core Cortex-A7 up to 1.2GHz.
RAM: 256/512MB DDR3.
Storage: TF card (Max. 32GB) / 2MB Spi-NOR Flash.

Network:
- onboard 10/100M Ethernet RJ45 (LAN0, POE +5V - default off).
- onboard WiFi 	XR819, IEEE 802.11 b/g/n (default off).

Indoor version MCR-10x:
- on main board 2x SMSC LAN9514 USB hub with Eth 10/100M Ethernet converters (LAN1, LAN2).
- on main board up to 3x Quectel EC25-EU LTE modem Cat.4 (two LCC module and one miniPCIE module).
- SMA antenna connector to each modem to 'main' modem port, another variant use SMA-to-IPEX Y-cable for 'main' and 'aux' modem port.

Outdoor MCR-10x-O:
- on main board 2x Quectel EC25-EU LTE modem Cat.4 (two LCC module), 2x2 MIMO panel antenna.

Additional features:
- hardware watchdog MAX6371KA (resets power supply for Orange Pi Zero).
- real time clock DS3231M i2c (TW0 Orange Pi Zero) bus with backup battery CR2032 (indoor version only).
- dedicated DC-DC converters TPS54332 3.3V 3A with GPIO-controlled for each modems.
- main DC-DC converters TPS54332 5V 3A with watchdog MAX6371KA controlled.

Power adapter indoor MCR-10x: 12V 3A (5.5mm barrel)
Power adapter outdoor MCR-10x-O: passive PoE 12V 3A

# Biforcom MCR-20x
Full technical description for MCR-20x https://b4com.tech/?page_id=280.

Based on: Nanopi Core board.

CPU: Allwinner H3 Quad-core Cortex-A7 up to 1.2GHz.
RAM: 512MB DDR3.
Storage: TF card (Max. 32GB) / 2MB Spi-NOR Flash.

Network:
- Nanopi Core 10/100M Ethernet RJ45 on main board (LAN0).
- on main board 3x SMSC LAN9514 USB hub with Eth 10/100M Ethernet converters (LAN1, LAN2, LAN3).
- on main board up to 3x Quectel EC25-EU LTE modem Cat.4 (LCC module).
- two omni antenna connected to each modem, MIMO 2x2 supported
- one USB 2.0

Additional features :
- supervisor/watchdog/buttons controller based on STM32L052T8 (resets power supply for Nanopi Core and modems).
- dedicated DC-DC converters TPS54332 3.3V 3A with STM32L052T8-controlled for each modems.
- main DC-DC converters TPS54332 5V 3A with watchdog STM32L052T8-controlled.
- onboard cradle with Li-Ion 18650 2200mAh battery. Charger and step-up converter for uninterruptible power supply.

Power adapter: 12V 4A (5.5mm barrel)

For normal Openwrt working you need:
1. Cut 3 wires near at STM32.
![MCR-202_STM32_cut_29-30-31](https://user-images.githubusercontent.com/65107625/186838787-e2084d41-d34a-4a55-9a14-95e1219d3175.jpg)

2. Solder two jumper from GPIO то pin #3 U1 and U3 as a pictures.
![MCR-202_modems_power](https://user-images.githubusercontent.com/65107625/186840582-ff58f7bf-eae1-4672-a28c-e2a8379ed1c3.jpg)

3. Cut or pull-up pin #3 U2.
