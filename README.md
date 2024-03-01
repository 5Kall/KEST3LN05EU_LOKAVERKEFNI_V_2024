# Lab Instructions

1. **Install and configure the server1, client1 and client2 with hostnames and domain as ddp.is**

   *Installation and Configuration:*
   - Install the operating system on each machine (server1, client1, and client2).
   - Set the hostname of each machine to `server1`, `client1`, and `client2` respectively.
   - Edit the `/etc/hosts` file on each machine to map `ddp.is` to the IP addresses of the machines.

   ![Server and client setup](image-archive\1. Install and configure the server1, client1 and client2 with hostnames and domain as ddp.is\client2-domain.png)
   ![Server and client setup](image-archive\1. Install and configure the server1, client1 and client2 with hostnames and domain as ddp.is\hosname-domin-client1.png)
   ![Server and client setup](image-archive\1. Install and configure the server1, client1 and client2 with hostnames and domain as ddp.is\hostname-client2.png)
   ![Server and client setup](image-archive\1. Install and configure the server1, client1 and client2 with hostnames and domain as ddp.is\Screenshot 2024-02-20 090252.png)
   ![Server and client setup](image-archive\1. Install and configure the server1, client1 and client2 with hostnames and domain as ddp.is\Server-domain-hostname.png)

2. **Configure server1 with static IP Address, from the IP Address block 192.168.100.0/24. The server must be configured with the 10th usable IP Address.**

   *Configuration Steps:*
   - Edit the network configuration file (`/etc/network/interfaces` or `/etc/sysconfig/network-scripts/ifcfg-eth0` depending on the Linux distribution) on server1.
   - Set the IP address to the 10th usable IP address from the block 192.168.100.0/24.
   - Restart the networking service or reboot the server for the changes to take effect.

   ![Static IP configuration](static_ip_config.png)

3. **Install and configure DHCP on server1, so both clients get an IP Addresses, Gateway, DNS IP address and domain name automatically via DHCP.**

   *Installation and Configuration:*
   - Install the DHCP server package (`dhcpd` on most Linux distributions).
   - Configure the DHCP server to allocate IP addresses, gateway, DNS IP address, and domain name.
   - Start the DHCP server service and ensure it starts automatically on system boot.

   ![DHCP configuration](dhcp_config.png)

4. **Install and configure DNS server on server1, so Hostnames are resolved to IP Addresses.**

   *Configuration Steps:*
   - Install a DNS server package (such as `bind9` on most Linux distributions).
   - Configure the DNS server to resolve hostnames to IP addresses.
   - Update the DNS records to include the hostnames and IP addresses of server1, client1, and client2.

   ![DNS configuration](dns_config.png)

5. **Create the users accounts using a script, see the Users file.**

   *User Account Creation Script:*
   - Utilize a script (e.g., Bash, Python) to automate the creation of user accounts.
   - Read the user details from a Users file and use the script to create user accounts accordingly.

   ![User account creation](user_creation.png)

6. **Install and configure MySQL on server1 and create Human Resource database.**

   *Installation and Configuration:*
   - Install MySQL server package (`mysql-server` on most Linux distributions).
   - Configure MySQL server to listen on the appropriate IP address.
   - Create a Human Resource database and define tables for employees, departments, locations, and jobs.

   ![MySQL installation](mysql_installation.png)

7. **Due to data loss the company policy requires taking backups weekly, as system engineer you are required to schedule backups of home directories to run weekly at midnight each Friday.**

   *Backup Scheduling:*
   - Set up a cron job to schedule backups of home directories.
   - Configure the cron job to run a backup script weekly at midnight each Friday.

   ![Backup scheduling](backup_scheduling.png)

8. **Install and configure NTP on the server and clients, server1 must be master server to synchronize the time of the clients.**

   *Installation and Configuration:*
   - Install the NTP server package (`ntp` or `chrony` on most Linux distributions) on server1.
   - Configure server1 as the master NTP server.
   - Install the NTP client package on client machines and configure them to synchronize time with server1.

   ![NTP configuration](ntp_config.png)

9. **Install and configure syslog server on server1, server1 should get logs from both the clients for proactive management and monitoring.**

   *Installation and Configuration:*
   - Install the syslog server package (`rsyslog` on most Linux distributions) on server1.
   - Configure the syslog server to receive logs from client machines.
   - Update syslog configuration files to specify log sources and destinations.

   ![Syslog server configuration](syslog_config.png)

10. **Install and configure Postfix on server1, so users can send and receive emails using Round Cube open-source software.**

    *Installation and Configuration:*
    - Install the Postfix mail server package on server1.
    - Configure Postfix to handle incoming and outgoing emails.
    - Integrate Postfix with Roundcube for webmail access.

    ![Postfix configuration](postfix_config.png)

11. **Install and configure shared printers for each group, only users that belong to the group should print only, except IT and Management groups should print and manage the printers.**

    *Installation and Configuration:*
    - Install printer driver packages for the shared printers.
    - Configure printer sharing and access control based on user groups.
    - Grant printing and printer management permissions to IT and Management groups.

    ![Printer configuration](printer_config.png)

12. **For security reasons, install and configure SSH on the server and clients, SSH login should use RSA keys instead of the password authentication.**

    *Installation and Configuration:*
    - Install the SSH server package (`openssh-server` on most Linux distributions) on server1 and clients.
    - Generate RSA key pairs for server1 and each client.
    - Configure SSH server to only allow RSA key-based authentication and disable password authentication.

    ![SSH configuration](ssh_config.png)

13. **All unused ports should be closed, use NMAP for testing.**

    *Port Testing with NMAP:*
    - Use the NMAP tool to scan for open ports on server1 and client machines.
    - Identify any open ports that are not required for system functionality.
    - Close unnecessary ports using firewall configuration or service disabling.

    ![Port testing with NMAP](nmap_testing.png)
