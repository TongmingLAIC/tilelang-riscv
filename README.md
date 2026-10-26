# TileLang for RISC-V

**围绕 TileLang 与 RISC-V 计算生态的开源协作社区。**

[社区项目](#社区项目) · [快速开始](#快速开始) · [参与贡献](#参与贡献) · [相关资源](#相关资源)

## 关于社区

**TileLang for RISC-V** 致力于推动 TileLang 在 RISC-V 计算平台与 AI 加速器上的应用，汇集编译器适配、算子开发、性能优化和开发工具等方向的开源工作。

我们希望以 TileLang 的算子编程抽象为基础，积累可复用的编译技术、可验证的算子实现和可复现的实验经验，降低高性能算子开发与硬件适配的门槛。

本仓库是社区的统一入口，用于介绍社区项目、汇总技术资料和提供参与指引。各项目的源代码、安装方法、支持范围与开发进展，请查看对应仓库。

## 社区项目

| 项目 | 简介 | 当前重点平台 | 项目入口 |
| --- | --- | --- | --- |
| **TileLang-TPU** | 面向 SOPHGO TPU 的 TileLang 扩展，提供 TPU 编译、代码生成与 JIT 运行集成 | SOPHGO BM1690 | [源码与说明](https://github.com/TongmingLAIC/tilelang-tpu) · [算子示例](https://github.com/TongmingLAIC/tilelang-tpu/tree/main/tpu_demo) |

### TileLang-TPU

[**TileLang-TPU**](https://github.com/TongmingLAIC/tilelang-tpu) 面向算能（SOPHGO）AI 加速器，在保留 TileLang Python DSL 的基础上，增加 TPU 后端的编译转换、代码生成和 JIT 支持，将 TileLang 算子连接到 TPU 编译与执行流程。

项目当前主线聚焦 **BM1690**，主要内容包括：

- **TPU 编译目标**：通过 `target="tpu"` 接入 TPU 后端。
- **JIT 运行集成**：衔接 Python 算子定义、生成代码以及主机端与设备端运行组件。
- **硬件执行与仿真**：提供 `mode="pcie"` 和 `mode="cmodel"` 两种执行路径。
- **TPU 算子原语**：提供数据搬运、矩阵乘法、归约等 TPU 相关 DSL 原语。
- **算子示例**：包括 Matmul、RMSNorm、RoPE、Reduce、SwiGLU 和 FlashAttention 等。

支持范围、依赖版本及各示例的运行条件，以项目当前文档为准。

**项目导航：**

- [项目介绍与安装入口](https://github.com/TongmingLAIC/tilelang-tpu#readme)
- [环境配置说明](https://github.com/TongmingLAIC/tilelang-tpu/blob/main/tpu_demo/instruction.md)
- [算子示例目录](https://github.com/TongmingLAIC/tilelang-tpu/tree/main/tpu_demo)
- [问题反馈与功能建议](https://github.com/TongmingLAIC/tilelang-tpu/issues)
- [代码贡献与 Pull Requests](https://github.com/TongmingLAIC/tilelang-tpu/pulls)

## 关注方向

社区围绕以下方向开展交流与协作，欢迎提出新的需求、方案和项目：

| 方向 | 关注内容 |
| --- | --- |
| **编译器与后端适配** | TileLang 面向 RISC-V 计算平台与 AI 加速器的编译转换、代码生成和运行时集成 |
| **算子开发与优化** | 矩阵乘法、注意力、归一化等算子的实现，以及数据搬运、内存布局和计算调度优化 |
| **测试与性能分析** | 正确性验证、性能测量、瓶颈分析和可复现的基准测试 |
| **开发工具与文档** | 环境配置、调试工具、示例程序、教程和技术实践分享 |

以上是社区的协作方向；具体功能的实现状态与硬件支持范围，由各项目分别说明。

## 快速开始

### 我想了解社区

阅读本页的项目介绍，选择感兴趣的项目，了解其目标平台、技术路线和当前进展。

### 我想运行一个示例

从 [TileLang-TPU](https://github.com/TongmingLAIC/tilelang-tpu#readme) 开始：

1. 阅读项目 README，确认硬件或仿真环境及工具链要求。
2. 按项目文档完成环境配置与安装。
3. 在 [算子示例目录](https://github.com/TongmingLAIC/tilelang-tpu/tree/main/tpu_demo) 中选择与当前环境匹配的示例。
4. 记录运行环境、代码版本与执行结果，便于复现和交流。

### 我想参与开发

浏览项目已有的 Issue 与 Pull Request，了解正在讨论的问题。对于涉及接口、编译流程或硬件支持的较大改动，建议先提交 Issue 讨论设计方案。

## 参与贡献

欢迎对 TileLang、RISC-V、编译器、AI 算子和系统软件感兴趣的开发者、研究人员与硬件团队参与。

你可以通过以下方式贡献：

- **开发与优化**：参与后端适配、算子实现、功能改进和问题修复。
- **测试与反馈**：提供环境适配经验、问题复现步骤、正确性测试或性能测试结果。
- **文档与示例**：完善安装说明、补充教程、整理开发笔记和可运行示例。
- **项目与交流**：介绍与社区主题相关的开源项目，分享技术方案与实践经验。

### 在哪里提交？

- **具体项目的问题与代码贡献**：提交到对应项目的 Issue 或 Pull Request。
- **社区介绍、项目索引与公共资料的修改**：在本仓库提交 Issue 或 Pull Request。
- **推荐新项目**：在本仓库提交 Issue，说明项目链接、目标平台、主要功能，以及与社区主题的关联。

反馈运行问题时，建议附上代码版本、硬件或仿真配置、工具链版本、复现命令和关键日志。分享性能结果时，请同时说明输入规模、数据类型、测量方法与对比基线。

## 相关资源

- [TongmingLAIC GitHub 组织](https://github.com/TongmingLAIC)
- [TileLang 上游项目](https://github.com/tile-ai/tilelang)
- [TileLang-TPU 项目](https://github.com/TongmingLAIC/tilelang-tpu)
- [SOPHGO PPL 项目](https://github.com/sophgo/PPL)

## 开源许可

各项目的许可证以对应仓库中的许可文件为准。