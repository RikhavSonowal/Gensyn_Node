
# Gensyn RL-Swarm Node Setup Guide 🚀

## 1) System Requirements aur Dependencies Install karna 🔧

### 1. System Packages update karo  
```bash
sudo apt-get update && sudo apt-get upgrade -y
```

### 2. Zaroori tools aur utilities install karo  
```bash
sudo apt install screen curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev -y
```
### 4. Python install karo 🐍  
```bash
sudo apt-get install python3 python3-pip python3-venv python3-dev -y
```

### 5. Node.js install karo  
```bash
sudo apt-get update
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt-get install -y nodejs
node -v
```

### 6. Yarn install karo  
```bash
sudo npm install -g yarn
yarn -v

# Ya phir official script se install karna ho to
curl -o- -L https://yarnpkg.com/install.sh | bash
export PATH="$HOME/.yarn/bin:$HOME/.config/yarn/global/node_modules/.bin:$PATH"
source ~/.bashrc
```

---

## 2) Repository clone karo 📂  
```bash
git clone https://github.com/gensyn-ai/rl-swarm/
cd rl-swarm
```

---

## 3) HuggingFace API key lo 🔑

1. [HuggingFace](https://huggingface.co/) pe account banao  
2. [Access Token](https://huggingface.co/settings/tokens) create karo, `Write` permissions ke saath, aur safe rakho  

---

## 4) Node run karo (VPS ya WSL dono ke liye) 💻

- Background mein run karne ke liye screen open karo  
```bash
screen -S swarm
```

- Python virtual environment banao aur activate karo  
```bash
python3 -m venv .venv
source .venv/bin/activate
```

- (Optional) Agar outdated build errors aaye to  
```bash
pip install -r requirements.txt
cd modal-login
yarn install
yarn upgrade && yarn add next@latest && yarn add viem@latest
cd ..
cd rl-swarm
```

- Node start karo  
```bash
./run_rl_swarm.sh
```
`Y` press karo ✅

---

## 5) Login karo 🔐

- Logs mein dikhega:  
`Waiting for userData.json to be created...`

- Browser mein login page open karo:  
  - Local PC ke liye: `http://localhost:3000/`  
  - VPS users ke liye: Agar email mein OTP nahi mil raha hai to port forwarding karo.

### VPS users ke liye Port Forwarding ⚠️  
- Apne local Windows PC mein PowerShell open karo  
- Yeh command run karo (Server_IP aur SSH_PORT apne VPS ke hisaab se badlo):  
```bash
ssh -L 3000:localhost:3000 root@Server_IP -p SSH_PORT
```
- Example:  
```bash
ssh -L 3000:localhost:3000 root@137.12.0.0 -p 22
```
- Password do, phir browser mein `http://localhost:3000/` open karo aur login karo  

---

## Official Dashboard 🖥️  
https://dashboard.gensyn.ai/  

Yahan apne node ka naam search karo, aur jab first training complete ho jayegi tab stats dekh sakte ho.  

---

## Next Day ke liye Node start karna ⏩  
```bash
cd rl-swarm
screen -S swarm
python3 -m venv .venv
source .venv/bin/activate
./run_rl_swarm.sh
```
`Y` press karo aur node chalao  

---

## Agar Gensyn Node mein Error aaye to Solution 🔧

1. `pip install --force-reinstall trl==0.19.1` chalao  
2. `pip freeze` command run karo (package versions check karne ke liye)  
3. Phir se node run karo: `./run_rl_swarm.sh`  

Thank You 🙏

---

## Gensyn Node ki aur jankari ke liye join karo Crypto Rik ka Telegram Channel!  
👉 https://t.me/CryptoRikhav  

---

Agar koi doubt ya help chahiye, toh batao! 😊✨
