# Suricata-Basics

# Objective
The objective of this lab was to set up Suricata, an open-source network threat detection tool, on a firewall, configure it to monitor network traffic, and investigate any malicious activity. Specifically, I aimed to:

Install Suricata on the firewall.

Configure Suricata to listen on the appropriate network interface.

Monitor network traffic for malicious DNS requests originating from a server.

![image](https://github.com/user-attachments/assets/6c531406-9fc8-4346-8a7e-bf9e15634ae1)

# Step 1: SSH into the Firewall

Open a terminal on the desktop.

SSH into the firewall using the following command:

**ssh student@192.168.6.4**

# Step 2: Setting Up Suricata

Install Suricata on the firewall using apt-get:

**sudo nano /etc/suricata/suricata.yaml**

![image](https://github.com/user-attachments/assets/fd550a8a-0d4a-47ee-ab04-ded95770925d)

# Step 4: Testing Suricata:

![image](https://github.com/user-attachments/assets/f6557171-7440-4d59-9a30-6a3a863eb212)

Monitor network traffic logged in /var/log/suricata/eve.json using the following command:

**sudo tail -f /var/log/suricata/eve.json | jq '. | select(.event_type == "dns" and .src_ip == "192.168.10.2")'**

![image](https://github.com/user-attachments/assets/4da8827f-4cef-46f4-899f-1399245572db)


