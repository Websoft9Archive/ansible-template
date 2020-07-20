## Introduction

[English](/README.md) | [简体中文](/README-zh.md)  

**RabbitMQ 自动化安装与部署**是由 [Websoft9](https://www.websoft9.com) 研发的 [RabbitMQ](https://rabbitmq.io/) 自动化安装程序，开发语言是 Ansible。使用本项目，只需要用户在 Linux 上运行一条命令，即可自动化安装 RabbitMQ，让原本复杂的安装过程变得没有任何技术门槛。  

## System Requirement

安装本项目，确保符合如下的条件：

| 条件       | 详情       | 备注  |
| ------------ | ------------ | ----- |
| 操作系统       | CentOS7.x, Ubuntu18.04, Amazon Linux2       |  可选  |
| 公有云| AWS, Azure, 阿里云, 华为云, 腾讯云 | 可选 |
| 私有云|  KVM, VMware, VirtualBox, OpenStack | 可选 |
| 服务器配置 | 最低1核1G，安装时所需的带宽不低于10M |  建议采用按量100M带宽 |

更多请见 [官方 System requirement](https://www.rabbitmq.com/download.html)

## Ecosystem

包含的核心组件为：可选 RabbitMQ2.8.24/3.0.7/3.2.13/4.0.14/5.0.7/stable 多个版本

更多请见 [参数表](/docs/zh/stack-components.md)

## Installation

### Run All-in-one Installer

以 **root** 权限运行自动化安装脚本，开始安装。必要时需要用户做出交互式选择，然后耐心等待直至安装成功。

```
$ sudo su -
$ wget -N https://raw.githubusercontent.com/Websoft9/ansible-linux/master/scripts/install.sh; bash install.sh -r rabbitmq
```

网络连接中断或网络不通，会导致SSH中断，安装就会失败，此时请重新安装。

### Image on Cloud 

多种原因导致无法顺利安装，请使用我们在公有云上发布的 [RabbitMQ 镜像](https://apps.websoft9.com/rabbitmq) 的部署方式

## Documentation

RabbitMQ Administrator Guide ([English](https://support.websoft9.com/docs/rabbitmq/zh) | [简体中文](https://support.websoft9.com/docs/rabbitmq/zh))

## Changelog

Detailed changes are documented in the [CHANGELOG](/CHANGELOG.md).

## License

[MIT](http://opensource.org/licenses/MIT), Additional Terms: It is not allowed to publish free or paid image based on this project in any Cloud platform's MarketPlace

Copyright (c) 2016-present, Websoft9

## FAQ

#### 命令脚本部署与镜像部署有什么区别？

请参考：[镜像部署-vs-脚本部署](https://support.websoft9.com/docs/faq/zh/bz-product.html#镜像部署-vs-脚本部署)

#### 本项目支持在 Ansible Tower 上运行吗
Yes

#### 如何安装和查看最新版？

本项目通过[RabbitMQ 官方仓库源](https://packagecloud.io/rabbitmq/rabbitmq-server/install)安装，每次安装均可保证为最新版本。通过[官方下载](https://www.rabbitmq.com/download.html)页面查看官方版号。 
