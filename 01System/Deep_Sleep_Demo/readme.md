##SDK Version: esp8266_nonos_sdk_v2.0.0_16_07_19
##Platform: ESP-LAUNCHER BOARD

##Purpose:
Test ESP8266 chip current under deep sleep mode.

##Procedure:
1.Connect GPIO16 to EXT_RSTB on hardware.

2.Please configure the ssid and the password of the router you want to connect to in user_main.c.

	os_sprintf(stationConf.ssid, "TP-LINK-FD");
	os_sprintf(stationConf.password, "aaaaaaaa");

3.Copy the examples next to bin/ folder in the SDK folder. The SDK folder should have folders inside it like : bin, examples, third party...Enter example folder, select the example you want to , run ./gen_misc.sh, and follow the tips and steps.

4.Select 1,1,2,0,2 during compiling step 1 to 5. Then bin files will generate in BIN_PATH folder which is bin/upgrade.

5.Download bin files to ESP-LAUNCHER as below sittings.

	Download address of each bin files
	blank.bin						0xFE000
	esp_init_data_default.bin		0xFC000
	boot_v1.6.bin					0x00000
	user1.2048.new.2.bin			0x01000
	
	Flash download tool settings.
	CrystalFreq: 26M
	SPI SPEED: 40MHz
	SPID MODE: QIO
	FLASH SIZE: 8Mbit

##Result:
1.Connect to the router your configure.

2.After 10 second, chip will go to deep sleep mode.

3.After 10 second, chip will reset and wake up from deep sleep mode, and connect to router again.
 
##Uart0 Log:

	ets Jan  8 2013,rst cause:2, boot mode:(3,2)	load 0x40100000, len 2408, room 16 	tail 8	chksum 0xe5	load 0x3ffe8000, len 776, room 0 	tail 8	chksum 0x84	load 0x3ffe8310, len 632, room 0 	tail 8	chksum 0xd8	csum 0xd8	2nd boot version : 1.6	  SPI Speed      : 40MHz	  SPI Mode       : QIO	  SPI Flash Size & Map: 8Mbit(512KB+512KB)	jump to run user1 @ 1000	rf cal sector: 251	rf[112] : 00	rf[113] : 00	rf[114] : 01	SDK ver: 2.0.0(656edbf) compiled @ Jul 19 2016 17:58:40	phy ver: 1055, pp ver: 10.2	SDK version:2.0.0(656edbf)	deep sleep test start	mode : sta(18:fe:34:ed:87:e3)	add if0	scandone	state: 0 -> 2 (b0)	state: 2 -> 3 (0)	state: 3 -> 5 (10)	add 0	aid 2	cnt 	connected with TP-LINK-FD, channel 12	dhcp client start...	event 0	ip:192.168.99.157,mask:255.255.255.0,gw:192.168.99.1	event 3	0	start sleeping...	state: 5 -> 0 (0)	rm 0	del if0	usl	event 1	 ets Jan  8 2013,rst cause:2, boot mode:(3,2)	load 0x40100000, len 2408, room 16 	tail 8	chksum 0xe5	load 0x3ffe8000, len 776, room 0 	tail 8	chksum 0x84	load 0x3ffe8310, len 632, room 0 	tail 8	chksum 0xd8	csum 0xd8	2nd boot version : 1.6	  SPI Speed      : 40MHz	  SPI Mode       : QIO	  SPI Flash Size & Map: 8Mbit(512KB+512KB)	jump to run user1 @ 1000	rf cal sector: 251	rf[112] : 00	rf[113] : 00	rf[114] : 01	SDK ver: 2.0.0(656edbf) compiled @ Jul 19 2016 17:58:40	phy ver: 1055, pp ver: 10.2	SDK version:2.0.0(656edbf)	deep sleep test start	mode : sta(18:fe:34:ed:87:e3)	add if0	scandone	state: 0 -> 2 (b0)	state: 2 -> 3 (0)	state: 3 -> 5 (10)	add 0	aid 2	cnt 	connected with TP-LINK-FD, channel 12	dhcp client start...	event 0	ip:192.168.99.157,mask:255.255.255.0,gw:192.168.99.1	event 3	0