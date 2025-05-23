# AI Learning Resources Navigator 

<div align="right">
  <a href="#chinese-version">中文</a> | <a href="#english-version">English</a>
</div>

---

<h2 id="chinese-version">中文</h2>

这是一个使用Vue.js构建的Web应用程序，提供AI学习资源导航和各大LLM平台的便捷访问。

## 项目概述

AI Learning Resources Navigator是一个中文AI学习资源导航平台，旨在为AI学习者和开发者提供一站式的资源访问。项目包括以下主要功能：

- AI发展历史时间线
- AI核心知识导航
- 主流LLM平台快速访问
- AI知识交互式学习

## 开发进度[本项目已经完成啦，辛苦自己了]

- [x] 首页开发与设计优化
- [x] AI简介页面
- [x] LLM平台导航页面
- [x] AI历史时间线页面
- [x] AI核心知识页面
- [x] 导航栏与路由设置
- [x] 响应式设计适配
- [x] 页面动画效果
  - [x] 初始加载动画
  - [x] 滚动触发动画
  - [x] 平台卡片优化动画
- [x] CSS架构优化
  - [x] 创建共享组件样式
  - [x] 统一动画系统
  - [x] 减少样式重复
- [x] UI设计优化
  - [x] 知识页面
  - [x] LLM页面样式调整

## 项目特色

1. **现代化UI设计**：使用响应式设计，提供流畅的用户体验
2. **丰富的动画效果**：包括页面加载动画和滚动触发动画，增强视觉体验
3. **全面的AI知识**：从AI历史、基础概念到最新应用
4. **平台导航**：直接访问主流AI平台，如ChatGPT、Google Gemini、Claude等
5. **开发文档**：详细的项目文档，包括动画实现指南
6. **优化的CSS架构**：模块化CSS，减少重复代码，提高维护性

## 项目结构

```
AI Learning Resources Navigator/
├── frontend/                # 前端代码
│   ├── src/
│   │   ├── assets/          # 静态资源
│   │   │   ├── images/      # 图片资源
│   │   │   └── styles/      # 样式文件
│   │   │       ├── animations.css    # 动画和过渡效果
│   │   │       ├── main.css          # CSS变量和基础样式
│   │   │       ├── components.css    # 共享组件样式
│   │   │       ├── platforms.css     # 平台页面专用样式
│   │   │       └── fonts.css         # 字体定义
│   │   ├── components/      # Vue组件
│   │   │   ├── layout/      # 布局组件
│   │   │   │   └── Navigation.vue    # 导航栏组件
│   │   │   ├── cards/       # 卡片组件
│   │   │   │   └── KeywordsBubble.vue # 关键词气泡组件
│   │   │   ├── Platforms/   # 平台相关组件
│   │   │   │   ├── LLMPlatforms.vue   # LLM平台组件
│   │   │   │   └── LLMintegrationplatform.vue # LLM集成平台组件
│   │   │   └── timeline/    # 时间线组件
│   │   ├── views/           # 页面组件
│   │   │   ├── HomePage.vue           # 首页
│   │   │   ├── AboutAIPage.vue        # AI简介页面
│   │   │   ├── AIHistoryPage.vue      # AI历史页面
│   │   │   ├── AIKnowledgePage.vue    # AI知识页面
│   │   │   └── LLMPlatformsPage.vue   # LLM平台页面
│   │   ├── router/          # 路由配置
│   │   │   └── index.js     # 路由定义
│   │   ├── main.js          # 入口文件
│   │   └── App.vue          # 根组件
│   ├── public/              # 公共资源
│   │   └── index.html       # HTML模板
│   ├── package.json         # 项目依赖
│   └── vite.config.js       # Vite配置
└── doc/                     # 项目文档
    ├── animations/          # 动画实现文档
    │   └── animation-guide.md # 动画指南
    ├── history.md           # 历史内容
    └── keywords.md          # 关键词定义
```

## CSS架构设计

项目采用模块化的CSS架构，提高代码可维护性和复用性：

1. **CSS变量系统**：
   - 在`main.css`中定义全局变量，包括颜色、字体、间距等

2. **模块化样式组织**：
   - `fonts.css`：字体定义，最先导入以确保CSS变量可用
   - `main.css`：全局CSS变量和基础样式
   - `components.css`：共享组件样式，减少重复
   - `platforms.css`：平台页面专用样式
   - `animations.css`：统一的动画和过渡效果

3. **组件样式复用**：
   - 通过`.page-container`、`.page-header`等类名实现跨组件样式复用
   - 减少重复编写相同样式的需求

