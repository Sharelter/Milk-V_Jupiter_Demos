# Milk-V Juipter 运行 Llama3.2 3B

## 开发板说明

### 开发板简介

开发板介绍文档 (Milk-V Docs)；https://milkv.io/zh/docs/jupiter/overview

Milk-V Jupiter 是一款基于 Spacemit K1/M1 的 Mini-ITX 设备。该设备集成了标准 PCIe X8 插槽，支持常见 PCIe 设备，如显卡、PCIe 转 SATA 转接卡、网卡；双千兆以太网接口；板载 WI-FI6/BT5.2 模组；支持 NVMe SSD，是入门级 RISC-V Desktop 首选。

### Demo简介

* demo说明

  <!-- > 这个demo大致是干什么的「方案选单」
  > -->
    本demo展示了如何在Milk-V Jupiter上运行 Llama3.2 3B 模型

* sdk 及链接

    [SpaceMit ollama](https://archive.spacemit.com/spacemit-ai/ollama/)
<!-- * Demo 运行所需的 SDK；用于 ruyisdk 集成 sdk； -->

### Demo运行

<!-- > * 另起文档单独描述Demo运行起来的详细步骤；
> * 要求0基础入门级别的人能够按照文档操作；
> * 文档目的：
>   * 集成前：该文档后续用于IDE集成参考；
>   * 集成后：尽量能够做到替换到文档中的通过ruyisdk下载解压等操作外，其它内容可以大幅度参考和复用；修改后的文档将作为ruyisdk社区文档/教材/宣发用途；
> * 可选，欢迎出运行视频、玩机视频； 用于更加直观的 IDE集成指导、社区文档/教材/宣发用途； -->

运行环境：
- 开发板：Milk-V Jupiter (16G RAM Version)
- 操作系统：Bianbu Linux 2.0
- 连接方式：SSH

> 由于模型运行所需的文件较多，建议在RAM大于8GB的型号上运行该demo。

下载并解压ollama推理工具

```shell
# 下载spacemit修改的ollama
wget https://archive.spacemit.com/spacemit-ai/ollama/jdsk-ollama-v0.0.1.tar.gz
# 解压tar-gzip包
tar xvf jdsk-ollama-v0.0.1.tar.gz
```

运行ollama推理服务端

```shell
cd ollama
chmod +x ollama
./ollama serve
```

在另一个终端中运行：

```shell
username@k1:~/llm-tests/ollama$ ./ollama run llama3.2
>>> hello
Hello! How can I assist you today?

>>> who are you?
I'm an artificial intelligence model, which means I'm a computer program designed to simulate human-like 
conversations and answer questions to the best of my ability. I don't have a personal identity or emotions like 
humans do, but I'm here to provide information, help with tasks, and engage in conversation.

I was trained on a massive dataset of text from various sources, which allows me to understand and respond to a 
wide range of topics and questions. My goal is to assist users like you with their queries and provide helpful 
and accurate information.

So, that's me in a nutshell! What about you? How can I help you today?

>>> /bye
```


### Demo运行总结

#### sdk 集成说明

<!-- > 给出需要 ruyisdk 集成建议或者总结; -->

K1处理器运行Llama3.2 3B模型实际使用中token生成速度非常缓慢，无法满足实际使用需求

推测可能没有spacemit的扩展指令集支持


#### 问题及状态

<!-- > 问题描述或者问题issue链接；用于跟踪/推动问题解决； -->


该demo运行需要进迭时空的修改版ollama推理工具，但是未找到这个工具的原始代码

如需集成的话现在只能打二进制包，无法进行源码集成