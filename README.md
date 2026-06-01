
# Repeater

一个用于学习 C# 音频处理与模拟输入的工具。支持播放指定音频并通过虚拟音频设备模拟麦克风输入，附带消息轰炸（键盘模拟）功能。

> **⚠️ 仅供技术研究**  
> 本工具仅用于学习 NAudio、虚拟音频路由、键盘模拟等底层技术。请勿在违反游戏规则或服务条款的环境中使用，滥用可能导致账号封禁或其它法律风险。

## 功能特性

- 🎵 **音频播放** – 使用 NAudio 播放 WAV/MP3 等音频文件
- 🎤 **模拟麦克风** – 通过 VB-Cable 虚拟音频设备将播放的音频直接送入游戏/软件的麦克风输入
- ⌨️ **消息轰炸** – 模拟键盘输入，支持重复发送自定义文本（带回车）
- 🔁 **循环/次数控制** – 可设置音频播放次数或无限循环
- 🧩 **简单 WinForms UI** – 按钮、文本框、设备选择下拉框，开箱即用

## 系统要求

- Windows 10 / 11（64 位）
- [.NET 8.0 运行时](https://dotnet.microsoft.com/download/dotnet/8.0)
- 虚拟音频设备驱动：**[VB-Cable Virtual Audio Cable](https://vb-audio.com/Cable/)**（免费）

## 安装与使用

### 1. 安装依赖驱动
下载并安装 [VB-Cable](https://vb-audio.com/Cable/)，重启电脑后会在声音设置中出现新的播放/录音设备：
- 播放设备：`CABLE Input (VB-Audio Virtual Cable)`
- 录音设备：`CABLE Output (VB-Audio Virtual Cable)`

### 2. 编译与运行
```bash
git clone https://github.com/你的用户名/repeater.git
cd repeater
dotnet build
dotnet run
```

或者直接用 Visual Studio 2022 打开 Repeater.sln 编译运行。

3. 使用步骤

1. 选择音频文件 – 点击“浏览”，选择狗叫或其它声音文件
2. 选择输出设备 – 在下拉框中选择 CABLE Input (VB-Audio Virtual Cable)
3. 设置重复次数 – 输入数字（0 表示无限循环）
4. 点击“播放” – 音频会从虚拟设备输出
5. 在目标软件中 – 将麦克风设置为 CABLE Output (VB-Audio Virtual Cable)
6. 消息轰炸（可选） – 输入要重复的文本、次数及间隔（毫秒），点击“开始轰炸”

项目结构

```
Repeater/
├── Repeater.csproj      // .NET 8.0 + WinForms 项目文件
├── Program.cs           // 应用程序入口
├── MainForm.cs          // 主窗体逻辑
├── AudioPlayer.cs       // NAudio 封装（设备选择、播放控制）
├── KeyboardSimulator.cs // 键盘模拟（使用 InputSimulator）
└── README.md
```

使用的 NuGet 包

包名 用途
NAudio 音频播放与设备枚举
InputSimulatorCore 模拟键盘按键和文本输入

许可证

本项目基于 GPLv3 开源协议发布。详情请见 LICENSE 文件。

免责声明

本软件仅用于学习和研究计算机音频处理、模拟输入技术。使用者必须遵守目标软件的用户协议和相关法律法规。作者不对因使用本软件造成的任何损失或封号行为负责。

---

如果你遇到真·狗对手，建议用真·狗叫去对线 🐶
