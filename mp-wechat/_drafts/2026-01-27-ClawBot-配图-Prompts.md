# ClawBot文章配图Prompt指南

## 配图策略：风格A+B组合

**风格A：拆解者风格（Tech Breakdown）**
- 深色科技感 + 3D可视化 + 拆解元素（无人物）
- 适用：封面、概念解释、对比分析
- 占比：40%（2-3张）

**风格B：图解说明风（Visual Guide）**
- 白底 + 卡片式布局 + 流程图表（无人物）
- 适用：流程步骤、工具推荐、总结回顾
- 占比：60%（3-5张）

## 配图清单（共6张）

### 配图1：封面图 - 风格A

**位置**：文章首图
**作用**：吸引点击，建立品牌识别

#### 图片描述（中文）
深色科技感封面图，展示ClawBot作为AI管家的概念。中央是发光的ClawBot图标，周围环绕多个消息平台图标（WhatsApp、Telegram、Slack等），用发光线条连接，形成网络状结构。背景是深蓝色渐变，有微妙的网格纹理。

**使用风格**：风格A
**场景模板**：A1-概念封面

#### Prompt Version 1 (豆包通用版)
```
深色科技感封面图，ClawBot AI管家概念。中央是发光的机器人图标，周围环绕WhatsApp、Telegram、Slack等消息平台图标，用发光线条连接成网络。深蓝色渐变背景，有网格纹理。科技感、未来感、无人物。
```

#### Prompt Version 2 (豆包细节版)
```
深色科技感封面图，ClawBot个人AI助手。中央是发光的蓝色机器人图标，周围环绕6个消息平台图标：WhatsApp绿色、Telegram蓝色、Slack紫色、Discord紫色、Signal绿色、iMessage蓝色。用发光线连接成星形网络。深蓝色到黑色渐变背景，有微妙的网格纹理。3D立体效果，光线追踪渲染。无人物元素，纯图标化设计。
```

#### Prompt Version 3 (Midjourney版)
```
tech breakdown style, dark blue gradient background with grid texture, glowing ClawBot AI assistant icon in center, surrounded by messaging app icons (WhatsApp, Telegram, Slack, Discord, Signal, iMessage) connected by glowing lines forming network pattern, 3D illustration, cinematic lighting, no people --ar 16:9 --style raw --v 6
```

#### 建议尺寸
- 横版：1200x675 (16:9)

#### 备选方案
如果AI生成效果不好，可从Unsplash搜索"dark tech background"或"AI assistant concept"

---

### 配图2：多平台统一管理 - 风格A

**位置**：多平台管理章节
**作用**：可视化多平台统一管理概念

#### 图片描述（中文）
多个消息平台图标整合到一个统一的收件箱中。左侧是分散的多个App图标，右侧是统一的收件箱界面，中间用箭头表示整合过程。深色背景，有数据流动的视觉效果。

**使用风格**：风格A
**场景模板**：A2-概念对比

#### Prompt Version 1 (豆包通用版)
```
多平台统一管理概念图。左侧分散的多个消息App图标，右侧统一的收件箱界面，中间箭头表示整合。深色背景，数据流动效果。科技感、无人物。
```

#### Prompt Version 2 (豆包细节版)
```
多平台消息统一管理概念图。左侧：6个分散的消息App图标（WhatsApp、Telegram、Slack、Discord、Signal、iMessage），每个图标有消息数量提示。右侧：统一的收件箱界面，简洁设计，有消息分类标签。中间：蓝色箭头表示整合过程，有数据流动的粒子效果。深蓝到黑色渐变背景，有微妙的电路板纹理。无人物元素。
```

#### Prompt Version 3 (Midjourney版)
```
tech breakdown style, multiple messaging app icons (WhatsApp, Telegram, Slack, Discord, Signal, iMessage) on left side, unified inbox interface on right side, blue arrows showing integration process with data flow particles, dark blue gradient background with circuit board texture, 3D illustration, no people --ar 16:9 --style raw --v 6
```

#### 建议尺寸
- 横版：1200x675 (16:9)

---

### 配图3：本地vs云端对比 - 风格B

**位置**：技术对比章节
**作用**：清晰展示本地存储与云端存储的区别

#### 图片描述（中文）
白底对比图，左侧云端存储示意图（数据发到远程服务器），右侧本地存储示意图（数据留在用户设备）。用简单的图标和箭头清晰展示区别。

**使用风格**：风格B
**场景模板**：B1-对比图解

#### Prompt Version 1 (豆包通用版)
```
白底对比图，云端存储vs本地存储。左侧：数据发到远程服务器。右侧：数据留在用户设备。简洁图标和箭头说明区别。清晰易懂。
```

#### Prompt Version 2 (豆包细节版)
```
白底对比图解，云端AI助手vs本地AI助手。左侧：手机图标，数据通过云朵图标发到远程服务器，标注"云端存储"。右侧：手机图标，数据停留在设备内部，标注"本地存储"。用红色叉号表示隐私风险，绿色对号表示安全。简洁的扁平化设计，信息图表风格。
```

#### Prompt Version 3 (Midjourney版)
```
infographic style, white background, comparison between cloud storage vs local storage, left side: data sent to remote server with cloud icon, right side: data stays on user device, simple icons and arrows, clean minimalist design, information chart, no people --ar 16:9 --style raw --v 6
```

