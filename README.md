# Lab Instructions

1. **Install and configure the server1, client1 and client2 with hostnames and domain as ddp.is**

   *Installation and Configuration:*
   - Install the operating system on each machine (server1, client1, and client2).
   - Set the hostname of each machine to `server1`, `client1`, and `client2` respectively.
   - Edit the `/etc/hosts` file on each machine to map `ddp.is` to the IP addresses of the machines.

   <img src="image-archive/1. Install and configure the server1, client1 and client2 with hostnames and domain as ddp.is/client2-domain.png" alt="Client 2 Domain" style="max-width: 400px;">

   <img src="image-archive\1. Install and configure the server1, client1 and client2 with hostnames and domain as ddp.is\hosname-domin-client1.png" alt="Client 1 Hostname" style="max-width: 400px;">

   <img src="image-archive/1. Install and configure the server1, client1 and client2 with hostnames and domain as ddp.is/hostname-client2.png" alt="Client 2 Hostname" style="max-width: 400px;">

   <img src="image-archive/1. Install and configure the server1, client1 and client2 with hostnames and domain as ddp.is/Screenshot 2024-02-20 090252.png" alt="Screenshot" style="max-width: 400px;">

   <img src="image-archive/1. Install and configure the server1, client1 and client2 with hostnames and domain as ddp.is/Server-domain-hostname.png" alt="Server Domain Hostname" style="max-width: 400px;">

2. **Configure server1 with static IP Address, from the IP Address block 192.168.100.0/24. The server must be configured with the 10th usable IP Address.**

   *Configuration Steps:*
   - Edit the network configuration file (`/etc/network/interfaces` or `/etc/sysconfig/network-scripts/ifcfg-eth0` depending on the Linux distribution) on server1.
   - Set the IP address to the 10th usable IP address from the block 192.168.100.0/24.
   - Restart the networking service or reboot the server for the changes to take effect.

    <img src="image-archive\2. configure server1 with static IP Address\server-ip-a.png" alt="server ip address" style="max-width: 400px;">
    <img src="image-archive\2. configure server1 with static IP Address\Server-network.png" alt="server network settings" style="max-width: 400px;">

3. **Install and configure DHCP on server1, so both clients get an IP Addresses, Gateway, DNS IP address and domain name automatically via DHCP.**

   *Installation and Configuration:*
   - Install the DHCP server package (`dhcpd` on most Linux distributions).
   - Configure the DHCP server to allocate IP addresses, gateway, DNS IP address, and domain name.
   - Start the DHCP server service and ensure it starts automatically on system boot.

   <img src="image-archive\3. Install and configure DHCP on server1\Server-dhcp.png" alt="dchp server">

4. **Install and configure DNS server on server1, so Hostnames are resolved to IP Addresses.**

   *Configuration Steps:*
   - Install a DNS server package (such as `bind9` on most Linux distributions).
   - Configure the DNS server to resolve hostnames to IP addresses.
   - Update the DNS records to include the hostnames and IP addresses of server1, client1, and client2.

    <img src="image-archive\4. Install and configure DNS server on server1\dns-conf.png" alt="dns configure file" style="max-width: 400px;">
    <img src="image-archive\4. Install and configure DNS server on server1\dns.png" alt="bind9 server configure" style="max-width: 400px;">

5. **Create the users accounts using a script, see the Users file.**

   *User Account Creation Script:*
   - Utilize a script (e.g., Bash, Python) to automate the creation of user accounts.
   - Read the user details from a Users file and use the script to create user accounts accordingly.

   <img src="image-archive\5. Create the users accounts using a script\user-add.png" alt="bash script to add users" style="max-width: 400px;">
    <img src="image-archive\5. Create the users accounts using a script\users.png" alt="display created users" style="max-width: 400px;"> 


6. **Install and configure MySQL on server1 and create Human Resource database.**

   *Installation and Configuration:*
   - Install MySQL server package (`mysql-server` on most Linux distributions).
   - Configure MySQL server to listen on the appropriate IP address.
   - Create a Human Resource database and define tables for employees, departments, locations, and jobs.

   <img src="image-archive\6. Install and configure MySQL on server1 and create Human Resource database\sql-code.png" alt="sql code part one" style="max-width: 400px;">
   <img src="image-archive\6. Install and configure MySQL on server1 and create Human Resource database\sql-code2.png" alt="sql code part two" style="max-width: 400px;">
   <img src="image-archive\6. Install and configure MySQL on server1 and create Human Resource database\sql-running.png" alt="sql running" style="max-width: 400px;">

7. **Due to data loss the company policy requires taking backups weekly, as system engineer you are required to schedule backups of home directories to run weekly at midnight each Friday.**

   *Backup Scheduling:*
   - Set up a cron job to schedule backups of home directories.
   - Configure the cron job to run a backup script weekly at midnight each Friday.

   <img src="image-archive\7. Due to data loss the company policy requires taking backups weekly\backup.png" alt="backup code" style="max-width: 400px;">

