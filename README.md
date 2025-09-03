# 🐦 鸟类鸣叫声识别系统

> **项目灵感**：源于对环境保护的热情以及人工智能技术的快速发展，本项目旨在利用深度学习对鸟类鸣叫声进行自动识别和分类，为生态保护和科研提供技术支持。  
> **开发周期**：历时约一年完成。

---

## 📖 项目简介
本项目通过对鸟类音频数据进行特征提取和深度学习建模，实现对 **27 种鸟类** 的鸣叫声高精度识别。项目借鉴了 **BirdCLEF 国际竞赛** 的研究思路，针对真实录音中背景噪声复杂、类别不均衡、多物种同时鸣叫等挑战提出优化方案，最终实现模型在测试集上的 **87% 准确率**。

**亮点：**
- 🎯 测试集整体准确率：**87%**
- 🏅 11 种鸟类 F1-score 超过 **90%**
- 🔍 支持多标签、多物种识别，鲁棒性强
- 📚 提供完整的训练、验证、推理代码及文档

---

## ✨ 功能特点
- 🎙️ **音频预处理**：统一采样率、Mel 频谱图转换、高通滤波去除低频噪声  
- 🧠 **深度学习建模**：基于 EfficientNetB3 的迁移学习模型  
- 🛠️ **数据增强**：多种图像级增强策略缓解过拟合和长尾问题  
- 📊 **模型评估**：支持准确率和 F1-score 可视化  
- 🚀 **可扩展性强**：代码可直接迁移至其他声学分类任务

---

## 🔧 技术栈
| 类型               | 技术 / 工具                                  |
|--------------------|-------------------------------------------|
| **语言**           | Python 3.8+                              |
| **深度学习框架**   | TensorFlow , Keras                     |
| **音频处理**       | Librosa                                   |
| **模型架构**       | EfficientNetB3, Adam 优化器              |
| **数据增强**       | ImageDataGenerator（平移、缩放、剪切等） |
| **类别不平衡处理** | class_weight 自动权重分配                |
| **硬件支持**       | NVIDIA GPU (建议)                        |

---

## 📂 项目结构
├── data/                 # 数据集目录 (train/val/test)
├── notebooks/            # Jupyter Notebook 代码
├── models/               # 模型权重文件
├── src/                  # 源码
│   ├── preprocess.py     # 音频预处理脚本
│   ├── train.py          # 模型训练脚本
│   ├── evaluate.py       # 模型评估脚本
│   └── utils.py          # 工具函数
├── references/           # 相关论文和资料
├── reports/              # 实验结果与分析
├── images/               # 图片 (频谱图等)
├── requirements.txt      # 依赖包列表
└── README.md             # 项目说明文件
---

## ⚙️ 快速开始

### 1. 克隆仓库
```bash
git clone https://github.com/ZFD-040109/Bird-Voice-Recognition-System.git
cd Bird-Voice-Recognition-System

2. 安装依赖
pip install -r requirements.txt

3. 准备数据
	•	下载 Xeno-Canto 或 BirdCLEF 鸟类音频数据
	•	按以下结构组织：
data/
├── train/
├── val/
└── test/

4. 训练模型
python src/train.py --epochs 30 --batch_size 16

5. 模型评估
python src/evaluate.py --model_path models/efficientnet_checkpoint.h5

📊 实验结果
指标                     数值
整体准确率                87%
F1-score > 90% 的类别    11 类
F1-score 70-90% 的类别   8 类
F1-score < 50% 的类别    6 类

模型在噪声环境和多物种录音中表现稳定，可支持生态监测和科研应用。

⸻

🛠️ 后续优化计划（暂时不更新了，要准备考研了，最新版更新到2023.7）
	•	引入 Mixup、SpecAugmentation 等专用音频增强
	•	探索 PANN、ResNeSt 等更强模型
	•	开发 Web / 移动端在线识别工具
	•	增加可视化界面和演示 Demo
⸻

📝 开源协议

本项目基于 MIT License 开源。

⸻

🤝 致谢
	•	鸟类音频数据来源于 Xeno-Canto
	•	项目开发参考了国际竞赛解决方案
	•	特别感谢开源社区提供的深度学习和音频处理工具
	• 特别感谢一位资深程序员家人的指导

