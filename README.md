# openvpn-installation

#### Find your public IP address

##### Use any one of the following command to find out your IPv4 public address. If your internface name is eth0 or eth1, enter:
`$ ip addr show eth0`
or
`$ ip addr show eth1`

or use the host command or dig command as follows:
`$ host myip.opendns.com resolver1.opendns.com`

or
`$ dig TXT +short o-o.myaddr.l.google.com @ns1.google.com`

![Sample output](https://www.cyberciti.biz/media/new/faq/2016/06/my-public-ip.jpg)

##### Run the bash file
`$ sudo bash openvpn-install.sh`
![run](https://www.cyberciti.biz/media/new/faq/2016/06/openvpn-setup.jpg)

##### How to see added firewall rules ?
`$ cat /etc/rc.local`

##### Where to see openvpn server config file?
`$ cat /etc/openvpn/server.conf`

##### How to view connected users to open vpn server?
`$ sudo cat /etc/openvpn/openvpn-status.log`

##### How do I start/stop/restart OpenVPN server on Ubuntu Linux 16.04 LTS?

Type the following command stop the OpenVPN service:
`$ sudo systemctl stop openvpn@server`

Type the following command start the OpenVPN service:
`$ sudo systemctl start openvpn@server`

Type the following command restart the OpenVPN service:
`$ sudo systemctl restart openvpn@server`

##### How do I start/stop/restart OpenVPN server on Ubuntu Linux 14.04 LTS?

Type the following command stop the OpenVPN service:
`$ sudo /etc/init.d/openvpn stop`

Type the following command start the OpenVPN service:
`$ sudo /etc/init.d/openvpn start`

Type the following command restart the OpenVPN service:
`$ sudo /etc/init.d/openvpn restart`

###### Linux OpenVPN client configuration

First, install the openvpn client, enter:
`$ sudo yum install openvpn`
or
`$ sudo apt install openvpn`

Next, copy xyz.ovpn as follows:
$ sudo cp xyz.ovpn /etc/openvpn/client.conf

Test connectivity from the CLI:
$ sudo openvpn --client --config /etc/openvpn/client.conf

Your Linux system will automatically connect when computer restart using /etc/init.d/openvpn script:
`$ sudo /etc/init.d/openvpn start`

For systemd based system, use the following command:
`$ sudo systemctl start openvpn@client`

##### How do I add a new client?
run the script again:
`$ sudo bash openvpn-install.sh`
then select option 1 and type client name

##### How do I delete/revoke existing user certificate?
Run the script:
`$ sudo bash openvpn-install.sh`
Type 2 option and you will see a list of all the existing client certificate you want to revoke.
