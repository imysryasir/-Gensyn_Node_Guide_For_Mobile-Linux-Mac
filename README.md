#  Gensyn_Node_Guide_For_Mobile,Linux,Mac



For All VPS users Install TERMIUS on your devices

# Install Python and Other Tools

* For **Linux/Wsl**

```
sudo apt update && sudo apt install -y python3 python3-venv python3-pip curl wget screen git lsof

```

* **For Mac**

```
brew install python
```

Check Version

```
python3 --version
```


# Install Node.js , npm & yarn

* For **Linux/Wsl**

```
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash - && sudo apt update && sudo apt install -y nodejs
```

* Install Yarn (linux)

```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
```

```
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list > /dev/null
```

```
sudo apt update && sudo apt install -y yarn
```


* For **Mac**

```
brew install node && corepack enable && npm install -g yarn
```

* Check version **(Linux/Mac)**

```
node -v
```
```
npm -v
```

```
yarn -v
```


<div align="center">

# 👨🏻‍💻 Start The Node (Linux/Mac) 

</div>


* 1️⃣ Clone RL-SWARM Repo

```
git clone https://github.com/gensyn-ai/rl-swarm.git
```


* 2️⃣ Create a screen session **(vps)**

```
screen -S gensyn
````

* 3️⃣ Navigate to rl-swarm

```
cd rl-swarm
```

* 4️⃣ Create & Activate a Virtual Environment

```
python3 -m venv .venv
source .venv/bin/activate
```

* 5️⃣ Install Left-over dependencies

```
cd modal-login
```

```
yarn install
```

```
yarn upgrade &&  yarn add next@latest &&  yarn add viem@latest
```

* 6️⃣ Run the swarm Node 🚀

```
cd ..
```

```
./run_rl_swarm.sh
```

- After Running the Above command it will promt `Would you like to connect to the Testnet? [Y/n]` Enter `Y`

- After than it will promt `>> Which swarm would you like to join (Math (A) or Math Hard (B))? [A/b]`  Enter   `a`

- After than it will promt `>> How many parameters (in billions)? [0.5, 1.5, 7, 32, 72]`    

👇See below and Choose the model Depends on Your System! 

<pre>
- Qwen 2.5 0.5B                - Recommended 4GB RAM, (1GB DOWNLOAD)
- Qwen 2.5 1.5B                - Recommended 8GB RAM, (4GB DOWNLOAD)
- Qwen 2.5 7B                  - Recommended 16GB RAM, (15GB DOWNLOAD)
- Qwen 2.5 32B (4 bit)         - Recommended 50GB RAM, (35GB DOWNLOAD)
- Qwen 2.5 72B (4 bit)         - Recommended 100GB RAM, (70GB DOWNLOAD)
</pre>
    
- After that A web Pop-Up will appear, It will ask u to Login ( if no web pop-up then u have to paste this on ur brower `http://localhost:3000/` 


- Now Login With Your Email Id, Enter OTP and back to ur Terminal/Wsl? **( VPS users check FAQ1 )**




- Now U can see A `ORG_ID` On ur Terminal..Save it!


* Now It will promt `Would you like to push models you train in the RL swarm to the Hugging Face Hub? [y/N]` Enter `N`

<img width="1223" alt="Screenshot 2025-05-01 at 4 47 30 PM" src="https://github.com/user-attachments/assets/05fcfc61-b562-4089-b21f-ba95b1036a24" />







Here we go🚀

Its Done ✅

It will Generate Logs Soon🙌


* Detach from `screen session` **(vps)**

Use `Ctrl + A` and then press `D`

* Attach to gensyn Screen to see Logs

```
screen -r gensyn
```



<div align="center">

#  🛠 FAQ & Troubleshoot 🛠

</div>


#  How to Login or access  http://localhost:3000/ in VPS? 📶

* Open a new Terminal and login ur vps 

* Allow Incoming connection on VPS

```
sudo apt install ufw -y
sudo ufw allow 22
sudo ufw allow 3000/tcp
```