8. **Install and configure NTP on the server and clients, server1 must be master server to synchronize the time of the clients.**

   *Installation and Configuration:*
   - Install the NTP server package (`ntp` or `chrony` on most Linux distributions) on server1.
   - Configure server1 as the master NTP server.
   - Install the NTP client package on client machines and configure them to synchronize time with server1.

   <img src="image-archive\8. Install and configure NTP on the server and clients\ntp-client-centos-2.png" alt="cent os client image 2" style="max-width: 400px;">
   <img src="image-archive\8. Install and configure NTP on the server and clients\ntp-client-centos.png" alt="cent os client image 1" style="max-width: 400px;">
   <img src="image-archive\8. Install and configure NTP on the server and clients\ntp-client1-showcase.png" alt="client 1 showcase" style="max-width: 400px;">
   <img src="image-archive\8. Install and configure NTP on the server and clients\ntp-client1.png" alt="ntp client1 configure" style="max-width: 400px;">
   <img src="image-archive\8. Install and configure NTP on the server and clients\ntp-running-client2.png" alt="ntp running on client 2" style="max-width: 400px;">
   <img src="image-archive\8. Install and configure NTP on the server and clients\ntp-server1.png" alt="ntp running on server1" style="max-width: 400px;">

9. **Install and configure syslog server on server1, server1 should get logs from both the clients for proactive management and monitoring.**

   *Installation and Configuration:*
   - Install the syslog server package (`rsyslog` on most Linux distributions) on server1.
   - Configure the syslog server to receive logs from client machines.
   - Update syslog configuration files to specify log sources and destinations.

   <img src="image-archive\9. Install and configure syslog server on server1\rsyslog_client2 .png" alt="ryslog client2" style="max-width: 400px;">
   <img src="image-archive\9. Install and configure syslog server on server1\syslog-client1.png" alt="syslog client1 " style="max-width: 400px;">
   <img src="image-archive\9. Install and configure syslog server on server1\syslog-configuration-file.png" alt="syslog configureation file" style="max-width: 400px;">
   <img src="image-archive\9. Install and configure syslog server on server1\syslog-server1-running.png" alt="syslog running on server1" style="max-width: 400px;">

10. **Install and configure Postfix on server1, so users can send and receive emails using Round Cube open-source software.**

    *Installation and Configuration:*
    - Install the Postfix mail server package on server1.
    - Configure Postfix to handle incoming and outgoing emails.
    - Integrate Postfix with Roundcube for webmail access.

    <img src="image-archive\10. Install and configure Postfix on server1\postfix.png" alt="postfix runnning" style="max-width: 400px;">

11. **Install and configure shared printers for each group, only users that belong to the group should print only, except IT and Management groups should print and manage the printers.**

    *Installation and Configuration:*
    - Install printer driver packages for the shared printers.
    - Configure printer sharing and access control based on user groups.
    - Grant printing and printer management permissions to IT and Management groups.

    <img src="image-archive\11. Install and configure shared printers for each group\cups-account.png" alt="cups accounts" style="max-width: 400px;">
    <img src="image-archive\11. Install and configure shared printers for each group\cups-working-online-interface.png" alt="cups working online interface" style="max-width: 400px;">
    <img src="image-archive\11. Install and configure shared printers for each group\cups-working-online-interface2.png" alt="cups working online interface 2" style="max-width: 400px;">

12. **For security reasons, install and configure SSH on the server and clients, SSH login should use RSA keys instead of the password authentication.**

    *Installation and Configuration:*
    - Install the SSH server package (`openssh-server` on most Linux distributions) on server1 and clients.
    - Generate RSA key pairs for server1 and each client.
    - Configure SSH server to only allow RSA key-based authentication and disable password authentication.

    <img src="image-archive\12. For security reasons, install and configure SSH on the server and clients\ssh-client-config.png" alt="ssh client config" style="max-width: 400px;">
    <img src="image-archive\12. For security reasons, install and configure SSH on the server and clients\ssh-client-connection-config-status.png" alt=" ssh client connection config status" style="max-width: 400px;">
    <img src="image-archive\12. For security reasons, install and configure SSH on the server and clients\ssh-server-config-status-connection.png" alt="ssh server config status" style="max-width: 400px;">

13. **All unused ports should be closed, use NMAP for testing.**

    *Port Testing with NMAP:*
    - Use the NMAP tool to scan for open ports on server1 and client machines.
    - Identify any open ports that are not required for system functionality.
    - Close unnecessary ports using firewall configuration or service disabling.

    <img src="image-archive\13. All unused ports should be closed, use NMAP for testing\nmap-test.png" alt=" testing nmap on server1" style="max-width: 400px;">