4. **最近优化**：
   - 移除重复动画定义，统一动画类名
   - 提取共享组件样式到`components.css`
   - 增强代码可读性和可维护性

## 技术栈

- **前端框架**: Vue.js 3 (Composition API)
- **路由管理**: Vue Router 4
- **UI组件库**: Naive UI
- **构建工具**: Vite
- **样式处理**: CSS
- **动画实现**: CSS Animations + Intersection Observer API

## 如何运行

### 环境准备

确保您已安装以下工具：

#### macOS:
```bash
# 使用Homebrew安装Node.js
brew install node

# 验证安装
node --version
npm --version
```

#### Windows:
- 从[Node.js官网](https://nodejs.org/)下载安装LTS版本
- 验证安装：
  ```bash
  node --version
  npm --version
  ```

### 项目设置

1. **克隆项目**
   ```bash
   git clone [repository-url]
   cd AI-Learning-Resources-Navigator
   ```

2. **安装依赖**
   ```bash
   cd frontend
   npm install
   ```

   ```bash
   cd frontend
   npm install
   ```

3. **启动开发服务器**
   ```bash
   npm run dev
   ```

应用将在`http://localhost:3000`（或其他端口，如果3000已被占用）上运行。

## 特别功能

### 动画系统

项目实现了一套完整的动画系统，主要包括：

1. **初始加载动画** - 页面加载时自动触发的动画
2. **滚动触发动画** - 当元素滚动到视图中时触发的动画
3. **统一动画类** - 通过`animate-ready`和`animate-active`类实现一致的过渡效果

详细的动画实现文档可以在`doc/animations/animation-guide.md`中找到。

### 平台导航

提供快速访问以下主流LLM平台：
- ChatGPT
- Google Gemini
- Claude
- Perplexity AI
- Deepseek R1
- Qwen 2.5

## 常见问题

1. **端口已被占用**
   - 如果端口3000已被占用，开发服务器将自动尝试下一个可用端口
   - 您可以通过修改`vite.config.js`文件手动指定端口

2. **依赖项问题**
   - 如果遇到依赖相关错误，请尝试：
     ```bash
     rm -rf node_modules package-lock.json
     npm install
     ```

## 支持与贡献

如有任何问题或建议，请在仓库中提交issue。欢迎贡献代码和改进建议！

---

<h2 id="english-version">English Version</h2>

# AI Learning Resources Navigator

This is a web application built with Vue.js that provides easy navigation to AI learning resources and quick access to various LLM platforms.

## Project Overview

AI Learning Resources Navigator is a Chinese AI learning resource navigation platform, designed to provide AI learners and developers with one-stop resource access. The project includes the following main features:

- AI development history timeline
- AI core knowledge navigation
- Quick access to mainstream LLM platforms
- Interactive AI knowledge learning

## Development Progress[All finished]

- [x] Home page development and design optimization
- [x] About AI page
- [x] LLM platforms navigation page
- [x] AI history timeline page
- [x] AI core knowledge page
- [x] Navigation bar and routing setup
- [x] Responsive design
- [x] Page animation effects
  - [x] Initial loading animations
  - [x] Scroll-triggered animations
  - [x] Platform card optimized animations
- [x] CSS architecture optimization
  - [x] Shared component styles
  - [x] Unified animation system
  - [x] Reduced style duplication
- [x] UI design optimization
  - [x] Knowledge page
  - [x] LLM page style adjustments

## Project Features

1. **Modern UI Design**: Responsive design for a smooth user experience
2. **Rich Animation Effects**: Including page loading animations and scroll-triggered animations
3. **Comprehensive AI Knowledge**: From AI history and basic concepts to latest applications
4. **Platform Navigation**: Direct access to mainstream AI platforms like ChatGPT, Google Gemini, Claude, etc.
5. **Development Documentation**: Detailed project documentation including animation implementation guide
6. **Optimized CSS Architecture**: Modular CSS, reduced code duplication, improved maintainability

## Project Structure

```
AI Learning Resources Navigator/
├── frontend/                # Frontend code
│   ├── src/
│   │   ├── assets/          # Static resources
│   │   │   ├── images/      # Image resources
│   │   │   └── styles/      # Style files
│   │   │       ├── animations.css    # Animations and transitions
│   │   │       ├── main.css          # CSS variables and base styles
│   │   │       ├── components.css    # Shared component styles
│   │   │       ├── platforms.css     # Platform-specific styles
│   │   │       └── fonts.css         # Font definitions
│   │   ├── components/      # Vue components
│   │   │   ├── layout/      # Layout components
│   │   │   │   └── Navigation.vue    # Navigation bar component
│   │   │   ├── cards/       # Card components
│   │   │   │   └── KeywordsBubble.vue # Keywords bubble component
│   │   │   ├── Platforms/   # Platform-related components
│   │   │   │   ├── LLMPlatforms.vue   # LLM platforms component
│   │   │   │   └── LLMintegrationplatform.vue # LLM integration platforms component
│   │   │   └── timeline/    # Timeline components
│   │   ├── views/           # Page components
│   │   │   ├── HomePage.vue           # Home page
│   │   │   ├── AboutAIPage.vue        # About AI page
│   │   │   ├── AIHistoryPage.vue      # AI history page
│   │   │   ├── AIKnowledgePage.vue    # AI knowledge page
│   │   │   └── LLMPlatformsPage.vue   # LLM platforms page
│   │   ├── router/          # Router configuration
│   │   │   └── index.js     # Route definitions
│   │   ├── main.js          # Entry file
│   │   └── App.vue          # Root component
│   ├── public/              # Public resources
│   │   └── index.html       # HTML template
│   ├── package.json         # Project dependencies
│   └── vite.config.js       # Vite configuration
└── doc/                     # Project documentation
    ├── animations/          # Animation implementation docs
    │   └── animation-guide.md # Animation guide
    ├── history.md           # History content
    └── keywords.md          # Keyword definitions
```

## CSS Architecture Design

The project employs a modular CSS architecture to improve code maintainability and reusability:

1. **CSS Variable System**:
   - Global variables defined in `main.css`, including colors, fonts, spacing, etc.

2. **Modular Style Organization**:
   - `fonts.css`: Font definitions, imported first to ensure CSS variables are available
   - `main.css`: Global CSS variables and base styles
   - `components.css`: Shared component styles to reduce redundancy
   - `platforms.css`: Styles specific to platform pages
   - `animations.css`: Unified animations and transition effects

3. **Component Style Reuse**:
   - Cross-component style reuse through classes like `.page-container`, `.page-header`, etc.
   - Reduced need to write the same styles repeatedly

4. **Recent Optimizations**:
   - Removed duplicate animation definitions, unified animation class names
   - Extracted shared component styles to `components.css`
   - Enhanced code readability and maintainability

## Tech Stack

- **Frontend Framework**: Vue.js 3 (Composition API)
- **Router**: Vue Router 4
- **UI Component Library**: Naive UI
- **Build Tool**: Vite
- **Styling**: CSS
- **Animation Implementation**: CSS Animations + Intersection Observer API

## How to Run

### Environment Preparation

Make sure you have installed the following tools:

#### macOS:
```bash
# Install Node.js using Homebrew
brew install node

# Verify installation
node --version
npm --version
```

#### Windows:
- Download and install the LTS version from [Node.js website](https://nodejs.org/)
- Verify installation:
  ```bash
  node --version
  npm --version
  ```

### Project Setup

1. **Clone the Project**
   ```bash
   git clone [repository-url]
   cd AI-Learning-Resources-Navigator
   ```

2. **Install Dependencies**
   ```bash
   cd frontend
   npm install
   ```

3. **Start Development Server**
   ```bash
   npm run dev
   ```

The application will run on `http://localhost:3000` (or another port if 3000 is already in use).

## Special Features

### Animation System

The project implements a complete animation system, including:

1. **Initial Loading Animations** - Animations triggered automatically when the page loads
2. **Scroll-Triggered Animations** - Animations triggered when elements scroll into view
3. **Unified Animation Classes** - Consistent transition effects through `animate-ready` and `animate-active` classes

Detailed animation implementation documentation can be found in `doc/animations/animation-guide.md`.

### Platform Navigation

Provides quick access to the following mainstream LLM platforms:
- ChatGPT
- Google Gemini
- Claude
- Perplexity AI
- Deepseek R1
- Qwen 2.5

## Common Issues

1. **Port Already in Use**
   - If port 3000 is already in use, the development server will automatically try the next available port
   - You can manually specify the port by modifying the `vite.config.js` file

2. **Dependency Issues**
   - If you encounter dependency-related errors, try:
     ```bash
     rm -rf node_modules package-lock.json
     npm install
     ```

## Support and Contribution

If you have any questions or suggestions, please submit an issue in the repository. Code contributions and improvement suggestions are welcome!
