# NBFC-Acer-Nitro-AN517-54

This repository contains the **NBFC (Notebook Fan Control)** configuration for the **Acer Nitro AN517-54** running on Linux.

## 📌 Purpose
- Enable manual and automatic fan control for the **Acer Nitro AN517-54**.
- Provide a community-driven configuration file for better fan speed management.
- Reduce overheating issues by fine-tuning the fan speed.

## 🚀 Installation & Usage

### 1️⃣ Install NBFC for Linux  
Ensure you have **nbfc-linux** installed. If not, install it using:  

```sh
yay -S nbfc-linux
```

Or, manually clone and install:  

```sh
git clone https://github.com/nbfc-linux/nbfc-linux.git
cd nbfc-linux
make && sudo make install
```

### 2️⃣ Add the Configuration File  
Copy the **`Acer Nitro AN517-54.json`** file to the NBFC configurations directory:  

```sh
sudo cp "Acer Nitro AN517-54.json" /usr/share/nbfc/configs/
```

### 3️⃣ Apply the Configuration  
Set the profile for your laptop:  

```sh
sudo nbfc config -s "Acer Nitro AN517-54"
```

Then, start the NBFC service:  

```sh
sudo systemctl enable --now nbfc.service
```

### 4️⃣ Adjust Fan Speed  
You can manually set the fan speed percentage:  

```sh
sudo nbfc set -s 100   # 100% fan speed
sudo nbfc set -s 50    # 50% fan speed
sudo nbfc set -s 0     # Turn off fans (not recommended)
```

To check the current status:  

```sh
sudo nbfc status
```

## 🛠 Troubleshooting  
- If the service doesn’t start, check logs with:  

```sh
sudo journalctl -u nbfc.service --no-pager | tail -n 50
```

- If fans do not respond, ensure `thermald` or `tlp` are not conflicting with NBFC. You may need to disable them:  

```sh
sudo systemctl stop thermald
sudo systemctl stop tlp
```

## 🤝 Contribute  
If you test this configuration and find improvements, feel free to submit a **Pull Request** or create an **Issue**.
