# 🎛️ Chromatic Glitch — 创意音频效果插件

[English](README.md) | [简体中文](README_zh.md) | [快速上手指南 (激活说明)](#快速上手指南-激活说明)

<p align="center">
  <strong>一款专为故障音效、声码器和失真处理设计的创意音频效果插件。</strong><br>
  A creative audio effect plugin for glitch, vocoder, and distortion processing.<br>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-macOS-black?style=for-the-badge&logo=apple" alt="macOS">
  <img src="https://img.shields.io/badge/Format-VST3%20%7C%20AU-blue?style=for-the-badge" alt="Formats">
  <img src="https://img.shields.io/badge/Framework-JUCE%208-green?style=for-the-badge" alt="JUCE 8">
</p>

**Chromatic Glitch** 是由 **Vox — Zonic Design Production** 独家研发的专业音频插件。它将三大强力引擎整合为一个极具凝聚力的声音设计工具包：基于缓冲区的故障（Glitch）引擎、32 频段通道声码器，以及多算法失真处理单元。

如果您需要一个能实时粉碎并重构音频、用来掌控音乐中混乱元素的强力乐器，这就是您的最佳选择。

[访问官网 & 下载试用版](https://chromatic-glitch-web.vercel.app) · [报告问题](mailto:legal@zonicdesign.com)

---

## 核心特性

- **故障引擎 (Glitch Engine)** — 基于缓冲的断续 (Stutter)、反转 (Reverse) 和半速磁带 (Half-Speed) 效果，与您的 DAW 速度完美同步。
- **声码器/梳状引擎 (Vocoder/Comb)** — 在原始的 32 频段纯粹通道声码器和密集、共振的梳状滤波器组之间无缝渐变。
- **失真算法 (Distortion)** — 提供 8 种独特的驱动电路，范围从温暖的电子管染色到极其残酷的数字位深破碎 (Bitcrushing)。
- **聚焦均衡架构 (Focus EQ)** — 精准隔离您想要破坏的独立频段，同时不影响混音中其他元素的清晰度。
- **硬件安全绑定** — 采用高级的 RSA-2048 密码学级别的加密机制，将您的许可证与您的专属工作室运算环境紧密绑定。

---

## 信号路由

本插件采用了独特的 "Focus EQ"（聚焦均衡）架构，允许您将极端效果专门施加于某一个特定频段，同时保留其它原有的纯净信号（干声）。

```mermaid
graph TD
    In[Audio Input 音频输入] --> IG[Input Gain 输入增益]
    IG --> Split{Focus EQ Split 分频点?}
    Split -- 启用 (Enabled) --> Focus[Focus Band 聚焦频段]
    Split -- 启用 (Enabled) --> Bypass[Bypass Band 旁通频段]
    Split -- 禁用 (Disabled) --> Focus[Full Signal 完整信号]
    
    subgraph "处理链 Processing Chain (仅限聚焦部分)"
        Focus --> GE[故障引擎 Glitch Engine]
        GE --> VE[声码器 Vocoder / 梳状 Comb]
        VE --> DIST[失真 Distortion]
    end
    
    DIST --> Sum[Summing Mixer 混合总线]
    Bypass --> Sum
    Sum --> OG[Output Level 输出电平]
    OG --> Out[Audio Output 音频输出]
```

## 控制指南 (Control Guide)

### 输入部分 (Input Section)

- **INPUT**: 控制进入处理链之前的输入信号电平。
- **FOCUS EQ (按钮)**: 激活频率分频模式。
- **FREQ**: 设置聚焦频段的中心频率。
- **WIDTH (Q)**: 设置聚焦频段的带宽或共振程度。

### 故障引擎 (Glitch Engine)

- **MODE (模式)**: 包含 `Stutter` (重复断续切碎)，`Reverse` (反向播放缓冲区)，`Half-Speed` (类似磁带减速的效果)。
- **RATE**: 故障效果的播放速度。
- **MIX**: 控制故障引擎的干湿混合比例。
- **BPM SYNC**: 将效果速度与您的宿主 DAW 速度同步。

### 颜色 / 声码器引擎 (Color / Vocoder)

- **ENGINE MODE (引擎模式)**: 在 **Comb Bank (梳状滤波器组)** 和 **32-Band Vocoder (32 频段声码器)** 之间切换。
- **COLOR / MORPH**: 控制滤波器的共振（梳状模式中）或声码器频段的清晰度与亮度（声码器模式中）。
- **ATTACK / RELEASE**: 为声码器包络跟随器设置反应速度。
- **SHIFT**: 偏移频段，从而得到类似共振峰偏移的人声发音改变效果。
- **CARRIER / MOD / NOISE**: 为声码器内部构件提供的独立混合比例控制。

### 输出部分 (Output Section)

- **DRIVE ALGORITHM**: 8 种失真模式，包含软饱和 (Soft Sat)、位宽破碎 (Bitcrush) 以及锗二极管法兹 (Germanium Fuzz) 等。
- **DRIVE**: 控制失真的饱和或破坏强度。
- **OUTPUT**: 最终输出的总音量控制。

---

## 快速上手指南 (激活说明)

1. 打开您的 DAW，并将 **Chromatic Glitch** 加载到任一轨道上。
2. 插件的用户界面将显示一个独一无二的 **Machine ID (机器码)**，该 ID 基于您的硬件信息生成。
3. 点击界面右上角的 **REGISTER (注册)** 按钮。
4. 将该 Machine ID 发送给开发者，或者在激活平台使用它获取您的专属 `Activation Code (激活码)`。
5. 将得到的激活码粘贴回插件窗口中，即可成功解锁完整版本。

> **隐私保护声明：** 您的 Machine ID 是纯基于硬件配置生成的数学哈希值。它不包含您的任何个人数据或隐私信息。您可以绝对安全地分享此 ID 进行激活。

### 试用版限制说明 (Demo Restrictions)

在尚未激活前，插件将在功能受限的试用模式 (Demo Mode) 下运行：

- **故障模式**: 被永久锁定为 "Stutter"。
- **失真模式**: 被限制为仅能使用 Soft Sat, Wavefold, 和 Germanium 三种。
- **声码器**: 部分核心参数无法调节。
- **用户界面**: 界面上会覆盖一层试用版专属的半透明水印。

---

## 许可及安全声明

Chromatic Glitch 是由 **Vox — Zonic Design Production** 研发与持有的专有商业软件。

> **⚠️ 警告：软件盗版是严重的违法行为。**
>
> Chromatic Glitch 使用了高强度的 **RSA-2048 硬件级别锁定防御授权**系统。您的每一份正版拷贝都已与您的创作硬件实现了深度关联与唯一锁定。
> 任何意图破解、打补丁修改、绕过或试图规避此激活系统的行为，均直接违反各有关知识产权保护保护法（包括不限于 **DMCA** 与 **CFAA**）。
>
> **Zonic Design Production 坚决维护自身合法权益，并将积极寻求一切可用的法律救济措施**，其中包括对每次侵权行为最高索要 **150,000 美元** 的法定损害赔偿 (依据 17 U.S.C. § 504)。任何分发破解版本的个人或团体，不仅自身触法，还将在法律上承受严重的“共同侵权与替代侵权责任”。

如果您在互联网发现任何未经授权的拷贝分发，或是发现授权系统内的安全漏洞，恳请您向我们在法律与安全层面的邮箱负责人进行负责任的披露与举报：**<security@zonicdesign.com>**

## 致谢 / Credits

- **开发者 (Developer)**: Vox — Zonic Design Production
- **UI 框架 (Framework)**: [JUCE](https://juce.com)
- **核心音频算法 (Audio DSP)**: 定制化的 C++ 矩阵算法实现

*© 2026 Vox — Zonic Design Production. 保留所有权利。严禁一切未经授权的翻录、逆向或重新分发。*
