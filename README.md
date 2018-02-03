# openvpn-installation

#### Find your public IP address

##### Use any one of the following command to find out your IPv4 public address. If your internface name is eth0 or eth1, enter:
`$ ip addr show eth0`

OR
`$ ip addr show eth1`

Or use the host command or dig command as follows:
`$ host myip.opendns.com resolver1.opendns.com`

OR
`$ dig TXT +short o-o.myaddr.l.google.com @ns1.google.com`

##### Run the bash file
`$ sudo bash openvpn-install.sh`
