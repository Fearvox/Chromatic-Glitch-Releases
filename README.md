# Chromatic Glitch

<p align="center">
  <strong>A creative audio effect plugin for glitch, vocoder, and distortion processing.</strong><br>
  一款专为故障音效、声码器和失真处理设计的创意音频效果插件。<br><br>
  <em>Built with JUCE 8 | VST3 & AU | macOS</em><br>
  <em>由 Vox — Zonic Design Production 开发</em>
</p>

---

## Overview / 概述

Chromatic Glitch is a professional audio plugin combining three powerful engines:
Chromatic Glitch 是一款专业音频插件，结合三大强力引擎：

- **Glitch Engine / 故障引擎** — Buffer-based stutter, reverse, and half-speed effects with BPM sync / 基于缓冲的断续、反转和半速效果，支持 BPM 同步
- **Vocoder/Comb Engine / 声码器/梳状引擎** — 32-band channel vocoder and comb filter bank / 32 频段通道声码器和梳状滤波器组
- **Distortion / 失真** — 8 unique modes from tape saturation to germanium fuzz / 8 种独特模式，从磁带饱和到锗二极管失真
- **Sidechain Input / 侧链输入** — Use external audio as a carrier for the vocoder to achieve "colorbass" pitch mapping / 使用外部音频作为声码器载波，实现“colorbass”音高映射

## Feature Focus: Sidechain Vocoding / 特色功能：侧链声码器

Chromatic Glitch supports an external sidechain input for the Vocoder engine.
Chromatic Glitch 的声码器引擎支持外部侧链输入。

1. **Route Audio**: Send a MIDI-triggered chord synth or any melodic source to the plugin's "Sidechain" input.
   **路由音频**：将 MIDI 触发的和弦合成器或任何旋律源发送至插件的“侧链”输入。
2. **Switch Mode**: Set the plugin to **Vocoder** mode.
   **切换模式**：将插件设置为 **Vocoder** 模式。
3. **Enjoy Colorbass**: The sidechain signal will act as the carrier, while your main track acts as the modulator.
   **尽享 Colorbass**：侧链信号将作为载波，而您的主轨道将作为调制器。

## Building from Source / 从源码构建

```bash
mkdir cmake-build-debug && cd cmake-build-debug
cmake .. -DCMAKE_BUILD_TYPE=Debug
cmake --build . -j $(sysctl -n hw.logicalcpu)
```

The plugin will be automatically installed to your system's plugin directories.
插件将自动安装到系统的插件目录中。

## License / 许可协议

Chromatic Glitch is proprietary software developed by **Vox — Zonic Design Production**.
Chromatic Glitch 是由 **Vox — Zonic Design Production** 开发的专有软件。

### Terms of Use / 使用条款

1. **Single-Machine License / 单机授权**: Each license is tied to one hardware device via a unique Machine ID. / 每个许可证通过唯一机器 ID 绑定至一台硬件设备。
2. **Non-Transferable / 不可转让**: Licenses may not be transferred, shared, sold, or sublicensed. / 许可证不得转让、共享、出售或再授权。
3. **No Modification / 禁止修改**: Reverse engineering, decompilation, disassembly, or any attempt to derive the source code is strictly prohibited. / 严禁逆向工程、反编译、反汇编或任何试图推导源代码的行为。
4. **No Redistribution / 禁止再分发**: You may not distribute the plugin binary, license files, or activation codes to any third party. / 不得向任何第三方分发插件二进制文件、许可文件或激活码。

### Anti-Piracy Statement / 反盗版声明

> **⚠️ WARNING: Software piracy is a serious crime. / 警告：软件盗版是严重的违法行为。**
>
> Chromatic Glitch uses **RSA-2048 cryptographic hardware-locked licensing**. Each copy is uniquely tied to the user's machine.
>
> Chromatic Glitch 使用 **RSA-2048 加密硬件锁定授权**。每份副本都唯一绑定到用户的机器。
>
> **Any attempt to crack, patch, bypass, or circumvent the activation system constitutes a violation of:**
>
> **任何试图破解、补丁、绕过或规避激活系统的行为均违反以下法律：**
>
> - The **Digital Millennium Copyright Act (DMCA)** (17 U.S.C. § 1201) / 《数字千年版权法》
> - The **Computer Fraud and Abuse Act (CFAA)** (18 U.S.C. § 1030) / 《计算机欺诈和滥用法》
> - The **EU Copyright Directive** (Article 6 & 7) / 《欧盟版权指令》第 6 和第 7 条
> - Applicable local copyright and intellectual property laws / 适用的当地版权和知识产权法律
>
> **Zonic Design Production will actively pursue all legal remedies available**, including but not limited to:
>
> **Zonic Design Production 将积极追究所有可用的法律救济**，包括但不限于：
>
> - Filing DMCA takedown requests / 提交 DMCA 下架请求
> - Pursuing civil damages for copyright infringement / 追究版权侵权民事赔偿
> - Reporting criminal violations to law enforcement / 向执法机构举报刑事违法行为
> - Seeking statutory damages up to **$150,000 per infringement** (17 U.S.C. § 504) / 寻求每次侵权最高 **$150,000** 的法定赔偿
>
> **Distributing cracked copies exposes the distributor to contributory and vicarious copyright infringement liability.**
>
> **分发破解副本将使分发者承担共同侵权和替代侵权责任。**
>
> If you discover unauthorized copies, please report to: **<legal@zonicdesign.com>**
>
> 如发现未经授权的副本，请举报至：**<legal@zonicdesign.com>**

### Responsible Disclosure / 负责任的信息披露

If you discover a security vulnerability in the licensing system, please contact **<security@zonicdesign.com>** before disclosing publicly.

如果您发现授权系统中的安全漏洞，请在公开披露之前联系 **<security@zonicdesign.com>**。

## Credits / 致谢

- **Developer / 开发者**: Vox — Zonic Design Production
- **Framework / 框架**: [JUCE](https://juce.com) (GPLv3 / Commercial)
- **Audio DSP / 音频 DSP**: Custom implementations / 自定义实现

---

*© 2026 Vox — Zonic Design Production. All rights reserved. Unauthorized reproduction or distribution is prohibited by law.*

*© 2026 Vox — Zonic Design Production. 版权所有。未经授权的复制或分发均属违法行为。*
