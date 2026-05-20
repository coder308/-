# -
用来检测你是否处于分心状态，主要通过MediaPipe Face Mash 的468关键点人脸模型来进行判断是否处于低头看手机状态，触发后会在电脑显示提醒，在手机上通过钉钉机器人提醒
# Distraction Detection 👀

基于 **MediaPipe Face Mesh (468点)** 的课堂/办公分心检测系统。
检测到低头（玩手机）或无人时，自动弹窗提醒并发送钉钉通知。

## 功能

- ✅ **人脸检测** — MediaPipe Face Mesh (468个面部关键点)
- ✅ **低头判断** — 额头占比 > 鼻子到下巴1.5倍 = 低头
- ✅ **人走开提醒** — 连续5秒没人脸触发报警
- ✅ **弹窗提醒** — 分心时弹出警告图 + 播放提示音
- ✅ **截屏保存** — 自动保存分心时刻的画面
- ✅ **钉钉通知** — 通过钉钉机器人发送到手机（可选）

## 快速开始 (60秒)

```bash
# 1. 克隆仓库
git clone https://github.com/你的名字/distraction-detection.git
cd distraction-detection

# 2. 一键安装（自动下载模型、生成提示图）
chmod +x setup.sh && ./setup.sh

# 3. 运行
python3 main.py
```

## 依赖

- Python 3.7+
- OpenCV
- MediaPipe
- Ultralytics YOLOv8
- 摄像头（USB 或 内置）

## 配置

修改 `config.py` 即可自定义：
- `DINGTALK_WEBHOOK` — 钉钉机器人地址（不需要就留空）
- `WARNING_IMAGE_PATH` — 提示图片路径
- `WARNING_SOUND_PATH` — 提示音路径
- `CAMERA_ID` — 摄像头ID

## 退出

- 按键盘 **Q** 或点界面 **Quit 按钮**

## 目录结构

```
distraction-detection/
├── main.py          # 主程序
├── ai_analyzer.py   # AI推理（MediaPipe人脸检测+低头判断）
├── alert.py         # 弹窗/声音/钉钉提醒
├── camera.py        # 摄像头
├── ui.py            # 界面
├── notifier.py      # 钉钉通知
├── config.py        # 配置
├── setup.sh         # 一键安装脚本
├── requirements.txt # Python依赖
├── models/          # AI模型（自动下载）
├── assets/          # 提示资源
└── captures/        # 分心截图保存
```
