Here is the step-by-step summary of the video with the specific commands used for the installation and setup of **OpenClaw**.

### **1. System Preparation**

* **Switch to Root User:**
```bash
sudo su

```


[[00:13](http://www.youtube.com/watch?v=Zqnzg6W9rjY&t=13)]
* **Update System Repositories:** Use the standard update and upgrade commands to ensure the system is ready [[00:26](http://www.youtube.com/watch?v=Zqnzg6W9rjY&t=26)].

### **2. Install Docker and Docker Compose**

* **Official Installation Script:**
```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sh get-docker.sh

```


*(Note: The video uses the official automated script to install Docker and its components)* [[00:38](http://www.youtube.com/watch?v=Zqnzg6W9rjY&t=38)].

### **3. Download and Configure OpenClaw**

* **Clone the Repository:**
```bash
git clone https://github.com/open-claw/open-claw.git
cd open-claw

```


[[00:53](http://www.youtube.com/watch?v=Zqnzg6W9rjY&t=53)]
* **Export the Alpine Image Variable:**
```bash
export OPENCLAW_IMAGE=alfane/openclaw:latest

```


[[01:40](http://www.youtube.com/watch?v=Zqnzg6W9rjY&t=100)]
* **Create Environment File:** Create a `.env` file and add the configuration paths [[02:04](http://www.youtube.com/watch?v=Zqnzg6W9rjY&t=124)]:
```text
OPENCLAW_CONFIG_DIR=/root/.openclaw/config
OPENCLAW_WORKSPACE_DIR=/root/.openclaw/workspace

```



### **4. Launch the Gateway**

* **Start the Docker Container:**
```bash
docker compose up -d

```


[[02:23](http://www.youtube.com/watch?v=Zqnzg6W9rjY&t=143)]
* **Fix Permissions:** Update ownership of the config directory:
```bash
chown -R 1000:1000 /root/.openclaw

```


[[03:08](http://www.youtube.com/watch?v=Zqnzg6W9rjY&t=188)]

### **5. Onboarding & API Setup**

* **Run Onboarding Wizard:**
```bash
docker compose run onboard

```


[[03:16](http://www.youtube.com/watch?v=Zqnzg6W9rjY&t=196)]
* **Configure Google Gemini:** Follow the prompts to enter your API key from Google AI Studio [[03:32](http://www.youtube.com/watch?v=Zqnzg6W9rjY&t=212)].
* **Configure Telegram:** Enter your Telegram Bot Token obtained from **BotFather** [[05:03](http://www.youtube.com/watch?v=Zqnzg6W9rjY&t=303)].

### **6. Pairing and Testing**

* **Approve Telegram Pairing:**
Instead of the standard local command, use Docker Compose to approve the pairing request:
```bash
docker compose run pair --approve [YOUR_TELEGRAM_SENDER_ID]

```


[[05:53](http://www.youtube.com/watch?v=Zqnzg6W9rjY&t=353)]
* **Verify Installation:** Check the container status:
```bash
docker ps

```


[[06:25](http://www.youtube.com/watch?v=Zqnzg6W9rjY&t=385)]

You can watch the full demonstration here: [https://www.youtube.com/watch?v=Zqnzg6W9rjY](https://www.youtube.com/watch?v=Zqnzg6W9rjY)
