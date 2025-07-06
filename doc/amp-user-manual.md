# Amp 用户手册 - 小白快速入门指南

## 📋 目录

1. [什么是 Amp？](#什么是-amp)
2. [快速安装](#快速安装)
3. [基础使用](#基础使用)
4. [实操命令大全](#实操命令大全)
5. [高级功能](#高级功能)
6. [最佳实践](#最佳实践)
7. [常见问题](#常见问题)

---

## 什么是 Amp？

Amp 是由 Sourcegraph 开发的 **AI 代理编码工具**，它能够：

- 🤖 **智能编码助手**：基于 Claude Sonnet 4 模型，提供强大的代码生成和分析能力
- 🔧 **多平台支持**：支持 VS Code、Cursor、Windsurf 编辑器和命令行工具
- 👥 **团队协作**：支持线程分享和团队协作功能
- 🎯 **专业级工具**：无代币限制，始终使用最佳模型

### 核心特点

- ✅ **无限制使用**：无代币限制，按实际使用付费
- ✅ **自动模型选择**：无需手动选择模型，自动使用最优模型
- ✅ **直接模型对话**：Amp 是外壳，你直接与模型对话
- ✅ **持续更新**：跟随最新最强模型，不被锁定

---

## 快速安装

### 方式一：编辑器扩展（推荐）

1. **注册账号**
   ```bash
   # 访问官网注册
   https://ampcode.com/settings
   ```

2. **安装扩展**
   - VS Code：在扩展商店搜索 "Amp"
   - Cursor：在扩展商店搜索 "Amp"
   - Windsurf：在扩展商店搜索 "Amp"

3. **登录认证**
   - 安装后会自动提示登录
   - 按提示完成认证

### 方式二：命令行工具

#### 使用 npm 安装

```bash
# 全局安装
npm install -g @sourcegraph/amp

# 启动交互模式
amp

# 直接输入命令
echo "今天是几号？" | amp
```

#### 使用 pnpm 安装

```bash
# 全局安装
pnpm add -g @sourcegraph/amp

# 启动交互模式
amp

# 直接输入命令
echo "今天是几号？" | amp
```

#### 使用 yarn 安装

```bash
# 全局安装
yarn global add @sourcegraph/amp

# 启动交互模式
amp

# 直接输入命令
echo "今天是几号？" | amp
```

#### 使用 npx（无需安装）

```bash
# 直接运行（首次会提示登录）
npx @sourcegraph/amp

# 直接输入命令
echo "今天是几号？" | npx @sourcegraph/amp
```

### 方式三：CI/CD 或脚本使用

```bash
# 设置 API Key 环境变量
export AMP_API_KEY=your-api-key

# 在脚本中使用
echo "检查代码质量" | amp
```

---

## 基础使用

### 1. 启动 Amp

#### 编辑器中使用

```bash
# VS Code 快捷键
Cmd/Ctrl + L          # 新建线程
Cmd/Ctrl + I          # 显示/隐藏 Amp 侧边栏
Cmd/Ctrl + K          # 切换到线程
Cmd/Ctrl + Enter      # 提交消息
```

#### 命令行使用

```bash
# 启动交互模式
amp

# 直接提问
echo "解释这段代码的作用" | amp

# 带文件输入
cat main.py | amp "优化这段代码"
```

### 2. 基本对话

```bash
# 简单提问
amp
> 你好，请介绍一下你的功能

# 代码相关
amp
> 帮我写一个 Python 函数，实现快速排序

# 项目相关
amp
> 分析当前项目的目录结构并给出优化建议
```

### 3. 文件操作

```bash
# 编辑器中使用 @ 符号引用文件
@README.md 帮我改进这个文档

# 命令行中指定文件
amp "优化这个文件的代码结构" < src/main.js
```

---

## 实操命令大全

### 代码生成与优化

```bash
# 生成代码
amp "写一个 React 组件，实现用户登录表单"

# 优化代码
amp "重构这个函数，提高性能和可读性"

# 代码审查
amp "审查这段代码，找出潜在问题"

# 添加注释
amp "为这个函数添加详细的注释"

# 类型检查
amp "为这个 JavaScript 代码添加 TypeScript 类型"
```

### 调试与修复

```bash
# 调试错误
amp "这个错误是什么原因？如何修复？"

# 运行并修复
amp "运行 npm run build 并修复所有错误"

# 测试相关
amp "为这个函数编写单元测试"

# 性能优化
amp "分析这段代码的性能瓶颈并优化"
```

### 项目管理

```bash
# 项目初始化
amp "初始化一个新的 React 项目"

# 依赖管理
amp "分析并更新 package.json 中的依赖"

# 文档生成
amp "为这个项目生成 README.md 文档"

# 配置文件
amp "创建 ESLint 和 Prettier 配置文件"
```

### Git 操作

```bash
# 提交代码
amp "检查 git diff 并提交更改"

# 分析提交历史
amp "使用 git log 查找添加这个功能的提交"

# 合并冲突
amp "解决这个 Git 合并冲突"

# 代码审查
amp "审查最近的提交，检查代码质量"
```

### 数据库操作

```bash
# 数据库查询
amp "编写 SQL 查询语句来获取用户数据"

# 数据库迁移
amp "创建数据库迁移脚本"

# 数据分析
amp "分析这个数据表的结构并优化"
```

### 部署与运维

```bash
# 构建项目
amp "运行构建命令并修复所有错误"

# 部署配置
amp "创建 Docker 配置文件"

# 环境配置
amp "设置开发环境的配置文件"

# 监控脚本
amp "编写系统监控脚本"
```

---

## 高级功能

### 1. AGENT.md 配置

创建项目根目录下的 `AGENT.md` 文件，为 Amp 提供项目上下文：

```markdown
# 项目配置

## 构建命令
- 构建: `npm run build`
- 测试: `npm run test`
- 启动: `npm run start`
- 代码检查: `npm run lint`

## 项目结构
- `src/` - 源代码目录
- `tests/` - 测试文件目录
- `docs/` - 文档目录

## 编码规范
- 使用 TypeScript
- 遵循 ESLint 规则
- 使用 Prettier 格式化代码
```

### 2. 子代理 (Subagents)

```bash
# 并行处理多个文件
amp "使用子代理同时转换这 5 个文件为 TypeScript"

# 复杂任务分解
amp "创建一个电商网站，使用子代理分别处理前端、后端和数据库"
```

### 3. Oracle 高级推理

```bash
# 复杂问题分析
amp "使用 Oracle 分析这个架构设计是否合理"

# 代码审查
amp "让 Oracle 深度审查这个算法的正确性"

# 性能优化
amp "使用 Oracle 分析系统性能瓶颈"
```

### 4. 团队协作

```bash
# 分享线程
# 在编辑器中点击分享按钮，获取线程链接

# 查看团队活动
# 访问 https://ampcode.com/team 查看团队使用情况

# 协作开发
amp "基于团队的最佳实践，优化这个代码"
```

### 5. 自定义工具 (MCP)

在编辑器设置中配置自定义工具：

```json
{
  "amp.mcpServers": {
    "playwright": {
      "command": "npx",
      "args": ["-y", "@playwright/mcp@latest", "--headless", "--isolated"]
    },
    "linear": {
      "url": "https://mcp.linear.app/sse"
    }
  }
}
```

---

## 最佳实践

### 1. 有效的提示词

**✅ 推荐**
```bash
# 明确具体
amp "实现用户认证功能，包括登录、注册和密码重置"

# 提供上下文
amp "基于 React 和 Node.js 项目，添加实时聊天功能"

# 指定输出格式
amp "只规划如何实现这个功能，不要写代码"
```

**❌ 不推荐**
```bash
# 模糊不清
amp "能帮我吗？"

# 混合任务
amp "同时修改 CSS 样式和数据库结构"
```

### 2. 项目管理

```bash
# 使用 AGENT.md 提供上下文
amp "根据 AGENT.md 的配置，运行项目测试"

# 分解大任务
amp "创建一个完整的博客系统"
# 拆分为：
# 1. 设计数据库结构
# 2. 创建 API 接口
# 3. 实现前端界面
# 4. 添加用户认证
```

### 3. 代码质量

```bash
# 代码审查
amp "审查这次提交的代码，确保符合最佳实践"

# 测试覆盖
amp "为这个模块编写全面的测试用例"

# 文档更新
amp "更新 API 文档，确保与代码同步"
```

### 4. 性能优化

```bash
# 性能分析
amp "分析这个应用的性能瓶颈"

# 代码优化
amp "优化这个查询，提高数据库性能"

# 缓存策略
amp "实现合适的缓存策略"
```

---

## 常见问题

### Q1: 如何开始使用 Amp？

**A:** 最简单的方式是安装 VS Code 扩展：
1. 访问 https://ampcode.com/settings 注册账号
2. 在 VS Code 中搜索并安装 "Amp" 扩展
3. 按提示完成认证即可使用

### Q2: 命令行工具如何使用？

**A:** 
```bash
# 快速开始
npm install -g @sourcegraph/amp
amp

# 或使用 npx（无需安装）
npx @sourcegraph/amp
```

### Q3: 如何提高 Amp 的响应质量？

**A:**
- 使用明确具体的提示词
- 创建 AGENT.md 文件提供项目上下文
- 分解大任务为小任务
- 使用 @ 符号引用特定文件

### Q4: 如何处理复杂任务？

**A:**
```bash
# 使用子代理
amp "使用子代理并行处理这几个独立的任务"

# 使用 Oracle
amp "使用 Oracle 深度分析这个复杂问题"
```

### Q5: 如何管理团队协作？

**A:**
1. 创建团队：访问 https://ampcode.com/team
2. 邀请成员加入团队
3. 分享有用的线程链接
4. 查看团队活动排行榜

### Q6: 如何控制使用成本？

**A:**
- Amp 使用预付费模式，不会超额收费
- 新用户通常获得 $10 免费额度
- 可以在设置中查看使用情况
- 团队使用可以集中管理账单

### Q7: 如何处理网络代理问题？

**A:**
```bash
# 设置代理环境变量
export HTTP_PROXY=your-proxy-url
export HTTPS_PROXY=your-proxy-url
export NODE_EXTRA_CA_CERTS=/path/to/certificates.pem
```

### Q8: 如何启用 Amp Tab 代码补全？

**A:**
在编辑器设置中添加：
```json
{
  "amp.tab.enabled": true
}
```

---

## 🚀 快速开始清单

- [ ] 注册 Amp 账号
- [ ] 安装编辑器扩展或命令行工具
- [ ] 尝试第一个简单对话
- [ ] 创建 AGENT.md 文件
- [ ] 学习基本快捷键
- [ ] 尝试文件操作和代码生成
- [ ] 探索高级功能

---

## 📞 获取帮助

- **官方文档**: https://ampcode.com/manual
- **Discord 社区**: https://discord.gg/amp
- **账单问题**: amp-billing-help@sourcegraph.com
- **企业咨询**: amp-devs@sourcegraph.com

---

*最后更新: 2025年1月*

> 💡 **提示**: 这个手册会根据 Amp 的更新而持续改进。如果发现任何问题或有改进建议，请随时反馈！
