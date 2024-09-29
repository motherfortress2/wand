#  Wand Installation Script for GitHub Codespaces

> [!NOTE]
> May need to fork other things soon. nginx and all that.

> [!IMPORTANT]
> If this works, it will open a new gate to inexperienced coders, so it's necessary to say, if you are inexperienced this is __NOT__ for you.

Wand makes it easy to configure dash, houdini and a media server utilizing docker & docker-compose.

> [!NOTE]
> This can also be ran on Windows using WSL.

## Installation script
**Step 1** run the script
```bash
bash <(curl -s https://raw.githubusercontent.com/motherfortress2/wand/master/install.sh)
```
**Step 2** Answer Questions which are:
* Database password (Leave blank for random password)
* Hostname (example: `clubpenguin.com`) (Leave empty for localhost) (This fork attempts to use the /play setup for free subdomain support. May not work but I tried.)
* External IP Address (Leave empty for localhost) (If you don't know an external IP address, my best bet is to try some other source, I don't want people getting harmed.)
**Step 3** Run and enjoy.
Run this command:
```bash
$ cd wand && sudo docker-compose up
```
## Manual setup

> [!IMPORTANT]
> This fork is for GH Codespaces, DO NOT USE THIS! Use the install script.

**Step 1** Choose your Linux Distribution

<details>
  <summary>Debian/Ubuntu</summary>

```bash
$ sudo apt update
$ sudo apt install git curl
$ curl -fsSL https://get.docker.com -o get-docker.sh
$ sh get-docker.sh
$ sudo curl -L "https://github.com/docker/compose/releases/download/v2.20.3/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
$ sudo chmod +x /usr/local/bin/docker-compose
```
</details>

<details>
  <summary>Fedora/RHEL</summary>
  
```bash
$ sudo dnf update
$ sudo dnf install git curl
$ curl -fsSL https://get.docker.com -o get-docker.sh
$ sh get-docker.sh
$ sudo curl -L "https://github.com/docker/compose/releases/download/v2.20.3/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
$ sudo chmod +x /usr/local/bin/docker-compose
```
</details>

<details>
  <summary>Arch based distros</summary>
  
```bash
$ sudo pacman -Syu
$ sudo pacman -S docker docker-compose git curl
$ systemctl start docker.service
$ systemctl enable docker.service
```
</details>


**Step 2** Clone the repository & submodules
```bash
$ git clone --recurse-submodules https://github.com/solero/wand && cd wand
```

**Step 3** Edit the config file (optional, default values are fine for a local setup)
```bash
$ nano .env
```

**Step 4** Start the services
```bash
$ sudo docker-compose up
```

**Step 5** You're done!
