# Install required packages

sudo apt-get install wpasupplicant iw wireless-tools

# See available interfaces

iwconfig

# Scan for networks

iw wlan0 scan 
iw wlan0 scan | grep SSID

# Get the psk value of the wifi password

wpa_passphrase "SSID Name" Passphase >> /etc/network/interfaced.d./wlan0 


# /etc/network/interfaces.d/wlan0

auto wlan0
iface wlan0 inet dhcp
	wpa-ssid "SSID Name"
	wpa-psk <psk-value-of-passphrase-goes here>
}
