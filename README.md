# What is Sonaric AI and how to run the Sonaric Node on VPS server to recieve points. 
The Sonaric Network is a cutting-edge, AI-driven platform designed to make blockchain computing smarter and more efficient. By autonomously matching pooled resources with demand across different blockchain networks, it ensures optimal resource allocation. For contributors, it promises fair rewards, making it an innovative solution for decentralized computing.

Although still in its early stages, the project has generated interest due to the credibility of its investors, advisors, and backers, as detailed on https://sonaric.xyz/. However, as with any emerging technology, it's crucial to do your own research (DYOR) before getting involved.

## System Requirements
| Ram | cpu     | disk                      |
| :-------- | :------- | :-------------------------------- |
| `2 GB`      | `2 Core` | `10-20 GB SSD` |

## 1. Dependecies
```console
# Update packages
sudo apt update && apt upgrade -y

sudo apt install curl make wget clang net-tools pkg-config libssl-dev build-essential jq lz4 gcc unzip snapd -y
```

## 2. Install the Sonaric Node
```console
sh -c "$(curl -fsSL https://get.sonaric.xyz/scripts/install.sh)"
```
* After Installation, Your node starts running in the background

## 3. Check your node is running
```console
sonaric node-info
```
![Screenshot_143](https://github.com/user-attachments/assets/d0bd314b-2d65-49cd-8057-e7ae1a84bf5a)

## 4. Update Sonaric
```console
apt-get update
apt-get install sonaricd sonaric

# To confirm the node is running the latest version
sonaric node-info

# Update if needed
sh -c "$(curl -fsSL https://get.sonaric.xyz/scripts/install.sh)"
```

## 5. Backup your node

* In order to export the current identity of your node to a file called your-node-name.identity, run the following command
```console
sonaric identity-export -o your-node-name.identity
```
> You can specify a different file name by changing your-node-name.identity to the desired file name. The name is arbitrary and can be anything you like.
>
> Transfer and save the file in your local PC. You can use Mobaxterm or Termius to directly access to your directories
>
> It is normal to see different file contents each time you export the identity. The file is encrypted using a method that randomizes the output.

## 6. Discord Role (Operator)

Join Discord: https://discord.gg/jy5EZwhtZH

**1- Type: /addnode in #general**

**2- Copy the code**

**3- Move to your VPS, then replace your code with `CODE`:**
```
sonaric node-register CODE
```

**Type: /node in #general to list your nodes**

## 7. Multiple Nodes
**You can add multiple nodes to your cluster by just adding them to your discord account in the same way**

### 8. Optional: Delete node
```
sudo apt remove --purge sonaricd sonaric
```
