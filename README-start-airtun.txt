apt-get remove libnl3-dev
apt-get install libnl-dev
make
airmon-ng start wlan0 <chennel_of_ssid_to_monitor>
airodump-ng mon0 # get bssid and essid
src/airtun-ng -a <access_oin_bssid_mac> -e <ssid_to_monitor> -p 'wpa_password' mon0
ifconfig at0 up
# 4 way handshake should be captured for airtun to work correctly
