This is a cheatsheet for commands and tools commonly used in ethical hacking.

1) Change Mac      : a) ifconfig ath0 down b) ifconfig ath0 hw ether <new_mac> c) ifconfig ath0 up

2) Sniffing Packets: a) airodump-ng wlan0 or b) airodump-ng --bssid <ap_mac> --channel <channel> --write <out_file> wlan0

3) Deauth          : a)  aireplay-ng -0 1 -a 00:14:6C:7E:40:80 -c 00:0F:B5:34:30:30 ath0
4) Fake Auth       : a)  aireplay-ng -1 0 -a 00:14:6C:7E:40:80 -h 00:09:5B:EC:EE:F2 ath0

5) Cracking WEP/WPA: Use of aircrack-ng depends on encryption

6) Reconnaissance  : a) netdiscover -r 10.0.2.1/24 b) nmap / zenmap(GUI)

7)
       
