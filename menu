#!/bin/bash 
# =========================================
# Menu For Script
# Edition : Stable Edition V2.0
# Auther  : TekiroVpn X LynzVpn X ProfAmpoh
# (C) Copyright 2023-2024
# =========================================
# COLOR VALIDATION
clear
y='\033[1;33m' #yellow
BGX="\033[42m"
CYAN="\033[96m"
z="\033[96m"
BIRed='\033[1;91m'        # Red
RED='\033[0;31m'
NC='\033[0m'
gray="\e[1;30m"
Blue="\033[0;34m"
green='\033[0;32m'
grenbo="\e[92;1m"
purple="\033[1;95m"
YELL='\033[0;33m'
#INTALLER-UDP
UDPX="https://docs.google.com/uc?export=download&confirm=$(wget --quiet --save-cookies /tmp/cookies.txt --keep-session-cookies --no-check-certificate 'https://docs.google.com/uc?export=download&id=1S3IE25v_fyUfCLslnujFBSBMNunDHDk2' -O- | sed -rn 's/.*confirm=([0-9A-Za-z_]+).*/\1\n/p')&id=1S3IE25v_fyUfCLslnujFBSBMNunDHDk2"
ISP=$(curl -s ipinfo.io/org | cut -d " " -f 2-10 )
CITY=$(curl -s ipinfo.io/city )
IPVPS=$(curl -s ipv4.icanhazip.com)
domain=$(cat /etc/xray/domain)
RAM=$(free -m | awk 'NR==2 {print $2}')
USAGERAM=$(free -m | awk 'NR==2 {print $3}')
MEMOFREE=$(printf '%-1s' "$(free -m | awk 'NR==2{printf "%.2f%%", $3*100/$2 }')")
LOADCPU=$(printf '%-0.00001s' "$(top -bn1 | awk '/Cpu/ { cpu = "" 100 - $8 "%" }; END { print cpu }')")
MODEL=$(cat /etc/os-release | grep -w PRETTY_NAME | head -n1 | sed 's/=//g' | sed 's/"//g' | sed 's/PRETTY_NAME//g')
CORE=$(printf '%-1s' "$(grep -c cpu[0-9] /proc/stat)")
DATEVPS=$(date +'%d/%m/%Y')
TIMEZONE=$(printf '%(%H:%M:%S)T')
SERONLINE=$(uptime -p | cut -d " " -f 2-10000)
clear
MYIP=$(curl -sS ipv4.icanhazip.com)
echo ""
#########################
# USERNAME
rm -f /usr/bin/user
username=$(curl -sS https://raw.githubusercontent.com/Ryuchiii/izinkansaya/main/ip | grep $MYIP | awk '{print $2}')
echo "$username" >/usr/bin/user
# validity
rm -f /usr/bin/e
valid=$(curl -sS https://raw.githubusercontent.com/Ryuchiii/izinkansaya/main/ip | grep $MYIP | awk '{print $3}')
echo "$valid" >/usr/bin/e
# DETAIL ORDER
username=$(cat /usr/bin/user)
oid=$(cat /usr/bin/ver)
exp=$(cat /usr/bin/e)
clear
# CERTIFICATE STATUS
d1=$(date -d "$valid" +%s)
d2=$(date -d "$today" +%s)
certifacate=$(((d1 - d2) / 86400))
# VPS Information
DATE=$(date +'%Y-%m-%d')
datediff() {
    d1=$(date -d "$1" +%s)
    d2=$(date -d "$2" +%s)
    echo -e "$COLOR1 $NC Expiry In   : $(( (d1 - d2) / 86400 )) Days"
}
mai="datediff "$Exp" "$DATE""

# Status ExpiRED Active | Geo Project
Info="(${green}Active${NC})"
Error="(${RED}ExpiRED${NC})"
today=`date -d "0 days" +"%Y-%m-%d"`
Exp1=$(curl -sS https://raw.githubusercontent.com/Ryuchiii/izinkansaya/main/ip | grep $MYIP | awk '{print $3}')
if [[ $today < $Exp1 ]]; then
sts="${Info}"
else
sts="${Error}"
fi
echo -e "\e[32mloading...\e[0m"
clear

# OS Uptime
uptime="$(uptime -p | cut -d " " -f 2-10)"
cpu_usage1="$(ps aux | awk 'BEGIN {sum=0} {sum+=$3}; END {print sum}')"
cpu_usage="$((${cpu_usage1/\.*} / ${coREDiilik:-1}))"
cpu_usage+=" %"
WKT=$(curl -s ipinfo.io/timezone )
DAY=$(date +%A)
DATE=$(date +%m/%d/%Y)
DATE2=$(date -R | cut -d " " -f -5)
IPVPS=$(wget -qO- ipinfo.io/ip)
cname=$( awk -F: '/model name/ {name=$2} END {print name}' /proc/cpuinfo )
cores=$( awk -F: '/model name/ {core++} END {print core}' /proc/cpuinfo )
freq=$( awk -F: ' /cpu MHz/ {freq=$2} END {print freq}' /proc/cpuinfo )
tram=$( free -m | awk 'NR==2 {print $2}' )
uram=$( free -m | awk 'NR==2 {print $3}' )
fram=$( free -m | awk 'NR==2 {print $4}' )
clear
ssh_service=$(/etc/init.d/ssh status | grep Active | awk '{print $3}' | cut -d "(" -f2 | cut -d ")" -f1)
dropbear_service=$(/etc/init.d/dropbear status | grep Active | awk '{print $3}' | cut -d "(" -f2 | cut -d ")" -f1)
haproxy_service=$(systemctl status haproxy | grep Active | awk '{print $3}' | cut -d "(" -f2 | cut -d ")" -f1)
xray_service=$(systemctl status xray | grep Active | awk '{print $3}' | cut -d "(" -f2 | cut -d ")" -f1)
nginx_service=$(systemctl status nginx | grep Active | awk '{print $3}' | cut -d "(" -f2 | cut -d ")" -f1)
#Status | Geo Project
clear
# STATUS SERVICE  SSH 
if [[ $ssh_service == "running" ]]; then 
   status_ssh="${green}ON${NC}"
else
   status_ssh="${z}OFF${NC} "
fi

# // SSH Websocket Proxy
ssh_ws=$( systemctl status ws | grep Active | awk '{print $3}' | sed 's/(//g' | sed 's/)//g' )
if [[ $ssh_ws == "running" ]]; then
    status_ws_epro="${green}ON${NC}"
else
    status_ws_epro="${z}OFF${NC} "
fi

# STATUS SERVICE HAPROXY
if [[ $haproxy_service == "running" ]]; then 
   status_haproxy="${green}DONE${NC}"
else
   status_haproxy="${z}OFF${NC} "
fi

# STATUS SERVICE XRAY
if [[ $xray_service == "running" ]]; then 
   status_xray="${green}ON${NC}"
else
   status_xray="${z}OFF${NC} "
fi

# STATUS SERVICE NGINX
if [[ $nginx_service == "running" ]]; then 
   status_nginx="${green}ON${NC}"
else
   status_nginx="${z}OFF${NC} "
fi

# STATUS SERVICE Dropbear
if [[ $dropbear_service == "running" ]]; then 
   status_dropbear="${green}ON${NC}"
else
   status_dropbear="${z}OFF${NC} "
fi
#####INFOAKUN
vlx=$(grep -c -E "^#& " "/etc/xray/config.json")
let vla=$vlx/2
vmc=$(grep -c -E "^### " "/etc/xray/config.json")
let vma=$vmc/2
ssh1="$(awk -F: '$3 >= 1000 && $1 != "nobody" {print $1}' /etc/passwd | wc -l)"
trx=$(grep -c -E "^#! " "/etc/xray/config.json")
let trb=$trx/2
ssx=$(grep -c -E "^#ss# " "/etc/xray/config.json")
let ssa=$ssx/2
###########
KANAN="\033[1;32m<\033[1;33m<\033[1;31m<\033[1;31m$NC"
KIRI="\033[1;32m>\033[1;33m>\033[1;31m>\033[1;31m$NC"
########
kiprok="\033[0m"
piu="\033[0m\033[33m"
r="\033[1;31m"  #REDTERANG
a=" ${z}ACCOUNT PREMIUM" 
echo -e " "
echo -e " \033[97;1m┌─────────────────────────────────────────────────┐${NC}"
echo -e " \033[97;1m│ \e[0m \033[41;1;97;1m                 TEKIRO TUNNELING             $NC \033[97;1m│$NC"
echo -e " \033[97;1m└─────────────────────────────────────────────────┘${NC}"
echo -e " \033[97;1m┌─────────────────────────────────────────────────┐${NC}"
echo -e " \033[97;1m│\033[97;1m OS         : $MODEL${NC}"
echo -e " \033[97;1m│\033[97;1m RAM        : $RAM MB $NC"
echo -e " \033[97;1m│\033[97;1m SWAP       : $uram MB $NC"
echo -e " \033[97;1m│\033[97;1m CITY       : $CITY ${NC}"
echo -e " \033[97;1m│\033[97;1m ISP        : $ISP ${NC}"
echo -e " \033[97;1m│\033[97;1m IP         :$Blue $IPVPS${NC}"
echo -e " \033[97;1m│\033[97;1m DOMAIN     :$Blue $domain${NC}"
echo -e " \033[97;1m│\033[97;1m UPTIME     : $SERONLINE${NC}"
echo -e " \033[97;1m└─────────────────────────────────────────────────┘${NC}"

echo -e " \033[97;1m┌─────────────────────────────────────────────────┐${NC}"
echo -e " \033[97;1m│  ${piu} XRAY : ${kiprok} $status_xray | ${piu} SSH-WS : ${kiprok} $status_ssh | ${piu} NGINX : ${kiprok} $status_nginx    │$NC" 
echo -e " \033[97;1m└─────────────────────────────────────────────────┘${NC}"
echo -e "     \033[97;1m┌─────────────────────────────────────────┐${NC}"
echo -e "     \033[97;1m│\033[97;1m  Version        : v2.0 LTS${NC}"
echo -e "     \033[97;1m│\033[97;1m  Client Name    :$BIRed $username${NC}"
echo -e "     \033[97;1m│\033[97;1m  Expiry In      :$BIRed $certifacate Days${NC}"
echo -e "     \033[97;1m└─────────────────────────────────────────┘${NC}"
echo -e "     \033[97;1m───────────────────────────────────────────${NC}"
echo -e " \033[97;1m┌─────────────────────────────────────────────────┐${NC}"
echo -e "  ${Blue}    1.)\033[97;1m ☞ SSH/OPENVPN $NC      ${Blue} 6.)\033[97;1m ☞ FEATURES ${NC}"
echo -e " \033[97;1m│${Blue}    2.)\033[97;1m ☞ XRAY $NC             ${Blue} 7.)\033[97;1m ☞ CERT  \033[97;1m       │${NC}"
echo -e "  ${Blue}    3.)${NC}\033[97;1m ☞ TROJAN $NC           ${Blue} 8.) \033[97;1m☞ BACKUP ${NC}"
echo -e " \033[97;1m│${Blue}    4.)${NC}\033[97;1m ☞ SS-Libev $NC         ${Blue} 9.) \033[97;1m☞ RESTORE  \033[97;1m   │${NC}"
echo -e "  ${Blue}    5.)${NC}\033[97;1m ☞ REBOOT $NC           ${Blue} x.) \033[97;1m☞ EXIT ${NC}"
echo -e " \033[97;1m└─────────────────────────────────────────────────┘${NC}"
echo -e "     \033[97;1m───────────────────────────────────────────${NC}"
echo
read -p " Select menu : " opt
echo -e ""
case $opt in
1)
clear
m-sshws
;;
2)
clear
m-vmess
;;
3)
clear
m-trojan
;;
4)
clear
m-ssws
;;
5)
clear
reboot
;;
6)
clear
utility
;;
7)
clear
fixcert
;;
8)
clear
backup
;;
9)
clear
restore
;;
10)
clear
encrypt
;;
x)
clear
exit
;;
*)
clear
menu
;;
esac
