## 一、调研概述

### 1.1 调研背景

随着AI辅助开发工具的普及，开发者越来越多地依赖AI生成前端界面代码。然而，AI生成的设计往往存在风格单一、缺乏设计语言一致性、图标资源管理困难等问题。本次调研聚焦于8个AI设计相关的Skills和工具，旨在帮助团队建立AI辅助开发中的设计规范和质量保障体系。

### 1.2 工具概览

| 工具 | 类型 | 核心功能 | 适用场景 |
|------|------|---------|---------|
| **Impeccable** | 设计质量工具 | 设计反模式检测、设计语言教学 | 全面设计质量保障 |
| **Awesome Design Skills** | Skills注册表 | 设计系统Skills的集中索引 | 快速查找和获取设计Skills |
| **Awesome DESIGN.md** | DESIGN.md集合 | 品牌设计系统参考文档 | 快速复用成熟设计风格 |
| **Taste-Skill** | 设计Skills套件 | 7种设计风格Skills + 参数化调节 | 多样化界面生成 |
| **Better Icons** | 图标资源工具 | 20万+图标检索与管理 | 统一图标资源管理 |
| **UI Skills** | 实用Skills套件 | 可访问性、动效、元数据等专项优化 | 界面专项优化 |
| **Google Stitch** | 设计语言协议 | DESIGN.md标准规范 | 设计系统标准化定义 |
| **Google Stitch CLI** | 命令行工具 | DESIGN.md预览与验证 | 设计文档的本地开发调试 |

---

## 二、Impeccable

### 2.1 产品介绍

Impeccable是一个全面的设计语言教学和设计质量检测工具，它通过一套系统化的设计知识库和18个命令，帮助AI生成更专业、更精致的前端界面。其核心理念是：AI学习自同样的通用模板，没有干预时会产生同样的可预测错误——Inter字体、紫色渐变、卡片嵌套、低对比度等问题。Impeccable通过对抗这种"设计偏见"来提升AI的设计质量。

### 2.2 核心功能

**1. 增强型设计技能（Enhanced Design Skill）**

Impeccable内置了7个维度的设计领域知识，每次AI编写代码时都会加载这些参考知识：

| 领域 | 内容要点 |
|------|---------|
| **Typography**（排版） | 字体系统、字体配对、模块化比例、OpenType特性 |
| **Color & Contrast**（色彩与对比度） | OKLCH色彩空间、调色中性色、暗色模式、可访问性 |
| **Spatial Design**（空间设计） | 间距系统、网格、视觉层次 |
| **Responsive**（响应式） | 移动优先、流体布局、容器查询 |
| **Interaction**（交互设计） | 表单设计、焦点状态、加载模式 |
| **Motion**（动效设计） | 缓动曲线、交错动画、减少动画偏好支持 |
| **UX Writing**（UX文案） | 按钮标签、错误提示、空状态文案 |



**2. 18个设计命令**

这些命令构成了用户与AI之间的共享设计语言：

| 命令 | 功能描述 |
|------|---------|
| `/impeccable teach` | 一次性设置：收集设计上下文，保存到配置文件 |
| `/impeccable craft` | 完整的设计→构建流程，包含视觉迭代 |
| `/impeccable extract` | 提取可复用组件和设计Token到设计系统 |
| `/audit` | 技术质量检查（可访问性、性能、响应式） |
| `/critique` | UX设计评审（层次、清晰度、情感共鸣） |
| `/polish` | 最终打磨，设计系统对齐，发布就绪检查 |
| `/distill` | 精简设计到核心要素 |
| `/clarify` | 改进不清晰的UX文案 |
| `/optimize` | 性能优化 |
| `/harden` | 错误处理、引导、国际化、边界情况完善 |
| `/animate` | 添加有目的的动效 |
| `/colorize` | 引入战略性配色 |
| `/bolder` | 增强平淡的设计 |
| `/quieter` | 调低过于张扬的设计 |



**3. 设计反模式检测（Anti-Patterns Detection）**

25个确定性检测规则，无需LLM即可运行，模式匹配捕获渐变文本、AI配色方案、嵌套卡片、低对比度等20+种问题，支持HTML、CSS、JSX/TSX、Vue、Svelte文件。

