# Ubuntu Network Firewall Configuration

## 📝 Objective
This project demonstrates the setup and configuration of a network firewall on an Ubuntu system utilizing UFW (Uncomplicated Firewall). The primary goal was to manage access controls and protect the network infrastructure from unauthorized threats by explicitly defining allowed and denied traffic.

## 🛠️ Tools & Technologies Used
*   **Operating System:** Ubuntu Linux
*   **Firewall Tool:** UFW (Uncomplicated Firewall)
*   **Network Scanning:** Nmap (for rule validation)

## 🗺️ Configuration & Deployment Steps

### 1. Initial Setup and Default Policies
The Ubuntu system was first updated and upgraded, followed by the installation and activation of UFW. To establish a strong baseline security posture, the default firewall policies were configured to deny all incoming traffic and allow all outgoing traffic. 

### 2. Implementing Access Control Rules
Specific rules were implemented to ensure necessary services remained available while blocking unauthorized access:
*   **Administrative Access:** Explicitly allowed SSH (port 22) connections to prevent locking administrators out of the system.
*   **Web Services:** Allowed standard web traffic by opening HTTP (port 80) and HTTPS (port 443).
*   **IP & Subnet Whitelisting:** Allowed connections from specific trusted internal subnets (e.g., `192.168.1.0/24`).
*   **Targeted Denials:** Explicitly blocked traffic on highly vulnerable ports, such as port 23 (Telnet), and denied connections from specific untrusted IP addresses.

### 3. Advanced Configuration & Logging
To maintain visibility over network activity, UFW logging was enabled to monitor allowed and blocked connections. Application profiles were also reviewed to quickly allow full application suites (like `Nginx Full`) when necessary.

## 🔍 Testing & Validation
After the rules were applied, the firewall's effectiveness was tested using Nmap from an external machine. The aggressive scan (`nmap -v -A`) confirmed that only the explicitly allowed ports were open to the network, and the denied services and IPs were successfully blocked.

## 💡 Conclusion
By configuring UFW, the Ubuntu system was successfully hardened against unauthorized network access. Documenting and validating these rules ensures a strong defensive layer that can be easily updated and monitored as the organization's network requirements change.
