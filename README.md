# 🎂 莫兰迪奶油花园 · Morandi Buttercream Garden (3D)

> **Three.js × GSAP 韩式复古莫兰迪油画刮刀双层奶油生日蛋糕**  
> 纯前端、零外部 3D 模型依赖（Zero External Assets），完全由 Three.js 内置几何体与 Canvas 程序化刮刀厚涂油画材质实时解算生成。支持 360° 微距自由赏析、5 层结构爆破拆解、白昼/暗夜许愿烛光、三套莫兰迪油画色彩平滑渐变与 3D 悬浮花瓣雨物理模拟。

[![Live Demo](https://img.shields.io/badge/Demo-GitHub%20Pages-f5ebe1?style=for-the-badge&logo=github&logoColor=333)](https://sukikeeling.github.io/morandi-buttercream-cake/)
[![Three.js](https://img.shields.io/badge/Three.js-r160-black?style=for-the-badge&logo=threedotjs)](https://threejs.org/)
[![GSAP](https://img.shields.io/badge/GSAP-3.12.5-00e699?style=for-the-badge&logo=greensock)](https://greensock.com/)
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](./LICENSE)
[![WebGL2](https://img.shields.io/badge/WebGL2-Supported-orange?style=for-the-badge&logo=webgl)](https://www.khronos.org/webgl/)

---

## 🌟 在线体验 (Live Demo)

👉 **在线体验**：[https://sukikeeling.github.io/morandi-buttercream-cake/](https://sukikeeling.github.io/morandi-buttercream-cake/)

💌 **个性化定制祝福 (Custom Greeting)**：  
支持通过 URL Query 参数自定义吹灭蜡烛后的祝福致辞与落款，示例：  
👉 [https://sukikeeling.github.io/morandi-buttercream-cake/?to=Alice&from=Bob](https://sukikeeling.github.io/morandi-buttercream-cake/?to=Alice&from=Bob)

---

## 📸 视觉预览 (Preview)

### 默认视角 · 莫兰迪摄影棚高调柔光
![默认视角预览](preview.png)

### 结构拆解 · 5 层爆破与动态 3D 工艺标注卡
![结构拆解预览](preview-exploded.png)

---

## ✨ 核心亮点与技术实现

### 1. 🎨 韩式莫兰迪油画刮刀肌理 (Procedural Impasto)
- **纯代码生成**：告别数十兆笨重且不可编辑的扫描 3D 模型，通过 HTML5 2D Canvas + Mulberry32 伪随机种子算法实时解算绘制；
- **真实色块堆叠**：灰雾蓝（#8FA3B8）、丁香紫（#C2AFC8）、蜜桃粉（#E8B8BA）与乳白膏体横向错落交织，还原刮刀推开黄油膏体的边缘起伏与立体色块；
- **全套 PBR 纹理映射**：实时派生高分辨率 **Color Map**、**Bump Map**、**Sobel 法线贴图** 与 **Displacement Map**，配合 `MeshStandardMaterial`（粗糙度 0.85），在掠射侧光下细腻呈现乳脂光泽与油画刀痕。

### 2. 🌹 纯算法手工裱花艺术 (Procedural Floral & Piping)
- **多层玫瑰花冠 (Band Petal Roses)**：基于曲面薄带空间展开算法构建 18~24 瓣三层立体花头，中心含螺旋内苞，外层点缀微外翻落地裙瓣；
- **法式贝壳花边 (Fan Shell Piping)**：7 组胶囊体扇形阵列铰链展开算法，边缘点缀珍珠糖珠；
- **复古立体棱纹绳 (Fluted Rope)**：自定义环面扫掠几何体，还原经典法式奶油挤花压纹；
- **植物叶片与糖珠**：挤压微弯鼠尾草叶片、`InstancedMesh` 高反光清漆糖珠（Physical Material，支持 clearcoat / iridescence 虹彩反射）。

### 3. 💥 3D 爆炸图结构拆解 (Exploded View Animation)
- **5 层分层分离**：GSAP 动画时间线精准驱动**花冠**向斜上外翻、**上层戚风**升起、**中层玫瑰环**悬浮、**下层基座**稳固下沉、**底托**沉降延展；
- **剖面流心工艺**：分层剖面真实展现香草籽戚风蛋糕胚、树莓果酱流心、伯爵茶奶油与蓝莓芋泥；
- **3D 屏幕空间自适应标注**：3D 空间锚点实时矩阵映射投影至屏幕像素空间，动态排布 4 组毛玻璃工艺卡片与发光 SVG 连接引线；
- **相机动态构图**：根据屏幕长宽比自适应重构视野（Fit Camera Target），确保展开时构图饱满居中。

### 4. 🕯️ 白昼与暗夜许愿烛光 (Day / Night Wish Candle)
- **浪漫昼夜律动**：双击蛋糕顶部或点击底栏，优雅升起螺纹金粉蜡烛；
- **氛围灯光平滑重塑**：摄影棚明亮柔白光过渡至暗夜烛光模式，伴随暖金点光源动态摆动与半透明 Additive 火焰 Glow；
- **星尘与礼花粒子**：金色微光粒子漫天浮动；吹灭蜡烛瞬间触发全屏彩色糖珠礼花（Confetti Particles），并浮现法式复古祝福贺卡。

### 5. 🎨 三套莫兰迪油画预设色彩实时渐变 (Dynamic Palette Switch)
- **经典莫兰迪 (Classic Morandi)**：蓝灰、丁香紫、柔桃粉、灰绿、奶白
- **春日抹茶樱粉 (Spring Garden)**：嫩抹茶绿、樱粉、奶油黄
- **落日焦糖伯爵茶 (Sunset Earl Grey)**：焦糖棕、杏仁米白、落日暖橘
- **Shader 纹理平滑混叠**：自定义 Shader 采样双纹理实时混合（`uMix` crossfade），裱花与 UI 色彩平滑补间。

### 6. 🌸 600+ 3D 悬浮花瓣雨 (Ambient Petal Dynamics)
- GPU InstancedMesh 粒子系统模拟微风轻拂的花瓣漫天飘落，配合正弦风力场与动态翻滚；
- 鼠标或触控在屏幕上划过时，花瓣受物理气流排斥向外推散。

### 7. 📱 极致单文件与全端自适应 (Single File & Responsive)
- **零构建工具、零编译配置**：单 HTML 文件（约 120KB）直接运行；
- **移动端深度调优**：自动侦测视口宽度与设备性能，自适应缩减贴图分辨率、细分层级、DPR 与粒子上限，保障 60 FPS 流畅交互。

---

## 🎮 交互指南 (Controls)

| 操作 | 动作效果 |
| :--- | :--- |
| **🖱️ 鼠标拖拽 / 单指滑动** | 360° 自由旋转观察角度 |
| **🔍 滚轮 / 双指捏合** | 微距推拉镜头，细品奶油刀痕与裱花纹理 |
| **🍰 单击蛋糕** | 结构爆破拆解 / 还原结构 |
| **🕯️ 双击蛋糕顶部 或 空格键** | 召唤点亮许愿蜡烛 / 吹灭蜡烛许愿 |
| **⌨️ 按下 `Esc`** | 关闭生日贺卡 / 还原拆解结构 |
| **🎛️ 底部控制坞** | 快速切换：自动旋转、拆解结构、点亮烛光、切换油画配色、花瓣雨 |

---

## 🚀 本地运行 (Local Run)

由于该项目为纯静态单文件应用，运行非常简单：

### 方式一：浏览器直接双击打开
直接双击打开 `index.html` 即可（依赖通过 CDN 极速分发，需联网加载 Three.js / GSAP 与 Google Fonts 字体）。

### 方式二：使用本地静态服务器（推荐）
```bash
# Python 3
python -m http.server 8000

# Node.js
npx serve .
```
打开浏览器访问 `http://localhost:8000` 即可。

---

## 📂 项目结构 (Project Structure)

```
morandi-buttercream-cake/
├── index.html              # 核心单文件 (HTML + CSS + Three.js + GSAP 全功能)
├── preview.png             # 默认摄影棚视角高清预览图
├── preview-exploded.png    # 5 层结构拆解与 3D 标注图
├── README.md               # 详细项目说明文档与技术原理
├── LICENSE                 # MIT 开源许可证
└── .gitignore              # Git 忽略配置
```

---

## 📜 开源许可证 (License)

本项目基于 [MIT License](./LICENSE) 开源。欢迎 Star、Fork 与二次创作！
