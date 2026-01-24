# Claude Skills 信息收集

## 元信息
- 信息收集时间：2026-01-24
- 下次更新建议：2026-02-24
- 信息来源：
  - GitHub官方仓库：https://github.com/anthropics/skills
  - 个人素材库：Claude Code 2.1发布文章
- 使用工具：WebFetch, 个人素材库搜索

## 什么是Claude Skills？

### 官方定义
Skills是Claude的扩展功能系统，允许用户自定义Claude的能力和工作流。

### 核心特性（来自Claude Code 2.1文章）
- **热重载**：改完skill文件立即生效，不用重启
- **上下文隔离**：context: fork让skill在隔离环境运行
- **Hooks支持**：支持PreToolUse、PostToolUse、Stop等hooks
- **YAML格式**：allowed-tools字段支持清晰的YAML列表写法

## 官方Skills完整列表（16个）

### 1. 文档处理类（生产环境推荐⭐⭐⭐）
| Skill | 功能 | 许可协议 |
|-------|------|---------|
| **docx** | Word文档创建和编辑 | Source-available |
| **pdf** | PDF文件处理和表单提取 | Source-available |
| **pptx** | PowerPoint演示文稿生成 | Source-available |
| **xlsx** | Excel电子表格操作 | Source-available |

**重要性**：这4个是Claude生产环境实际使用的核心技能，官方强烈推荐

### 2. 设计与创意类
- **algorithmic-art**：算法艺术
- **canvas-design**：Canvas设计
- **frontend-design**：前端设计⭐（推荐）
- **theme-factory**：主题工厂

### 3. 开发与技术类
- **mcp-builder**：MCP构建器⭐（推荐）
- **web-artifacts-builder**：Web构件构建器
- **webapp-testing**：Web应用程序测试

### 4. 协作与沟通类
- **doc-coauthoring**：文档协同创作
- **internal-comms**：内部沟通
- **slack-gif-creator**：Slack GIF创建器

### 5. 元技能类
- **skill-creator**：Skill创建器⭐⭐（推荐）
- **brand-guidelines**：品牌指南

## 仓库热度指标
- ⭐ **51.4k stars** - 非常受欢迎
- 🍴 **4.9k forks**
- 📝 **83 issues**
- 🔀 **102 PRs**
- 许可协议：Apache 2.0（开源Skills）+ Source-available（文档类Skills）

## 重点推荐的Skills（基于分析）

### 推荐1：frontend-design（前端设计）
- **适用场景**：快速设计和生成前端界面
- **目标用户**：产品经理、设计师、前端开发者
- **价值**：降低前端设计门槛

### 推荐2：mcp-builder（MCP构建器）
- **适用场景**：构建自定义MCP服务器
- **目标用户**：开发者、技术人员
- **价值**：扩展Claude能力

### 推荐3：skill-creator（Skill创建器）
- **适用场景**：创建自定义Skills
- **目标用户**：所有想定制Claude的用户
- **价值**：降低Skills创建门槛

### 推荐4：pdf（PDF处理）
- **适用场景**：PDF文档处理、表单提取
- **目标用户**：所有办公场景用户
- **价值**：实用性强，生产环境推荐

### 推荐5：docx/xlsx/pptx（Office文档处理）
- **适用场景**：办公文档自动化
- **目标用户**：所有办公场景用户
- **价值**：高频需求，实用性强

## 个人素材库相关信息

### 来自《Claude-Code-2.1发布》文章
- **Skills热重载**：调试skill不用重启，迭代速度大幅提升
- **实际使用痛点**：之前改完skill要重启十几次，现在立即生效
- **配置示例**：context: fork, hooks支持, YAML列表格式
- **官方资源**：https://github.com/anthropics/skills

### 真实使用场景
- 搭建代码审查workflow
- 调整审查规则措辞
- 快速迭代测试

## 技术细节（供参考）

### Skills配置结构
```yaml
allowed-tools:
  - tool1
  - tool2

hooks:
  - PreToolUse
  - PostToolUse
  - Stop

context: fork  # 隔离上下文
```

### 安装位置
- 全局：`~/.claude/skills`
- 项目级：`.claude/skills`

## 关键洞察

### 1. Skills是工作流的核心
- 不只是功能扩展，是定制化工作流的基础
- 热重载大幅提升迭代效率

### 2. 官方推荐的4个文档类Skills最实用
- docx, pdf, pptx, xlsx
- 生产环境验证，实用性强
- 高频办公场景

### 3. skill-creator是元技能
- 用Skill创建Skill
- 降低创建门槛
- 适合非技术人员

### 4. 受众分层明确
- **非技术人员**：文档类Skills（pdf, docx, xlsx, pptx）
- **技术人员**：mcp-builder, web-artifacts-builder
- **所有人**：skill-creator, frontend-design

## 待补充信息

### 需要进一步调研
- [ ] 每个Skill的详细使用方法
- [ ] 真实使用案例和效果
- [ ] 国内社区的讨论热度
- [ ] 与Cursor、其他AI工具的对比
- [ ] Skills的实际测试效果

### 热度评估来源
- 少数派、机器之心、36氪的相关讨论
- 国内技术社区的反馈
- X/Twitter的讨论

## 下一步行动
1. 执行Step 2.5：热度评估
2. 设计3-4个选题方案
3. 测试推荐的Skills（如需）