**4. 视觉模式（Visual Mode）**

Chrome扩展可在任何页面上叠加显示设计问题，无需截图或猜测，直接在页面上高亮标注问题位置。

### 2.3 使用方法

**安装方式一：Skills安装（推荐）**

```bash
npx skills add pbakaus/impeccable
```
安装后运行 `/impeccable teach` 设置项目设计上下文。

**安装方式二：Claude Code插件**

在Claude Code中打开插件市场，添加 `pbakaus/impeccable`。

**安装方式三：CLI工具（Beta）**

```bash
npx impeccable detect src/
# 或全局安装
npm i -g impeccable
```
可在CI流水线、pre-commit hooks中使用。

**Chrome扩展**

从Chrome Web Store安装，点击工具栏图标即可对当前页面进行反模式检测。

### 2.4 集成到开发流程

| 集成环节 | 方式 | 说明 |
|---------|------|------|
| **AI编码助手** | 安装Skills | 支持Cursor、Claude Code、Gemini CLI、Codex CLI等 |
| **CI/CD流水线** | CLI工具 | `npx impeccable detect` 检测代码中的设计反模式 |
| **Git Hooks** | CLI工具 | 在pre-commit阶段拦截设计问题 |
| **代码审查** | Chrome扩展 + CLI | 对已完成页面进行视觉和技术双重检测 |

### 2.5 其他有用信息

- **许可证**：开源（GitHub可查看完整源码）
- **依赖关系**：基于Anthropic的frontend-design skill构建，在此基础上扩展了更深的专业知识和更精细的控制
- **适用框架**：支持HTML、CSS、JSX/TSX、Vue、Svelte

---

## 三、Awesome Design Skills

### 3.1 产品介绍

Awesome Design Skills是一个精心整理的**设计系统Skill文件注册表**，专为Claude Code、Cursor、Codex等AI Agent工具设计。它通过typeui.sh CLI工具，让开发者可以用一条命令将任意设计Skill拉取到项目中。每个Skill都是一个SKILL.md文件，包含设计Token、组件指南、可访问性规则和实现规范。

### 3.2 核心功能

**1. 设计Skill注册表**

提供数十种不同风格的设计系统Skills，涵盖多种视觉风格和品牌调性：

| 类别 | 示例Skill | 风格描述 |
|------|---------|---------|
| **Themed & Unique** | Agentic | AI主题风格 |
| **Professional & Corporate** | Ant, Application | 专业企业级设计 |
| **Creative & Artistic** | Artistic | 创意艺术风格 |
| **Layout & Structure** | Bento | 便当盒式布局 |
| **Bold & Expressive** | Bold, Brutalism | 粗犷表达风格 |
| **Flat & Colorful** | Flat, Cartoon | 扁平卡通风格 |
| **Soft & Elegant** | Soft | 柔和优雅风格 |
| **Glassmorphism** | Glassmorphism | 毛玻璃效果 |
| **Minimalist & Swiss** | Minimalist | 极简瑞士风格 |

**2. 统一拉取工具**

通过typeui.sh CLI实现一站式管理：
```bash
npx typeui.sh pull <skill-name>
npx typeui.sh list
```


**3. 预览系统**

