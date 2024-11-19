# BananaPI BPI-F3 运行 ChatGLM2 Q4 量化版

## 开发板说明

### 开发板简介

开发板介绍文档 (Milk-V Docs)；https://milkv.io/zh/docs/jupiter/overview

Milk-V Jupiter 是一款基于 Spacemit K1/M1 的 Mini-ITX 设备。该设备集成了标准 PCIe X8 插槽，支持常见 PCIe 设备，如显卡、PCIe 转 SATA 转接卡、网卡；双千兆以太网接口；板载 WI-FI6/BT5.2 模组；支持 NVMe SSD，是入门级 RISC-V Desktop 首选。

### Demo简介

* demo说明

  <!-- > 这个demo大致是干什么的
  > -->
    本demo展示了如何在Milk-V Jupiter上运行ChatGLM2 Q4 量化版模型。

* demo源码链接

  <!-- > demo完整源码链接；该信息将用于包管理器集成/打包集成的信息输入
  > -->
    [bianbu-linux](https://gitee.com/bianbu-linux)
* sdk 及链接

    [inferllm-chatglm](https://forum.banana-pi.org/t/bpi-f3-large-model-demo/18541)
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

安装chatglm推理工具

```shell
sudo apt-get update
sudo apt-get install inferllm-chatglm
# 安装inferllm-chatglm包时，会自动下载chatglm2-q4模型
```

运行chatglm2推理

```shell
user@k1:~/llm-tests$ /usr/bin/inferllm-chatglm -m /usr/share/inferllm/chatglm2-q4.bin -t 4 -v 2
main: seed = 1732005254
skip weight transformer.rotary_pos_emb.inv_freq
total weight length = 3903463424
main: interactive mode on.
sampling parameters: temp = 0.100000, top_k = 40, top_p = 0.950000, repeat_last_n = 64, repeat_penalty = 1.300000


== 运行模型中. ==
 - 输入 Ctrl+C 将在退出程序.
 - 如果你想换行，请在行末输入'\'符号.

> 你好
 你好👋！我是人工智能助手 ChatGLM2-6B，很高兴见到你，欢迎问我任何问题。

> 泰山有多高
 泰山是中国著名的名山之一，位于山东省泰安市境内，主峰玉皇顶海拔为15329米🌉。泰山也是世界文化与自然双重遗产、中国 5A 
级旅游景区，吸引着无数游客前来观光旅游。

> ^C
Run Model Summary:
Total Model Compute Time:   208.563480s
Total Model Compute Token:  120
Average Token Compute Time: 1738.029003ms
Average Token Generation Speed: 0.575364token/s
```


### Demo运行总结

#### sdk 集成说明

<!-- > 给出需要 ruyisdk 集成建议或者总结; -->
该demo在Milk-V Jupiter上运行，需要安装spacemit在bianbu linux上打包📦的chatglm推理工具，推理工具安装包为inferllm-chatglm，安装包中包含chatglm2-6b-q4模型。

如要整合的话可以考虑将intferllm推理工具和模型打包到ruyisdk中，方便ruyisdk集成。

<!-- #### 问题及状态

> 问题描述或者问题issue链接；用于跟踪/推动问题解决； -->