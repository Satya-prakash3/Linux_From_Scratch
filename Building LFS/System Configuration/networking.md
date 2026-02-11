Here we will do some basic network configurations

cd /etc/sysconfig/

This will provide the kernel an idea to up which netwrok device after boot
cat > ifconfig.enp1s0 << "EOF"
ONBOOT=yes
IFACE=enp1s0
SERVICE=ipv4-dhcp
IP=192.168.122.108
GATEWAY=192.168.122.1
PREFIX=24
BROADCAST=192.168.122.255
EOF


This will create a local DNS file
cat > /etc/resolv.conf << "EOF"
# Begin /etc/resolv.conf

nameserver 8.8.8.8
nameserver 1.1.1.1

# End /etc/resolv.conf
EOF

This will set the hostname 
echo "<lfs>" > /etc/hostname

This will create our hosts file (we can map any domain to a particular IP here)
cat > /etc/hosts << "EOF"
# Begin /etc/hosts

127.0.0.1 localhost
127.0.1.1 lfs
::1       localhost ip6-localhost ip6-loopback
ff02::1   ip6-allnodes
ff02::2   ip6-allrouters

# End /etc/hosts
EOF