所有Skills均可在[typeui.sh/design-skills](https://typeui.sh/design-skills)上预览后再拉取。

### 3.3 使用方法

```bash
# 查看所有可用Skills
npx typeui.sh list

# 拉取特定Skill（如Glassmorphism）
npx typeui.sh pull glassmorphism

# 拉取后，SKILL.md文件会出现在项目目录中
# AI Agent会自动读取并遵循其中的设计规范
```

### 3.4 集成到开发流程

| 集成环节 | 方式 | 说明 |
|---------|------|------|
| **项目初始化** | `npx typeui.sh pull` | 在项目根目录添加设计Skill |
| **AI编码** | SKILL.md文件 | AI Agent自动读取并遵循设计规范 |
| **设计切换** | 拉取不同Skill | 快速尝试多种设计风格 |
| **团队协作** | 提交SKILL.md | 确保团队AI工具使用统一的设计规范 |

### 3.5 其他有用信息

- **维护者**：Bergside团队
- **预览平台**：typeui.sh
- **与Impeccable的关系**：Impeccable是单一深度工具，Awesome Design Skills是多个设计系统Skills的索引和分发平台，两者可互补使用

---

## 四、Awesome DESIGN.md

### 4.1 产品介绍

Awesome DESIGN.md是一个**DESIGN.md文件集合**，收录了从真实热门网站中提取的设计系统文档。DESIGN.md是Google Stitch提出的新概念——一个纯文本设计系统文档，AI Agent通过读取它来生成一致的UI界面。无需Figma导出、JSON Schema或特殊工具，只需一个Markdown文件放入项目根目录，任何AI编码Agent即可理解UI应该如何呈现。

### 4.2 核心功能

**1. 品牌设计系统库**

提供来自知名AI和开发者工具品牌的设计系统：

| 品牌 | 风格特征 |
|------|---------|
| **Claude** | 温暖的陶土色点缀，干净的编辑风格 |
| **Cohere** | 鲜艳的渐变，数据密集型仪表盘美学 |
| **ElevenLabs** | 深色电影风格UI，音频波形美学 |
| **Mistral AI** | 法式极简主义，紫色调 |
| **Ollama** | 终端优先，单色简约 |
| **Cursor** | 流畅的深色界面，渐变色点缀 |
| **Expo** | React Native平台风格 |

**2. DESIGN.md标准化**

每个DESIGN.md文件包含：
- 品牌使命与设计哲学
- 排版比例与字体系统
- 色彩方案（亮色/暗色模式）
- 间距系统与网格
- 组件样式规范
- 可访问性要求

**3. 按需定制服务**

可通过[getdesign.md/request](https://getdesign.md/request)请求特定网站的设计系统提取。

### 4.3 使用方法

```bash
# 直接复制DESIGN.md文件到项目根目录
cp ~/downloads/claude-design.md ./DESIGN.md

# 或通过网站获取
# 访问 getdesign.md 选择品牌，下载DESIGN.md
```

AI Agent会自动读取项目根目录的DESIGN.md文件并应用于UI生成。

### 4.4 集成到开发流程

| 集成环节 | 方式 | 说明 |
|---------|------|------|
| **设计系统定义** | 放置DESIGN.md | 为AI Agent提供设计规范 |
| **品牌风格对齐** | 选择品牌DESIGN.md | 快速实现类似某品牌的设计风格 |
| **设计迭代** | 替换DESIGN.md | 快速切换不同设计方向 |
| **团队标准化** | Git管理DESIGN.md | 版本控制设计系统演进 |

### 4.5 其他有用信息

- **DESIGN.md标准**：由Google Stitch定义，详见第七节
- **文件格式**：纯Markdown，LLM原生理解最佳
- **与SKILL.md的区别**：DESIGN.md定义"长什么样"，SKILL.md定义"怎么做"

---

## 五、Taste-Skill

### 5.1 产品介绍

Taste-Skill是一套让AI生成"有品味"前端代码的Skills集合。它通过7个专业化的Skill变体、可调参数系统和反重复规则，帮助AI生成现代、高级感的设计，而不是通用、乏味的界面。

### 5.2 核心功能

**1. 7个专业Skills**

| Skill | 功能描述 |
|-------|---------|
| **taste-skill** | 主设计Skill，涵盖布局、排版、配色、间距、动效 |
| **gpt-taste** | Awwwards级别的UI设计，包含严格GSAP动画要求 |
| **redesign-skill** | 升级现有项目，先审计后修复设计问题 |
| **soft-skill** | 柔和高级UI风格，优质字体、留白、深度、弹性动画 |
| **output-skill** | 防止AI偷懒，杜绝占位注释、跳过的代码块 |
| **minimalist-skill** | Notion/Linear风格，单色系、清晰边框 |
| **brutalist-skill** | 粗野主义，融合瑞士印刷风格与CRT终端美学 |
| **stitch-skill** | Google Stitch兼容的语义设计规则 |



**2. 参数化调节系统**

taste-skill支持三个可调参数（1-10范围）：

| 参数 | 低值（1-3） | 高值（8-10） |
|------|-----------|-------------|
| **DESIGN_VARIANCE** | 简洁居中布局 | 不对称现代布局 |
| **MOTION_INTENSITY** | 简单悬停效果 | 磁性/滚动触发效果 |
| **VISUAL_DENSITY** | 宽敞奢华感 | 密集仪表盘 |

**3. 反重复规则**

基于原创研究，内置防止AI重复生成相同设计的规则。

### 5.3 使用方法

```bash
# 安装整个Skills套件
npx skills add https://github.com/Leonxlnx/taste-skill

# 安装后，AI Agent即可使用7个Skills
# 可通过修改SKILL.md文件顶部的参数调节设计风格
```

**参数调节示例**（修改taste-skill文件顶部）：

```markdown
DESIGN_VARIANCE = 8
MOTION_INTENSITY = 7
VISUAL_DENSITY = 4
```

### 5.4 集成到开发流程

| 集成环节 | 方式 | 说明 |
|---------|------|------|
| **AI编码助手** | Skills安装 | 支持Cursor、Claude Code、Codex等 |
| **设计风格切换** | 参数调节 | 通过修改数字调整设计风格 |
| **项目升级** | redesign-skill | 对已有项目进行设计审查和升级 |
| **GSAP动画** | gpt-taste | 需要高级动画时使用 |

### 5.5 其他有用信息

- **v2 Beta版本**：正在开发中，可加入等待列表
- **框架无关**：适用于React、Vue、Svelte等所有主流框架
- **作者**：Leonxlnx
- **研究背景**：包含research文件夹，记录构建这些Skills的研究基础

---

## 六、Better Icons

### 6.1 产品介绍

Better Icons是一个**图标检索与管理工具**，提供对150+图标集合、超过20万个图标的统一访问能力。它同时支持MCP服务器模式（供AI Agent调用）和CLI模式（供开发者直接使用），旨在解决AI辅助编码中图标的常见痛点——AI不知道有哪些可用图标、生成的SVG代码不稳定、样式不一致、以及内联SVG消耗大量Token等问题。

### 6.2 核心功能

**1. 海量图标库**

- **200,000+图标**，来自150+图标集合
- 支持Lucide、Heroicons、Material Design Icons等主流图标库
- 跨集合搜索和相似图标推荐



**2. MCP服务器模式**

为AI Agent提供图标搜索和获取工具：

| 工具 | 功能 |
|------|------|
| `search_icons` | 搜索图标，支持关键词、数量限制、集合过滤、分类过滤 |
| `get_icon` | 获取指定图标SVG代码 |
| `batch_get_icons` | 批量获取多个图标 |
| `find_similar` | 查找不同集合中相同含义的图标 |
| `recent_icons` | 快速访问最近使用的图标 |

**3. CLI工具**

```bash
# 搜索图标
npx better-icons search arrow --limit 10
npx better-icons search home --prefix lucide

# 获取图标
npx better-icons get lucide:home > icon.svg
npx better-icons get mdi:account --color '#333' --size 24

# JSON输出（用于脚本）
npx better-icons search settings --json | jq '.icons[:5]'
```



**4. 智能功能**

- **自动学习**：记住你使用的图标集合，在后续搜索中优先推荐
- **项目同步**：直接将图标写入项目图标文件（`.tsx`、`.ts`、`.js`），而非在聊天中粘贴SVG（节省Token）
- **多框架支持**：React、Vue、Svelte、Solid、原始SVG



### 6.3 使用方法

**方式一：Skills安装**

```bash
npx skills add better-auth/better-icons
```

**方式二：MCP服务器配置**

```bash
# 交互式配置
npx better-icons setup
```

**手动配置**（以Cursor为例）：

在 `~/.cursor/mcp.json` 中添加：
```json
{
  "mcpServers": {
    "better-icons": {
      "command": "npx",
      "args": ["-y", "better-icons"]
    }
  }
}
```



**方式三：全局CLI安装**

```bash
npm install -g better-icons
# 或使用Bun（更快）
bun add -g better-icons
```



### 6.4 集成到开发流程

| 集成环节 | 方式 | 说明 |
|---------|------|------|
| **AI编码助手** | MCP服务器 | 让AI能搜索和获取正确的图标 |
| **命令行开发** | CLI工具 | 手动搜索和导出图标 |
| **CI/CD构建** | CLI + JSON输出 | 自动化图标资源处理 |
| **Token节省** | 项目同步模式 | 图标写入文件而非粘贴，节省上下文Token |

### 6.5 其他有用信息

- **开发者**：better-auth团队
- **开源协议**：GitHub公开可用
- **支持的AI工具**：Cursor、Claude Code、OpenCode、Windsurf、VS Code Copilot、Google Antigravity
- **图标集合数量**：150+个，持续增加

---

## 七、Google Stitch

### 7.1 产品介绍

Google Stitch是Google推出的一套**AI辅助UI开发工具链**，包含两个核心组成部分：

1. **DESIGN.md**：一个开放的设计语言协议（Open Format），以Markdown文件的形式定义设计系统。这个文件被AI Agent读取后，可生成符合该设计系统的UI界面。

2. **Stitch CLI**：用于预览和验证DESIGN.md文件效果的命令行工具，帮助开发者在本地快速迭代设计系统定义。

### 7.2 核心功能

**1. DESIGN.md格式规范**

DESIGN.md是一种纯文本的设计系统描述格式，核心设计理念是"Markdown是LLM理解最好的格式，无需解析或配置"。

典型的DESIGN.md结构包括：
- **Design Principles**：设计原则
- **Typography**：字体系统定义
- **Color Palette**：色彩系统（含亮色/暗色模式）
- **Spacing & Layout**：间距与布局规则
- **Components**：组件样式规范
- **Accessibility**：可访问性要求
- **Voice & Tone**：文案风格

**2. Stitch CLI工具**

```bash
# 预览DESIGN.md在AI眼中的效果
stitch preview

# 验证DESIGN.md文件格式
stitch validate ./DESIGN.md

# 创建新的DESIGN.md模板
stitch init
```

Stitch CLI的核心价值在于让开发者能在本地快速验证DESIGN.md定义是否准确表达了设计意图，确保AI Agent生成的UI与预期一致。

### 7.3 使用方法

**创建DESIGN.md**：

```bash
# 初始化一个新的DESIGN.md模板
npx @google/stitch init

# 编辑DESIGN.md，定义设计系统
# 预览效果
npx @google/stitch preview
```

**在项目中使用**：

1. 将DESIGN.md放入项目根目录
2. AI Agent会自动读取并应用其中的设计规范
3. 或通过Stitch CLI将DESIGN.md转换为其他格式

### 7.4 集成到开发流程

| 集成环节 | 方式 | 说明 |
|---------|------|------|
| **设计系统定义** | 编写DESIGN.md | 一次性定义，长期使用 |
| **设计系统迭代** | 修改DESIGN.md | 设计语言演进时同步更新 |
| **设计预览** | `stitch preview` | 本地预览AI理解的设计效果 |
| **设计验证** | `stitch validate` | 确保格式正确性 |
| **团队协作** | Git管理DESIGN.md | 设计系统的版本控制 |

### 7.5 生态整合

Google Stitch是整个AI设计生态的基础层，与本次调研的其他工具有紧密关联：

| 工具 | 与Stitch的关系 |
|------|---------------|
| **Awesome DESIGN.md** | 提供大量现成的DESIGN.md文件，可直接用于Stitch |
| **Taste-Skill（stitch-skill）** | 提供Stitch兼容的语义设计规则 |
| **UI Skills** | 可视为Stitch之上的专项优化Skills |

### 7.6 其他有用信息

- **开发方**：Google
- **开源状态**：公开可用
- **格式优势**：纯文本Markdown，LLM原生支持，无需解析开销
- **适用场景**：团队希望建立可版本控制、AI可读的轻量级设计系统

---

## 八、UI Skills

### 8.1 产品介绍

UI Skills是一套**实用的界面优化Skills集合**，提供针对特定设计问题的专项优化能力。由ibelick维护，支持Claude Code、Cursor、OpenCode等主流AI编码工具。

### 8.2 核心功能

**提供的Skills列表**：

| Skill | 功能描述 |
|-------|---------|
| **baseline-ui** | 基础UI优化，作为设计基准 |
| **fixing-accessibility** | 可访问性修复（WCAG合规） |
| **fixing-metadata** | 元数据（meta tags、OG标签）修复 |
| **fixing-motion-performance** | 动效性能优化 |
| **12-principles-of-animation** | 动画12原则应用 |
| **canvas-design** | Canvas设计指导 |
| **design-lab** | 设计实验环境 |
| **frontend-design** | 前端设计综合指导 |
| **interaction-design** | 交互设计规范 |
| **interface-design** | 界面设计原则 |
| **swiftui-ui-patterns** | SwiftUI UI模式 |
| **ui-ux-pro-max** | 综合UI/UX优化 |
| **wcag-audit-patterns** | WCAG审查模式 |
| **web-design-guidelines** | Web设计指南 |



### 8.3 使用方法

```bash
# 安装整套UI Skills
npx skills add ibelick/ui-skills

# 或安装单个Skill
npx ui-skills add fixing-accessibility
npx ui-skills add wcag-audit-patterns

# 使用Skill
/baseline-ui review src/
```

### 8.4 集成到开发流程

| 集成环节 | 方式 | 说明 |
|---------|------|------|
| **可访问性审查** | wcag-audit-patterns | 代码提交前的可访问性检查 |
| **动效优化** | fixing-motion-performance | 动画性能调优 |
| **元数据SEO** | fixing-metadata | 页面元数据完善 |
| **设计评审** | baseline-ui | 作为设计基准进行对比 |

### 8.5 与其他工具的定位差异

| 对比维度 | UI Skills | Impeccable | Taste-Skill |
|---------|----------|------------|-------------|
| **定位** | 专项优化工具集 | 全面设计质量工具 | 设计风格生成器 |
| **侧重点** | 特定问题的修复 | 设计反模式检测 | 设计风格多样性 |
| **使用场景** | 针对性的优化任务 | 全流程设计质量保障 | 新项目风格选择 |

---

## 九、工具对比与选型建议

### 9.1 功能维度对比

| 功能 | Impeccable | Awesome Design Skills | Awesome DESIGN.md | Taste-Skill | Better Icons | UI Skills | Google Stitch |
|------|------------|----------------------|-------------------|-------------|--------------|-----------|---------------|
| **设计质量检测** | ✅ 25项反模式检测 | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| **设计风格生成** | ✅ 内置7维度知识 | ✅ 数十种风格 | ✅ 品牌风格库 | ✅ 7种风格变体 | ❌ | ❌ | ✅ 格式标准 |
| **图标管理** | ❌ | ❌ | ❌ | ❌ | ✅ 20万+图标 | ❌ | ❌ |
| **专项优化** | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ 14个专项 | ❌ |
| **Chrome扩展** | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| **CLI工具** | ✅ | ✅（via typeui.sh） | ❌ | ❌ | ✅ | ✅ | ✅ |
| **参数化调节** | ❌ | ❌ | ❌ | ✅ 3参数 | ❌ | ❌ | ❌ |

### 9.2 选型建议

| 需求场景 | 推荐工具 | 理由 |
|---------|---------|------|
| **建立完整的AI设计质量保障体系** | Impeccable | 同时覆盖设计教学、命令控制和反模式检测 |
| **快速获取不同风格的设计系统** | Awesome Design Skills | 数十种风格一键拉取 |
| **复刻特定品牌的设计风格** | Awesome DESIGN.md | 提供真实品牌的设计系统 |
| **生成多样化、有品味的设计** | Taste-Skill | 7种风格变体 + 参数化调节 |
| **解决图标管理问题** | Better Icons | 20万+图标 + MCP/CLI双模式 |
| **针对性修复设计问题** | UI Skills | 14个专项优化Skills |
| **定义项目设计系统标准** | Google Stitch | DESIGN.md标准 + 预览验证工具 |

### 9.3 组合使用建议

**场景一：新项目启动**

1. 使用 **Google Stitch** 定义项目的DESIGN.md（设计系统基础）
2. 从 **Awesome Design Skills** 或 **Taste-Skill** 中选择适合的设计风格
3. 使用 **Better Icons** 管理图标资源
4. 开发过程中使用 **Impeccable** 命令进行设计评审和打磨

**场景二：已有项目优化**

1. 使用 **Impeccable** 的 `/audit` 和 `/critique` 命令进行设计审计
2. 针对审计发现的问题，使用 **UI Skills** 进行专项修复
3. 使用 **Better Icons** 统一替换不一致的图标
4. 将优化后的设计规范沉淀为 **DESIGN.md**

**场景三：团队标准化**

1. 团队统一使用 **Google Stitch** 定义和维护DESIGN.md
2. 将DESIGN.md纳入Git版本控制
3. 在CI流水线中集成 **Impeccable CLI** 进行设计反模式检测
4. 使用 **Better Icons MCP** 确保团队图标使用的一致性

### 9.4 集成架构图

```
┌─────────────────────────────────────────────────────────────────┐
│                        开发流程集成层                            │
├─────────────┬─────────────┬─────────────┬─────────────┬─────────┤
│  项目初始化  │  AI编码阶段  │  代码审查   │  CI/CD流水线 │  发布前  │
├─────────────┼─────────────┼─────────────┼─────────────┼─────────┤
│ Google Stitch│  DESIGN.md  │  DESIGN.md  │ Impeccable  │ Impeccable│
│ (init)      │  (自动读取)  │  (对比验证) │  CLI检测    │  /polish  │
│             │             │             │             │           │
│ Awesome     │ Taste-Skill │  UI Skills  │ Better Icons│  UI Skills│
│ DESIGN.md   │ (风格生成)  │  (专项优化) │  (资源检查) │  (最终)   │
├─────────────┴─────────────┴─────────────┴─────────────┴─────────┤
│                        工具链支撑层                              │
├─────────────────────────────────────────────────────────────────┤
│  • AI编码助手：Cursor、Claude Code、Codex、Windsurf等            │
│  • 设计标准：Google Stitch DESIGN.md格式                          │
│  • 资源管理：Better Icons (150+集合，20万+图标)                   │
└─────────────────────────────────────────────────────────────────┘
```

---

## 十、附录

### 10.1 快速安装命令汇总

| 工具 | 安装命令 |
|------|---------|
| Impeccable | `npx skills add pbakaus/impeccable` |
| Awesome Design Skills | `npx typeui.sh pull <skill-name>` |
| Awesome DESIGN.md | 从 [getdesign.md](https://getdesign.md/) 下载 |
| Taste-Skill | `npx skills add https://github.com/Leonxlnx/taste-skill` |
| Better Icons | `npx skills add better-auth/better-icons` |
| UI Skills | `npx skills add ibelick/ui-skills` |
| Google Stitch | `npx @google/stitch init` |

### 10.2 相关链接

| 工具 | 官网/GitHub | 预览/演示 |
|------|------------|----------|
| Impeccable | https://impeccable.style/ | [Cheatsheet](https://impeccable.style/cheatsheet) |
| Awesome Design Skills | https://github.com/bergside/awesome-design-skills | [typeui.sh](https://typeui.sh/design-skills) |
| Awesome DESIGN.md | https://github.com/VoltAgent/awesome-design-md | [getdesign.md](https://getdesign.md/) |
| Taste-Skill | https://github.com/Leonxlnx/taste-skill | - |
| Better Icons | https://github.com/better-auth/better-icons | - |
| UI Skills | https://www.ui-skills.com/ | - |
| Google Stitch | https://stitch.withgoogle.com | - |

### 10.3 术语解释

| 术语 | 含义 |
|------|------|
| **Skill** | 一个SKILL.md文件，包含AI生成代码时应遵循的指令和知识 |
| **DESIGN.md** | Google Stitch定义的设计系统Markdown文件 |
| **MCP** | Model Context Protocol，AI Agent调用外部工具的协议 |
| **Anti-Pattern** | 设计中应避免的常见错误模式 |
| **Type Scale** | 排版比例系统，定义字体大小的层次关系 |