* Enable ufw

```
sudo ufw enable
```

* Install cloudflared on the VPS

```
wget -q https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb
````

```
sudo dpkg -i cloudflared-linux-amd64.deb
```

* Check version

```
cloudflared --version
```

* Make sure your Node is running on port 3000 in Previous Screen

* Run the tunnel command

```
cloudflared tunnel --url http://localhost:3000
```

* Access the Link from your local machine

    


* Now follow Login!
 
* Done!✅



#  Save your `swarm.pem` file (for future login)

* open a wsl window 

* If U have to copy this file to your local machine from VPS then Run this command in Termius and COpy link to download--

```
[ -f backup.sh ] && rm backup.sh; curl -sSL -O https://raw.githubusercontent.com/zunxbt/gensyn-testnet/main/backup.sh && chmod +x backup.sh && ./backup.sh
```

It will save here in ur Terminal's Root Directory!


#  How To start the Next Day (Local Pc)

*
 ```
  cd rl-swarm
 ```

*
 ```
  python3 -m venv .venv
```

*
```
source .venv/bin/activate
```

*
```
./run_rl_swarm.sh
```

If you Face any error after rerun from second command and login to localhost again



<div align="center">

# 📈 How to upgrade to new release (v0.4.0) {Mac/Linux} 

</div>



* Move to rl-swarm directory
```
cd rl-swarm
```

* Pull the latest release

```
git pull
```

* Start the swarm Node 🚀

```
./run_rl_swarm.sh
```

- After Running the Above command it will promt `Would you like to connect to the Testnet? [Y/n]` Enter `Y`

- After than it will promt `>> Which swarm would you like to join (Math (A) or Math Hard (B))? [A/b]`  Enter   `a`

- After than it will promt `>> How many parameters (in billions)? [0.5, 1.5, 7, 32, 72]`    

👇See below and Choose the model Depends on Your System! 

<pre>
- Qwen 2.5 0.5B                - Recommended 4GB RAM, (1GB DOWNLOAD)
- Qwen 2.5 1.5B                - Recommended 8GB RAM, (4GB DOWNLOAD)
- Qwen 2.5 7B                  - Recommended 16GB RAM, (15GB DOWNLOAD)
- Qwen 2.5 32B (4 bit)         - Recommended 50GB RAM, (35GB DOWNLOAD)
- Qwen 2.5 72B (4 bit)         - Recommended 100GB RAM, (70GB DOWNLOAD)
</pre>
    
- After that A web Pop-Up will appear, It will ask u to Login ( if no web pop-up then u have to paste this on ur brower `http://localhost:3000/` 


- Now Login With Your Email Id, Enter OTP and back to ur Termius/Wsl? **( VPS users check FAQ1 )**



- Now U can see A `ORG_ID` On ur Terminal..Save it!


* Now It will promt `Would you like to push models you train in the RL swarm to the Hugging Face Hub? [y/N]` Enter `N`


## ⚠️ Troubleshooting

### 🔴 Daemon failed to start in 15.0 seconds
- If you are facing this issue then follow this step by step guide
- First use tihs command
```
nano $(python3 -c "import hivemind.p2p.p2p_daemon as m; print(m.__file__)")
```
- Then scroll down and look for this line `startup_timeout: float = 15,` , here u need to modify this 15 with 120, and after modifying it will look like this : `startup_timeout: float = 120,`
- Save this changes, first use `Ctrl` + `X` and then press `Y` and then press `Enter`
- Now use this command again to run `rl-swarm`
```bash
./run_rl_swarm.sh
```



###  Check Rewards
- Visit : https://gensyn-node.vercel.app/
- Enter Peer-ID that you often see this in your logs


> [!Note]
> If you see `0x0000000000000000000000000000000000000000` in `Connected EOA Address` section, that means your contribution is not being recorded, so you should run the node from beginning with fresh new email (means u need to delete existing `swarm.pem` file









👉 Join TG for more Updates: https://t.me/kind_cr


Follow official Docs for more info and Errors!

