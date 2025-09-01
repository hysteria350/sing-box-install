# Linux 平台 sing-box 安装与配置教程（2025 最新）

## sing-box 介绍

sing-box 是一款开源、跨平台的下一代科学上网与网络代理软件，由社区开发并活跃维护。它以 高性能、模块化、可扩展 为核心设计理念，能够替代 v2ray、xray 等传统代理工具。
相比旧一代软件，sing-box 在架构上更为简洁，支持 多种协议，如 VLESS、VMess、Shadowsocks、Trojan、Hysteria、Naïve 等，并内置 分流、规则匹配、DNS 劫持 等功能，方便用户根据需求灵活配置。

其突出优势在于：

1. 高性能 —— 使用 Go 语言编写，内存占用低，启动与连接速度快。
2. 跨平台 —— 支持 Linux、Windows、macOS、Android、iOS 等系统，适配性强。
3. 强大分流 —— 内置类 Surge/Clash 风格的规则系统，轻松实现按域名、IP、地理位置分流。
4. 灵活配置 —— JSON 配置文件清晰易扩展，且不断完善 GUI 客户端（如 NekoBox、SFA、SFM），降低使用门槛。
5. 未来导向 —— 原生支持 QUIC、gRPC 等新一代传输协议，并兼容多种加密算法，具备长远发展潜力。

得益于社区生态，sing-box 不仅适合个人用户科学上网，也适合机场主部署作为后端。其高效的网络处理能力和对新协议的快速跟进，使其逐渐成为新一代代理软件的主流选择。

## sing-box 安装

针对不同的操作系统，请参考不同的安装步骤。

### Debian 系列 Linux 系统下载并安装 sing-box

对于 debian 系列发行版（Ubuntu, Mint, MX, Kubuntu, Zorin 等等）

```bash

sudo apt update  -y
sudo apt install sing-box

# 设置为开机自启动
sudo systemctl enable sing-box
```

### Redhat 系列 Linux 系统下载并安装 sing-box

对于 Redhat 系列发行版（Centos, Fedora, AlmaLinux, Rocky Linux 等）

```bash

sudo dnf config-manager addrepo --from-repofile=https://sing-box.app/sing-box.repo 
sudo dnf install sing-box

# 设置为开机自启动
sudo systemctl enable sing-box
```

### 一键脚本 sing-box

该脚本从 GitHub 发布中下载并安装最新的软件包，适用于基于 deb 或 rpm 的 Linux 发行版、ArchLinux 和 OpenWrt。

安装正式版

```bash

curl -fsSL https://sing-box.app/install.sh | sh

```

## 配置 sing-box

```bash

sudo mkdir -p /etc/sing-box
sudo nano /etc/sing-box/config.json

```

在 config.json 中写入你需要的代理配置（例如 VLESS、Shadowsocks 等）。

## 参考文档

- [包管理器](https://sing-box.sagernet.org/zh/installation/package-manager/)
- [sing-box config examples](https://github.com/chika0801/sing-box-examples)


