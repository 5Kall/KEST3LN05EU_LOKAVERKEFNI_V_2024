# KEST3LN05EU_LOKAVERKEFNI_V_2024
Myndir og comment fyrir KEST3LN05EU Lokaverkefni

<br>
1. Install and configure the server1, client1 and client2 with hostnames and domain as ddp.is
<br>

![image](https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/a368021f-4314-4180-a625-7bf87c93eabc)


Gerðum 2 network adapters fyrir server, client1 og client2
Network adapter1 stilltur á custom og VMnet8 og adapter2 stilltur á VMnet1
![image](https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/a6c5c729-b7e9-409d-a22c-4ce6a9e36849)


til að breyta hostname og domain name notum við

![image](https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/e5d81d52-a457-441a-909a-304a3ec78478)



<br>
2. configure server1 with static IP Address, from the IP Address block 192.168.100.0/24. The
server must be configured with the 10th usable IP Address.
<br>
opnað var "/etc/dhcp.conf" til þess að breyta stillingar þannig að server1 gefur frá sér static ip tölu (sjá mynd fyrir virkni og uppsetninu)

<img width="861" alt="server-ip-a" src="https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/1e127d3b-1cb0-41f0-a9f9-06b4b4e050a7">

stillingar í "/etc/netplan/01-network-manager-all.yaml" til þess að stilla static ip tölu við server
<img width="433" alt="Server-network" src="https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/c35a875b-9e41-4eb7-ab9c-86e375d62352">




<br>
3. Install and configure DHCP on server1, so both clients get an IP Addresses, Gateway, DNS
IP address and domain name automatically via HDCP.
<br>

Hlöðuðum og stilltum DHCP (sjá mynd fyrir virkni og uppsetninu)

<img width="860" alt="Server-dhcp" src="https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/5a31cf3a-d832-4eb9-864a-80a3de9dac2b">

<br>
4. Install and configure DNS server on server1, so Hostnames are resolved to IP Addresses.
<br>
Hlöðuðum og stilltum DNS á server nr 1. (sjá mynd fyrir virkni og uppsetninu)
![image](https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/10ad25fb-c7ed-4ed1-b487-749408ad3386)


<br>
5. Create the users accounts using a script, see the Users file.
<br>

<img width="424" alt="user-add" src="https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/d453f494-66ee-4ebb-a643-a642ed9737ff">

<br>
6. Install and configure MySQL on server1 and create Human Resource database. The
database stores information about employees, employees are identified by their Kennitala,
Firstname, Lastname, Email, phone Number, hire date and salary. Employees work in
Departments where each department has one manager, departments are identified by
department ID, department name. Each department is in a different location. Locations are
identified by their location ID, city, Address, and zip code. One or more employees work on
different jobs, and the jobs are identified by Job ID, job title, Min salary and max salary.
<br>

<img width="322" alt="sql-code" src="https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/ee9b6243-6125-4ff2-842a-4631993e0b26">
<img width="416" alt="sql-code2" src="https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/c944dd41-f4ce-4320-a164-70ab546d3c57">
<img width="418" alt="sql-running" src="https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/84120af6-29bd-4192-bf10-7280ad164a27">

<br>
7. Due to data loss the company policy requires taking backups weekly, as system engineer
you are required to schedule backups of home directories to run weekly at midnight each
Friday.
<br>

<br>
8. Install and configure NTP on the server and clients, server1 must be master server to
synchronize the time of the clients.
<br>

<img width="532" alt="ntp-client1" src="https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/fc8a4aa8-bd59-4ab2-a32b-c0f00110c979">
<img width="860" alt="ntp-client1-showcase" src="https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/39f49dda-445e-4973-bd2a-f33caa65c0d1">
<img width="421" alt="ntp-client-centos" src="https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/814379e5-b6e9-4196-b720-83c8c4bd5ce4">
<img width="428" alt="ntp-client-centos-2" src="https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/3e13b369-ce53-457a-9ee0-40dfddb90401">
<img width="517" alt="ntp-running-client2" src="https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/ec1d49be-443d-42d9-86ce-6c00ccec2d4c">
<img width="860" alt="ntp-server1" src="https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/d3b26a19-75f8-4d29-9c29-fd8cdcde5d91">


<br>
9. Install and configure syslog server on server1, server1 should get logs from both the clients
for proactive management and monitoring.
<br>

<img width="860" alt="syslog-server1-running" src="https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/7570b59d-5638-44a6-bfb6-eedab37bbf72">


<br>
10. Install and configure Postfix on server1, so users can send and receive emails using Round
Cube open-source software.
<br>

<br>
11. Install and configure shared printers for each group, only users that belong to the group
should print only, accept IT and Management groups should print and manage the printers.
<br>

<br>
12. For security reasons, install and configure SSH on the server and clients, SSH login should
use RSA keys instead of the password authentication.
<br>

<img width="381" alt="ssh-client-config" src="https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/aa0a88fd-ed52-4d22-977d-4bab62b3d633">
<img width="860" alt="ssh-client-connection-config-status" src="https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/ccf1ace9-d458-48aa-a523-269c6da8975d">
<img width="862" alt="ssh-server-config-status-connection" src="https://github.com/5Kall/KEST3LN05EU_LOKAVERKEFNI_V_2024/assets/89195445/06033732-a2cd-4b99-8a9c-60a3671257b7">


<br>
13. All unused ports should be closed, use NMAP for testing.
<br>
