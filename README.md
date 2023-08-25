# Cisco Router and Switch Commands

## 1.0 Basic Switch and Router commands


### basic device configuration
```
no ip domain-lookup
hostname S1
service password-encryption
enable secert class
banner motd #
dont hack me. or ill come after you #
```

### basic Console configuration
```
line con 0
password cisco
login
logging synchronous
exit
```
### basic Telnet configuration
```
line vty 0 4
password cisco
login
exit
```
### Generic show commands
```
show run
show ip int brief
show version  
show interfaces

```

## 2.0 router and switch security

### ssh login

```
service password-encryption
security passwords min-length 8    
no ip domain-lookup  
ip domain-name sg.local  
username stave secert Password1   
crypto key generate rsa 1024  
login block-for 100 attempts 3 within 100 

line vty 0 4
transport input ssh  
login local
exec-timeout 10 

show ip ssh
```

```
ip ssh time-out 50
ip ssh authentication-retries 3 
```

```
C:\>ssh steve@192.168.100.254  
```

## 3.0 Switch commands

```
show mac address-table 

show vlan 
show interface vlan1  
show ip interface vlan1  

show interface G0/1
```

### 3.1 Switch security

### switch management security on VLan 100 and restricted ports 

```
vlan 100
interface vlan100
ip address 192.168.100.254 255.255.255.0
no shutdown
exit
interface range F0/10 - 11 , G0/2
switchport access vlan 100
exit
exit

show vlan brief  
ip default-gateway 192.168.100.1

show interface vlan 100
```


### switch shutdown unused ports  
```
interface range F0/3-24 , G0/2
shutdown
```

### switch port security on used ports  

```
interface range f0/0-2
switchport port-security

show port security
show port security F0/0  
show interface F0/0
```

## 4.0 Router commands

### Router show commands
```
show ip route
```

### Router Interface configuration
```
interface G0/0/0
ip address 192.168.1.1 255.255.255.0
no shutdown

```

