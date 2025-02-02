# NBFC Configuration for Acer Nitro AN517-54  
📢 **Looking for contributors!** Help us fine-tune the fan control for this laptop model.

## ❓ Why this repo?  
The **Acer Nitro AN517-54** is not officially supported by NBFC. Many users struggle with overheating issues because fan speeds do not adjust properly on Linux.  

This repository is an attempt to create a working **NBFC (Notebook Fan Control) configuration** for this model, with the help of the community.

## 🔍 Current Issues  
- No official NBFC config for this model.
- Some configurations from similar models (**AN515-51, AN515-57, AN515-58, Predator G3-572**) work partially but have inconsistencies.
- Fan speeds do not ramp up properly under load.
- Manually setting fan speed sometimes fails or behaves erratically.

## 🚀 Installation & Testing  

### 1️⃣ Install NBFC for Linux  
```sh
yay -S nbfc-linux
```
Or manually:  
```sh
git clone https://github.com/nbfc-linux/nbfc-linux.git
cd nbfc-linux
make && sudo make install
```

### 2️⃣ Copy the Config File  
```sh
sudo cp "configs/Acer Nitro AN517-54.json" /usr/share/nbfc/configs/
```

### 3️⃣ Select and Start NBFC  
```sh
sudo nbfc config -s "Acer Nitro AN517-54"
sudo systemctl enable --now nbfc.service
```

### 4️⃣ Manually Set Fan Speed  
```sh
sudo nbfc set -s 100   # 100% fan speed
sudo nbfc status       # Check current speed
```

---

## 🔧 **How You Can Help**
We need **your help** to refine the fan configuration! If you own an **Acer Nitro AN517-54**, you can:  
✅ **Test different configs** from similar models (AN515-57, Predator G3-572, etc.).  
✅ **Edit `Acer Nitro AN517-54.json`** to improve fan behavior.  
✅ **Share your logs & experiences** in the Issues tab.  

---

## 📜 Current Configurations
| Model Tested         | Works? | Issues |
|----------------------|--------|--------|
| AN515-57            | ❌ No  | Fans speed up/down erratically |
| AN515-51            | ✅ Yes | Runs stable, but speed caps too low |
| Predator G3-572     | ⚠️ Partial | Might work, needs testing |
| Custom (current)    | ❌ No  | Service doesn’t start properly |

📌 **Latest attempt:** See [`configs/Acer Nitro AN517-54.json`](configs/Acer%20Nitro%20AN517-54.json)  

---

## 📬 Get Involved  
💬 **Have a better config?** Open a **Pull Request**.  
🐞 **Found issues?** Report it in **Issues**.  
🛠️ **Want to tweak settings?** Fork this repo and experiment!

---

🔥 **Let's fix this together and keep our Nitro cool!**  

---

### 🌎 Next Steps:  
1️⃣ **Create a new repository on GitHub** (e.g., `NBFC-Acer-Nitro-AN517-54`).  
2️⃣ **Upload your current configuration file (`Acer Nitro AN517-54.json`)** even if it’s not working.  
3️⃣ **Add the README** (use the markdown above).  
4️⃣ **Share your repo link on forums, Reddit, and GitHub discussions** related to Linux on Acer Nitro laptops.  

This way, **other users with the same laptop model can contribute** and help you get a working NBFC config! 🚀
