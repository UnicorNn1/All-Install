# <h1 align="center">Taiko Node Setup</h1>
![image](https://github.com/UnicorNn1/Rivalz/assets/82544940/6d2d17dd-c443-44ce-988c-7dc59fe81435)


## Links:
 * [Taiko Official Website](https://taiko.xyz/)
 * [Taiko Official Twitter](https://twitter.com/taikoxyz)
 * [Taiko Official Discord](https://discord.com/invite/taikoxyz)
 * [Taiko Node Documentation](https://docs.taiko.xyz/guides/run-a-taiko-node/)

### System Requirements
| System | Minimum Requirements | 
| ------------ | ------------ |
| ✔️CPU |	8 vCPU|
| ✔️RAM	| 16 GB |
| ✔️Storage	| 500 GB SSD or 1TB |
## System Update
```shell
sudo apt update
```

```shell
sudo apt upgrade
```

```shell
apt install docker-compose
```
### Docker Setup
```shell

sudo apt-get update && sudo apt install jq && sudo apt install apt-transport-https ca-certificates curl software-properties-common -y && curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - && sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable" && sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin && sudo apt-get install docker-compose-plugin

```

```shell
chmod +x /usr/local/bin/docker-compose

```
## Download Taiko files
```
git clone https://github.com/taikoxyz/simple-taiko-node.git
```

Create Screen
```
screen -S taiko
```

Let's Login to Taiko Folder
```
cd simple-taiko-node
```

Let's create an .env file. After creating this file, you will get the private key of the address you use in the Taiko platform testnet from your Fox wallet and save it in the .env file. 
```
cp .env.sample .env
```

Let's enter the .Env file, here is the bottom section you need to change. <br>

```
nano .env
```

<br>

*ENABLE_PROPOSER=true  ( We translate from true from false ) <br>
*L1_PROPOSER_PRIVATE_KEY= We write the private key of our wallet <br>
*L2_SUGGESTED_FEE_RECIPIENT= We write our wallet address. <br>
*ctrl + x We save by saying Yes. <br>

## Starting

After this process, it will install and start synchronising.

```
docker compose up
```

## Viewing block via Explorer 

Type your address via Explorer, if it is as in the picture below, there is no problem, of course it needs to be synchronised first. 

 * [Explorer](https://l2explorer.a1.taiko.xyz/)

## Logs Vision
```
cd simple-taiko-node
docker compose logs -f
```
## Stop

After this process, it will install and start synchronising.

```
docker compose down
```
## Deleting a Node
```
docker compose down -v
cd
rm -fr simple-taiko-node
```

