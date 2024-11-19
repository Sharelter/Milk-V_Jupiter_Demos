# Milv-V Jupiter 运行进迭时空InferLLM Demo

## 开发板说明

Milk-V Jupiter 是一款基于 Spacemit K1/M1 的 Mini-ITX 设备。该设备集成了标准 PCIe X8 插槽，支持常见 PCIe 设备，如显卡、PCIe 转 SATA 转接卡、网卡；双千兆以太网接口；板载 WI-FI6/BT5.2 模组；支持 NVMe SSD，是入门级 RISC-V Desktop 首选。

开发板介绍文档 (Milv-V Docs)：[Milk-V Jupiter](https://wiki.banana-pi.org/Milk-V_Jupiter)

开发板应用方向：
- NAS
- 桌面电脑
- 工业控制
- 人工智能边缘计算

## Demo简介

进迭时空官方ModelZoo 测试结果矩阵：[ModelZoo](https://developer.spacemit.com/documentation?token=RMBiwlSmAiiguxkrJKWcox9In91)

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

> 由于模型文件较大，建议在RAM大于8GB的型号上运行该demo。

安装chatglm推理工具

```shell
sudo apt-get update
sudo apt-get install inferllm-toolkit
```


> TODO: 运行命令待补充


### Demo运行总结

#### sdk 集成说明

> 给出需要 ruyisdk 集成建议或者总结; -->

<!-- <!-- #### 问题及状态 -->

> 问题描述或者问题issue链接；用于跟踪/推动问题解决；