# Guide to Bitz Miner CLI on Eclipse
---

## Install Dependecies
**1. Install Packages**
```bash
sudo apt-get update && sudo apt-get upgrade -y

sudo apt install screen curl nano  -y
```
**2. Install Rust**
```bash
 curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
* When Prompted, Enter `1` and wait unti installation compelete.
```bash
source $HOME/.cargo/env
```
**3. Install Solana CLI:**
```bash
curl --proto '=https' --tlsv1.2 -sSfL https://solana-install.solana.workers.dev | bash
```
* Close and reopen your Terminal.
```
solana version
```
* If you get `solana: command not found` RUN :
```bash
echo 'export PATH="/root/.local/share/solana/install/active_release/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```
```
solana --version
```

**4. Switch RPC**
```bash
solana config set --url https://mainnetbeta-rpc.eclipse.xyz/
```

---

## Wallet CLI
### 1. Create a CLI wallet
```bash
solana-keygen new
```
* Set a password or skip by pressing `Enter`.
* Save your Seed-Phrase & Public-Key
* `Public-Key`: Is your node **Eclipse wallet address**.

### 2. Export `Private-key`

1- Find Keypair path:
```bash
solana config get
```
* It gives your Keypair path like this: `~/.config/solana/id.json`

2- Export `Private-key`:
```bash
cat ~/.config/solana/id.json
```
* The exported array is your `Private-Key`, Save it.

### 3. Import and Fund Node Wallet
* Import `Private-Key` into your `Backpack` wallet.
* Fund it with `ETH` on `Eclipse` Network

---

## Install Bitz
```bash
cargo install bitz
```

---

## Run Bitz Miner
### 1. Open a screen
By opening a screen, you can run any process in the background, so it won't get terminated if you closed your VPS. (Windows users must keep their terminal open)
```bash
screen -S bitz
```

### 2. Start Miner
```bash
bitz collect
```

![image](https://github.com/user-attachments/assets/7c526a4b-07da-4ad5-889f-17674761b5e7)


### Usefull Commands

Check account info:
```bash
bitz account
```

Claim Bitz to your Node Wallet:
```bash
bitz claim
```
minimize screen:
  ```bash
  Ctrl+A+D
  ```
ON/OFF: 
```bash
screen -r bitz
 ```
