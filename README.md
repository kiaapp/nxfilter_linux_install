# nxfilter_linux_install
Install nxfilter on Linux system.
Befor install nxfilter , install java on your system.
   and type this code in terminal:
    sudo service systemd-resolved stop
    sudo systemctl disable systemd-resolved
    sudo rm /etc/resolv.conf
   sudo sh -c "echo nameserver 8.8.8.8 > /etc/resolv.conf"
1.Download nxfilter.zip from this link:
https://nxfilter.org/p4/download/
2.Extrat and chang folder name to nxfilter.
3.Copy to /etc in linux file system.
4.Go to etc/nxfilter/bin and open terminsl and type:
 sudo chmod +x *.sh 
 sudo sh startup.sh
5.wait until all filter category rows insert.
6.Press CTR+C to exit frodm insert.
7.Type:
 sudo nano /etc/systemd/system/nxfilter.service 
 and insert this script sode:
 [Unit]
Description=Start nxfilter

[Service]
Type=oneshot
ExecStart=/etc/nxfilter/bin/startup.sh

[Install]
WantedBy=multi-user.target
8.save and exit nano
9.Type:
systemctl enable --now nxfilter.service
then
reboot
10.After reboot in browser type:
127.0.0.1/admin  user:admin   password:admin
and read this help for manage nxfilter setting: 
https://tutorial.nxfilter.org
