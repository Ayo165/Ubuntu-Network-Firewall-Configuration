# Ubuntu Network Firewall Configuration

## 📝 Objective
This project demonstrates the setup and configuration of a network firewall on an Ubuntu system utilizing UFW (Uncomplicated Firewall)[cite: 3]. The primary goal was to manage access controls and protect the network infrastructure from unauthorized threats by explicitly defining allowed and denied traffic[cite: 3].

## 🛠️ Tools & Technologies Used
*   **Operating System:** Ubuntu Linux[cite: 3]
*   **Firewall Tool:** UFW (Uncomplicated Firewall)[cite: 3]
*   **Network Scanning:** Nmap (for rule validation)[cite: 3]

## 🗺️ Configuration & Deployment Steps

### 1. Initial Setup and Default Policies
The Ubuntu system was first updated and upgraded, followed by the installation and activation of UFW[cite: 3]. To establish a strong baseline security posture, the default firewall policies were configured to deny all incoming traffic and allow all outgoing traffic[cite: 3]. 

### 2. Implementing Access Control Rules
Specific rules were implemented to ensure necessary services remained available while blocking unauthorized access:
*   **Administrative Access:** Explicitly allowed SSH (port 22) connections to prevent locking administrators out of the system[cite: 3].
*   **Web Services:** Allowed standard web traffic by opening HTTP (port 80) and HTTPS (port 443)[cite: 3].
*   **IP & Subnet Whitelisting:** Allowed connections from specific trusted internal subnets (e.g., `192.168.1.0/24`)[cite: 3].
*   **Targeted Denials:** Explicitly blocked traffic on highly vulnerable ports, such as port 23 (Telnet), and denied connections from specific untrusted IP addresses[cite: 3].

### 3. Advanced Configuration & Logging
To maintain visibility over network activity, UFW logging was enabled to monitor allowed and blocked connections[cite: 3]. Application profiles were also reviewed to quickly allow full application suites (like `Nginx Full`) when necessary[cite: 3].

## 🔍 Testing & Validation
After the rules were applied, the firewall's effectiveness was tested using Nmap from an external machine[cite: 3]. The aggressive scan (`nmap -v -A`) confirmed that only the explicitly allowed ports were open to the network, and the denied services and IPs were successfully blocked[cite: 3].

## 💡 Conclusion
By configuring UFW, the Ubuntu system was successfully hardened against unauthorized network access[cite: 3]. Documenting and validating these rules ensures a strong defensive layer that can be easily updated and monitored as the organization's network requirements change[cite: 3].
