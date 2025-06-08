# Gensyn Node Setup Guide

> **Note:** Backup your `swam.pem` before deleting any files.

---

### 🛡️ Backup `swam.pem`

```
cp ~/swam.pem ~/swam.pem.bak
```

---

### ❌ Delete Previous Files (optional)

```
rm -rf ~/rl-swarm
```

---

### 🔁 Update & Install System Packages

```
sudo apt update && sudo apt upgrade -y
```

```
sudo apt install -y curl git wget nano tmux htop nvme-cli lz4 jq make gcc clang build-essential autoconf automake pkg-config libssl-dev libleveldb-dev libgbm1 bsdmainutils ncdu unzip tar
```

```
sudo apt-get install python3 python3-pip python3-venv python3-dev -y
```

---

### 🧱 Node.js & Yarn

```
sudo apt-get update && curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
```

```
sudo apt-get install -y nodejs && node -v && npm -v
```

```
sudo npm install -g yarn && yarn -v
```

---

### 🐍 Python Setup

```
sudo apt install -y python3 && sudo apt install -y python3-pip && python3 --version && pip3 --version
```

```
sudo apt install python3-dev python3-venv build-essential -y
```

---

### 📦 Extra Yarn Setup

```
sudo apt-get update && sudo apt-get install -y curl gnupg apt-transport-https
```

```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
```

```
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
```

```
sudo apt-get update && sudo apt-get install -y yarn && yarn --version
```

---

### 📁 Clone & Run Gensyn

```
git clone https://github.com/gensyn-ai/rl-swarm/
```

```
cd rl-swarm
```

```
sudo apt install screen -y
```

```
screen -S gensyn
```

---

### 🚀 Start Node

```
cd $HOME && rm -rf gensyn-testnet && git clone https://github.com/zunxbt/gensyn-testnet.git && chmod +x gensyn-testnet/gensyn.sh && ./gensyn-testnet/gensyn.sh
```

---

### 🔐 Enable Login & Cloudflare Tunnel

```
sudo apt install ufw -y
```

```
sudo ufw allow 3000/tcp
```

```
sudo ufw enable
```

```
wget -q https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb
```

```
sudo dpkg -i cloudflared-linux-amd64.deb
```

```
cloudflared tunnel --url http://localhost:3000
```

---

### ⚠️ Fix “Unbounded” Error

```
cd $HOME/rl-swarm/hivemind_exp/configs/mac/
```

```
ls
```

```
sudo apt update
```

```
sudo apt install nano
```

```
sudo nano grp*.yaml
```

Inside the opened file, change:
```
torch_dtype: float32
bf16: false
tf32: false
gradient_checkpointing: false
per_device_train_batch_size: 1
```

Save with `Ctrl + X`, then `Y`, then `Enter`.

---

### 🔄 Restart Node

```
cd $HOME && rm -rf gensyn-testnet && git clone https://github.com/zunxbt/gensyn-testnet.git && chmod +x gensyn-testnet/gensyn.sh && ./gensyn-testnet/gensyn.sh
```

# Gensyn Node DHTNODE BOOTSTRAP ERROR

## Error Solution ✅

```
cd rl-swarm
```

```
git switch main
git reset --hard
git clean -fd
git pull origin main
```

```
curl https://raw.githubusercontent.com/imysryasir/Gsnyn-1-Click-Solutions/refs/heads/main/updated-auto-termination-solution | bash
```

```
cd $HOME && rm -rf gensyn-testnet && git clone https://github.com/zunxbt/gensyn-testnet.git && chmod +x gensyn-testnet/gensyn.sh && ./gensyn-testnet/gensyn.sh
```
