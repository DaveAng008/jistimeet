# Jitsi Meet Deployment for Coolify

> **Domain**: https://jitsi-meet.daveang.store  
> **Server IP**: 145.79.11.133  
> **Managed by**: Coolify PaaS (Docker Compose)

---

## 🚀 Coolify 部署步骤 (Deployment on Coolify)

1. **新建应用 (New Resource)**：
   - 在 Coolify 面板中选择你的 Project / Environment。
   - 点击 **+ New Resource** -> 选择 **Public Repository** 或 **Git Repository**。
   - 填入仓库地址：`https://github.com/DaveAng008/jistimeet`。
   - 构建类型选择 **Docker Compose**。
2. **域名绑定 (Domain)**：
   - 在 `web` 服务配置中设置域名为：`https://jitsi-meet.daveang.store`。
   - 端口指向容器端口 `8000`。
3. **防火墙配置 (Firewall / Security Group)**：
   - **UDP 10000**：必须在云服务商防火墙与宿主机中完全放行（WebRTC 音视频媒体流直连）。
   - **TCP 80 & 443**：放行（网页访问与 SSL 证书申请）。
4. **环境变量 (Environment Variables)**：
   - 仓库内已包含配置好的 `.env` 文件（包含强随机生成的内部组件通信密钥及公网 IP）。

---

# Jitsi Meet on Docker

![](resources/jitsi-docker.png)

[Jitsi](https://jitsi.org/) is a set of Open Source projects that allows you to easily build and deploy secure videoconferencing solutions.

[Jitsi Meet](https://jitsi.org/jitsi-meet/) is a fully encrypted, 100% Open Source video conferencing solution that you can use all day, every day, for free — with no account needed.

This repository contains the necessary tools to run a Jitsi Meet stack on [Docker](https://www.docker.com) using [Docker Compose](https://docs.docker.com/compose/).

All our images are published on the [GitHub Container Registry (GHCR)](https://github.com/orgs/jitsi/packages).

## Tags

These are the currently published tags for all our images:

Tag | Description
-- | --
`stable` | Points to the latest stable release
`stable-NNNN-X` | A stable release
`unstable` | Points to the latest unstable release
`unstable-YYYY-MM-DD` | Daily unstable release

## Installation

The installation manual is available [here](https://jitsi.github.io/handbook/docs/devops-guide/devops-guide-docker).

### Kubernetes

If you plan to install the jitsi-meet stack on a Kubernetes cluster you can find tools and tutorials in the project [Jitsi on Kubernetes](https://github.com/jitsi-contrib/jitsi-kubernetes).

