# 📡 Wi-Fi Network Scanner

A simple Python tool to scan nearby Wi-Fi networks using built-in system commands. This project helps you learn how devices detect and list available wireless networks.

---

## 🛠 Features

- Detects nearby Wi-Fi networks
- Shows SSID, Signal Strength, Security Type, and more
- Works on both **Windows** and **Linux**
- No third-party libraries needed

---
### Run the script:
    -python scanner.py
### Python code
```
import subprocess
import platform

def scan_wifi_windows():
    try:
        output = subprocess.check_output("netsh wlan show networks mode=bssid", shell=True, encoding='utf-8')
        print("=== Available Wi-Fi Networks ===")
        print(output)
    except Exception as e:
        print("Error scanning Wi-Fi networks:", e)

def scan_wifi_linux():
    try:
        output = subprocess.check_output("nmcli dev wifi", shell=True, encoding='utf-8')
        print("=== Available Wi-Fi Networks ===")
        print(output)
    except Exception as e:
        print("Error scanning Wi-Fi networks:", e)

def main():
    print("🔍 Scanning for Wi-Fi Networks...")
    os_type = platform.system()

    if os_type == "Windows":
        scan_wifi_windows()
    elif os_type == "Linux":
        scan_wifi_linux()
    else:
        print("This script currently supports only Windows and Linux.")

if __name__ == "__main__":
    main()
```
### Output Example (Windows)
```
SSID 1 : MyHomeWiFi
    Network type            : Infrastructure
    Authentication          : WPA2-Personal
    Signal                  : 95%
    BSSID 1                 : xx:xx:xx:xx:xx:xx
    Channel                 : 6
```
### OUTPUT

![Screenshot 2025-07-10 120249](https://github.com/user-attachments/assets/dd9d88e7-c35a-42fe-bb16-d3131f9c3a68)


    
