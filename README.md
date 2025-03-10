🛠️ Setting Up Suricata on macOS 🔥

Suricata is a powerful, high-performance Network Intrusion Detection System (NIDS),
Intrusion Prevention System (IPS), and Network Security Monitoring (NSM) tool. Follow
these steps to set up Suricata on macOS.

  🚀 Installation & Configuration

1️⃣ Install Suricata 📦
  # brew install suricata

2️⃣ Check Network Interface 🌐
  # ifconfig # Find your interface name (e.g., en0, en1)

3️⃣ Open & Edit Configuration File ✍️
  # vim /usr/local/etc/suricata/suricata.yaml

Modify the following sections:
 vars:
 address-groups:
 HOME_NET: "[192.168.1.0/24]" # Replace with your network
 af-packet:
 - interface: en0 # Replace with your interface

4️⃣ Update Rules 🔄
  # suricata-update # Fetch latest rule sets

🎯 Running Suricata
✅ Start Suricata (IDS Mode) 🛡️
   # suricata -c /usr/local/etc/suricata/suricata.yaml -i en0 (replace en0 with your Interface name)

🔄 Run Suricata in Background 👻
   # suricata -c /usr/local/etc/suricata/suricata.yaml -i en0 -D

🧐 Test Suricata (IDS Response)
   #curl http://testmynids.org/uid/index.html

📜 Check Logs (Alerts & Events)
   # cat /usr/local/var/log/suricata/fast.log

📝 Notes
 Run Suricata with sudo if you face permission issues. I faced this error so i try with sudo and it worked for me.
 Use en0 or the correct network interface for your setup.
 Modify HOME_NET to match your internal network for accurate monitoring.
 Logs provide useful insights; check fast.log regularly for alerts.

✅ Enjoy monitoring your network with Suricata! 🚀
