git clone git@github.com:espressif/esptool.git
cd esptool
pip install --user -e .


## 2021-03-04 _ Firmware falshen
* git clone git@github.com:Baitcookie/esptool-ck.git
* ESPEasy von website laden: https://github.com/letscontrolit/ESPEasy/releases 
    * Versteckt bei *Assetts*
    *  ESPEasy_ESP82xx_mega-20210223.zip nehmen
* nach /$HOME/ESPEasy entpacken
* 
* Link esptool to ESPEasy folder (e.g. ln -s /$HOME/gitlab/esptool-ck/esptool /$HOME/ESPEasy)
* flash_espeasy.sh nach /$HOME/ESPEasy/ kopieren
* cd /$HOME/ESPEasy/bin
* ./../flash_espeasy.sh
* Passende Firmware auswählen (e.g. ESP_Easy_mega_20210223_normal_ESP8266_1M.bin)

## Serielle Steuerung
sudo apt install cutecom 
cutecom
* settings
    Write* Baud: 115200, Bits: 8, No FLow, Read/Write, No parity, stop
* Set WIFI:
    WifiSSID <ssid>
    WifiKey <secret>
    WifiConnect

| Debug                   | Internal  | Change Serial port debug level                                                                                                                 | Debug <1-4>                                                                                 |
|-------------------------|-----------|------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------|
| Delay                   | Rules     | Delay rule processing                                                                                                                          | Delay <delay in milliSeconds>                                                               |
| Event                   | Special   | Create an event, it's possible to send a float value along as well.                                                                            | event,<eventName> event,<eventName>=<eventValue>                                            |
| GPIO                    | Plugin    | Direct control of output pins                                                                                                                  | See:GPIO                                                                                    |
| Status                  | Plugin    | Get a status set by GPIO/PWM/Servo command.                                                                                                    | Status,GPIO,<pin number>                                                                    |
| IP                      | Internal  | Change IP address                                                                                                                              | IP <IP address>                                                                             |
| LongPulse               | Plugin    | Direct pulse control of output pins                                                                                                            | See:GPIO                                                                                    |
| LongPulse_mS            | Plugin    | Direct pulse control of output pins, same as above but using mSeconds instead of Seconds.                                                      | See:GPIO                                                                                    |
| Name                    | Internal  | Set the name of the unit                                                                                                                       | Name <new name>                                                                             |
| Password                | Internal  | Set the password of the unit                                                                                                                   | Password <new password>                                                                     |
| Pulse                   | Plugin    | Direct pulse control of output pins                                                                                                            | See:GPIO                                                                                    |
| Publish                 | Rules     | Send command using MQTT broker service                                                                                                         | Publish <topic>, <value>                                                                    |
| PWM                     | Plugin    | Direct PWM control of output pins                                                                                                              | See:GPIO                                                                                    |
| Reboot                  | Internal  | Reboot the ESP                                                                                                                                 | Reboot                                                                                      |
| Reset                   | Internal  | Reset config to factory default. Caution, all settings will be lost!                                                                           | Reset                                                                                       |
| ResetFlashWriteCounter  | Internal  | Reset flash write to zero.                                                                                                                     | ResetFlashWriteCounter                                                                      |
| Rules                   | Internal  | Rules enabled (1) or rules disabled (0)                                                                                                        | Rules,<value>                                                                               |
| Tone                    | Plugin    | Play tone via speaker or piezo                                                                                                                 | See:Buzzer (RTTTL)                                                                          |
| Rtttl                   | Plugin    | Play melody via speaker or piezo                                                                                                               | See:Buzzer (RTTTL)                                                                          |
| Save                    | Internal  | Save config to persistent flash memory                                                                                                         | Save                                                                                        |
| SendTo                  | Rules     | Send command to other ESP (using UDP)                                                                                                          | SendTo <unit nr>, <command>                                                                 |
| SendToHTTP              | Rules     | Send command to other network device using HTTP. Example for domain: SendToHTTP temperatur.nu,80,/rapportera.php?hash=123abc456&t=[temp2#out]  | SendToHTTP <IP address>, <Portnumber>, <command> SendToHTTP <domain>, <Portnumber>, </url>  |
| SendToUDP               | Rules     | Send command to other network device using UDP                                                                                                 | SendToUDP <IP address>, <Portnumber>, <command>                                             |
| Servo                   | Plugin    | Direct control of servo motors                                                                                                                 | See:GPIO  Example for MQTT: <MQTT subscribe template>/cmd Servo 1 0 120                     |
| Settings                | Internal  | Show settings on serial terminal                                                                                                               | Settings                                                                                    |
| TaskClear               | Internal  | Delete the given task/device                                                                                                                   | TaskClear,<task/device nr>                                                                  |
| TaskClearAll            | Internal  | Delete ALL task/device                                                                                                                         | TaskClearAll                                                                                |
| TaskRun                 | Internal  | Run/excecute the given task/device, use to manually force an update/read of the task.                                                          | TaskRun,<task/device nr>                                                                    |
| TaskValueSet            | Rules     | Set values on a Dummy Task device                                                                                                              | TaskValueSet,<task/device nr>,<value nr>,<value/formula>                                    |
| TimerSet                | Rules     | Start a timed event                                                                                                                            | TimerSet,<timernr>,<timeInSeconds>                                                          |
| Unit                    | Internal  | Set the unit number                                                                                                                            | Unit <unit number>                                                                          |
| WifiAPKey               | Internal  | Change AP WPA key                                                                                                                              | WifiAPKey <WPA key>                                                                         |
| WifiAPMode              | Internal  | Force the unit into AP mode.                                                                                                                   | WifiAPMode                                                                                  |
| WifiConnect             | Internal  | Connect to configured wireless network                                                                                                         | WifiConnect                                                                                 |
| WifiDisconnect          | Internal  | Disconnect from wireless network                                                                                                               | WifiDisconnect                                                                              |
| WifiKey                 | Internal  | Change WPA key for primary WiFi                                                                                                                | WifiKey <Wifi WPA key>                                                                      |
| WifiKey2                | Internal  | Change WPA key for secondary WiFi                                                                                                              | WifiKey2 <Wifi WPA key>                                                                     |
| WifiScan                | Internal  | Scan Wireless networks                                                                                                                         | WifiScan                                                                                    |
| WifiSSID                | Internal  | Change SSID to connect as primary WiFi                                                                                                         | WifiSSID <SSID>                                                                             |
| WifiSSID2               | Internal  | Change SSID  to connect as secondry WiFi                                                                                                       | WifiSSID2 <SSID>                                                                            |



## Connect Wifi
ESP-Easy (SSID)
Password: configesp


## Zugriff Weboberfläche

http://esp-easy
or fqdn: 
http://esp-easy.fritz.box
192.168.4.1

##
configure wifi and sensors:

* DS18b20
    * TX: GPIO-2, no RX
##
http://192.168.4.1/?cmd=wificonnect