#### 建议尺寸
- 横版：1200x675 (16:9)

---

### 配图4：Gateway架构流程图 - 风格B

**位置**：技术架构章节
**作用**：可视化Gateway工作流程

#### 图片描述（中文）
Gateway架构流程图，展示消息从进入到最后回复的完整流程。6个步骤清晰标注，用箭头连接。白底蓝线，信息图表风格。

**使用风格**：风格B
**场景模板**：B2-流程步骤

#### Prompt Version 1 (豆包通用版)
```
Gateway架构流程图。消息进入→Gateway接收→分析意图→调用工具→生成回复→发送回复。6步流程，箭头连接。白底蓝线，信息图表。
```

#### Prompt Version 2 (豆包细节版)
```
Gateway架构流程图，展示ClawBot工作流程。6个步骤：1.消息进入（WhatsApp/Telegram图标）→2.Gateway接收（服务器图标）→3.分析意图（大脑图标）→4.调用工具（工具图标）→5.生成回复（AI图标）→6.发送回复（发送图标）。每个步骤有简短说明。蓝色线条连接，白底背景，信息图表风格。简洁专业。
```

#### Prompt Version 3 (Midjourney版)
```
infographic style, white background, Gateway architecture workflow diagram, 6 steps: message entry → Gateway reception → intent analysis → tool calling → response generation → reply sending, blue connecting arrows, minimalist icons for each step, clean information chart, no people --ar 16:9 --style raw --v 6
```

#### 建议尺寸
- 横版：1200x675 (16:9)

---

### 配图5：安装步骤图解 - 风格B

**位置**：使用指南章节
**作用**：指导用户安装配置

#### 图片描述（中文）
安装步骤图解，4个步骤：环境准备→安装配置→平台连接→高级功能。每个步骤用图标和简短说明展示。

**使用风格**：风格B
**场景模板**：B3-步骤指南

#### Prompt Version 1 (豆包通用版)
```
安装步骤图解。4个步骤：环境准备、安装配置、平台连接、高级功能。每个步骤有图标和说明。白底，简洁明了。
```

#### Prompt Version 2 (豆包细节版)
```
ClawBot安装步骤图解。4个步骤：1.环境准备（系统要求图标）→2.安装配置（命令行图标）→3.平台连接（配对码图标）→4.高级功能（设置图标）。每个步骤有简短说明和预计时间。白底蓝标，步骤清晰，新手友好。
```

#### Prompt Version 3 (Midjourney版)
```
infographic style, white background, ClawBot installation steps diagram, 4 steps: environment preparation → installation configuration → platform connection → advanced features, simple icons for each step, clean step-by-step guide, no people --ar 16:9 --style raw --v 6
```

#### 建议尺寸
- 横版：1200x675 (16:9)

---

### 配图6：总结对比表 - 风格B

**位置**：总结章节
**作用**：一图看懂ClawBot优势

#### 图片描述（中文）
总结对比表，展示ClawBot vs 其他AI助手的优势。表格形式，重点突出ClawBot的独特价值。白底，信息图表风格。

**使用风格**：风格B
**场景模板**：B4-总结回顾

#### Prompt Version 1 (豆包通用版)
```
总结对比表，ClawBot vs 其他AI助手。表格形式，突出隐私、多平台、离线等优势。白底，清晰易读。
```

#### Prompt Version 2 (豆包细节版)
```
ClawBot优势总结对比表。对比维度：数据隐私、多平台支持、离线使用、开源透明、自定义程度、成本。ClawBot在关键维度有突出优势标记（对号、高亮）。表格形式，白底蓝标，信息图表风格。一图看懂核心价值。
```

#### Prompt Version 3 (Midjourney版)
```
infographic style, white background, comparison table showing ClawBot advantages vs other AI assistants, key dimensions: data privacy, multi-platform support, offline usage, open source, customization, cost, clear highlighting of ClawBot strengths, clean table design, no people --ar 16:9 --style raw --v 6
```

#### 建议尺寸
- 横版：1200x675 (16:9)

---

## 配图使用建议

### 图片文件夹结构
```
images/clawbot-article/
├── cover-style-a.png          # 配图1
├── multi-platform-style-a.png  # 配图2
├── comparison-style-b.png      # 配图3
├── gateway-flow-style-b.png    # 配图4
├── installation-style-b.png    # 配图5
└── summary-style-b.png         # 配图6
```

### 图片插入位置建议
1. **封面图**：文章开头
2. **多平台管理图**："多平台统一管理"章节后
3. **对比图**："本地vs云端对比"章节后
4. **架构流程图**："Gateway架构"章节后
5. **安装步骤图**："如何开始使用"章节后
6. **总结对比表**："ClawBot vs 其他AI助手"章节后

### 图片优化建议
- 所有图片保持一致的视觉风格
- 颜色方案：深蓝+白色为主色调
- 图标风格：简洁扁平化
- 文字清晰可读

### 备选图片来源
如果AI生成效果不理想，可考虑：
1. **Unsplash**：搜索"tech background"、"AI concept"
2. **Pexels**：搜索"technology"、"data privacy"
3. **Flaticon**：下载相关图标组合
4. **Canva**：使用信息图表模板

---

**配图完成标志**：6张图片准备就绪，风格统一，内容清晰。