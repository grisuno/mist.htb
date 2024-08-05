# ghost.htb
ghost.htb insane windows machine, Writeup complete, coming soon ;) 

hackTheBox: https://app.hackthebox.com/teams/overview/6429

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Shell Script](https://img.shields.io/badge/shell_script-%23121011.svg?style=for-the-badge&logo=gnu-bash&logoColor=white) ![Flask](https://img.shields.io/badge/flask-%23000.svg?style=for-the-badge&logo=flask&logoColor=white) ![image](https://github.com/user-attachments/assets/1b5049b8-3aad-40d1-89eb-642941ff13a1)
 [![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/Y8Y2Z73AV)

![image](https://github.com/user-attachments/assets/8105f19e-7595-4c76-a930-bef1f4e95d74)

![image](https://github.com/user-attachments/assets/4d020369-22cf-4783-856b-6abd4c6ee793)

clone the repo:
```bash
git clone https://github.com/grisuno/LazyOwn.git
cd LazyOwn
chmod +x install.sh
./install.sh
./lazyown
```

open the payload.json and edit the ip addres from the htb machine

![image](https://github.com/user-attachments/assets/d42ba06f-a8bd-4dd8-addb-eb7303b59d3d)

and then you:

![image](https://github.com/user-attachments/assets/b79cf40f-40f1-483b-a789-50ea00c72dba)

```bash
LazyOwn> payload
[*] Parameters loaded from payload.json
LazyOwn> run lazynmap
```
after the scann you can see the reports:

![image](https://github.com/user-attachments/assets/56b7bebb-c474-440e-b1bc-d96aaf0a854f)

it's windows machine by the ports open

and you can see the reports in detail.

![image](https://github.com/user-attachments/assets/db15f44c-70d8-4742-9cd2-cfa2a6be0b03)

nmap confirm it is a windows machine

and yoy can add the domain to the hosts file like this

![image](https://github.com/user-attachments/assets/ad3065ab-0717-4c4d-b372-60908c370b45)

```bash
addhosts ghost.htb
```
some recon

![image](https://github.com/user-attachments/assets/67fe5bdc-c9ac-43b3-b1a7-6f4d8ceff52f)

rpcclient command:

![image](https://github.com/user-attachments/assets/eb6a90d6-dba3-4b79-ae36-0a6c1852f52f)

more recon:

![image](https://github.com/user-attachments/assets/093df497-eff2-4c3d-9aa7-b77e51cccb6f)

some interesting from cme alias command from CrackMapExec and we habe the build :)

![image](https://github.com/user-attachments/assets/fb1a467a-d529-4935-b6b9-70b9016a412f)
![image](https://github.com/user-attachments/assets/a8576bdc-8805-4e56-97e3-3fe3f87fbb00)

new dommain found and it's is the domain controller :) now we can add to the /etc/hosts

![image](https://github.com/user-attachments/assets/7caf7045-690f-4a24-906d-3145d2234741)

now ours etc hosts looks like this:

![image](https://github.com/user-attachments/assets/d06267da-a374-4fe2-9d17-b6d161c6c211)

and rpcdump what say to us:

![image](https://github.com/user-attachments/assets/57a0d0a3-501e-4c74-96c8-ef3354505dd7)

some digging

![image](https://github.com/user-attachments/assets/8ad368c0-4b80-4060-81be-43e500ca7528)

![image](https://github.com/user-attachments/assets/84c0d8a7-d708-4b95-a98d-030486e06eac)

adding the new subdomain :) to hosts in etc directory :)

![image](https://github.com/user-attachments/assets/9bc3ca6e-41f2-49b9-847c-d1cbdf2fc382)

digging more deeper :P

![image](https://github.com/user-attachments/assets/035df31c-5016-451d-a7e1-24d834619133)
![image](https://github.com/user-attachments/assets/37d897d0-6fac-41ee-8c31-3968fe4db306)

gospider :)

![gospider](https://github.com/user-attachments/assets/94db9c5b-1417-4fb8-b004-47a780edc02e)

i save the request in sessions/request.txt and with command proxy or burpsuit and foxyproxy :)

![sqlmap](https://github.com/user-attachments/assets/4e92d292-9f2f-4648-89a1-a7efb5dc21aa)

![login1](https://github.com/user-attachments/assets/e464d73b-bcf0-49a0-98cc-7aa262b286bf)


login one finded with gospider :) 

![login2](https://github.com/user-attachments/assets/98c3db9b-ea50-4884-b1f5-c4b9e862ca89)


Second login :)
and its time to nikto

![nikto](https://github.com/user-attachments/assets/560bb724-f98a-4fc8-945d-a34439d55d3c)

:O

![searchsploit](https://github.com/user-attachments/assets/3b4c68dc-b7ac-42c6-8dc3-225f4a2d3189)

searchsploit or ss in LazyOwn :)

![second exploit ss](https://github.com/user-attachments/assets/0e76cbee-cc89-41d1-bb88-fe726346bf97)

another one :P
it's show time :)

the exploits dont work for me :S
try some lateral movement openssl s_client :)

![openssl](https://github.com/user-attachments/assets/e15355a6-2afb-4c30-9c06-ea6a10f78185)

hint to the next step is: 
inject ldap to some login ;)

![image](https://github.com/user-attachments/assets/f27fc7b3-a4b9-4f1b-9d0d-f46b1c75c735)

more info comming soon :)


![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Shell Script](https://img.shields.io/badge/shell_script-%23121011.svg?style=for-the-badge&logo=gnu-bash&logoColor=white) ![Flask](https://img.shields.io/badge/flask-%23000.svg?style=for-the-badge&logo=flask&logoColor=white) ![image](https://github.com/user-attachments/assets/1b5049b8-3aad-40d1-89eb-642941ff13a1)
 [![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/Y8Y2Z73AV)




