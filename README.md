# am-nodejs-proxy
基于 Node.js 的 vless 实现包。它在各种 Node.js 环境中都能运行，包括但不限于：Windows、Linux、MacOS、Android、iOS、树莓派等。同时，它也适用于各种 PaaS 平台，如：replit、heroku 等。

- [中文文档](./README_CN.md) 
- [视频教程](https://youtu.be/tj9uD575R80)
- [Telegram交流群](https://t.me/AM_CLUBS)
- [YouTube频道](https://youtube.com/@AM_CLUB)
- [Github仓库](https://github.com/ansoncloud8)

This README explains how to set up and use the `start.sh` script to manage the project components.

## Initial Setup

1. Connect to your host using SSH:

```
ssh <username>@<panel>.serv00.com
```

Use the information emailed to you by serv00.

2. Enable management permissions:

```
devil binexec on
```

***AFTER THIS STEP, EXIT FROM SSH AND LOG IN AGAIN.***

3. Clone the repository:

```
cd domains/<username>.serv00.net
git clone https://github.com/ansoncloud8/am-nodejs-proxy.git
cd am-nodejs-proxy
```

## Usage

To use the script, run:

```
./start.sh <action> <sub-action>
```

| Action |  Sub-Action   |         Command         |                  Description                   |
| :----: | :-----------: | :---------------------: | :--------------------------------------------: |
| setup  |   xray/node   | `./start.sh setup xray` |       Setup services in a single command       |
| check  |   xray/node   | `./start.sh check xray` |     Checks Cloudflared and other services      |
|  show  | xray/node/all | `./start.sh show xray`  | Displays VLESS connection links from node/.env |

***NODE.JS AND XRAY CANNOT BE ACTIVE SIMULTANEOUSLY. ONLY ONE OF THEM SHOULD BE RUNNING AT A TIME.***

## Checking Sessions

To check the status of a specific component, you can attach to its tmux session:

```
tmux attach -t <session>
```

Replace `<session>` with:

- `cf` for Cloudflared
- `node` for Node.js
- `xray` for Xray

For example, to check the Cloudflared session:

```
tmux attach -t cf
```

To detach from a tmux session without closing it, press:

```
Ctrl + b, then d
```

This key combination allows you to exit the session while leaving it running in the background.

## Notes

- The script uses tmux to manage sessions for each component.
- Cron jobs are set up for periodic maintenance of Node.js and Xray.
- Cloudflared, Node.js, and Xray configurations are generated automatically.
- The script includes functions for port management and cleanup.

vless://port@icook.tw:443?security=tls&sni=is&alpn=h2,http/1.1&fp=chrome&type=ws&path=/&host=is&encryption=none#[pl]%20[vl-tl-ws]%20[at-ar-no]
vless://This@visa.com:443?security=tls&sni=is&alpn=h2,http/1.1&fp=chrome&type=ws&path=/ws?ed%3D2048&host=is&encryption=none#[pl]%20[vl-tl-ws]%20[at-ar]
