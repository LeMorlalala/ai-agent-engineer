# Day 3: Claude Code - AI 编程助手的极致体验

> Anthropic 出品的 AI 编程利器

## 什么是 Claude Code？

**Claude Code** 是 Anthropic 推出的 AI 编程助手，它可以：
- 读取你的代码库
- 编辑文件
- 运行命令
- 集成开发工具

```mermaid
flowchart TB
    subgraph Claude Code 核心能力
        R[读取代码]
        E[编辑文件]
        C[运行命令]
        I[集成工具]
    end
    
    subgraph 支持环境
        T[终端]
        V[VS Code]
        D[桌面应用]
        B[浏览器]
        J[JetBrains]
    end
    
    R --> T
    E --> V
    C --> D
    I --> B
    I --> J
```

## 安装 Claude Code

### macOS / Linux / WSL

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

### Windows PowerShell

```powershell
irm https://claude.ai/install.ps1 | iex
```

### Homebrew

```bash
brew install --cask claude-code
```

### 启动使用

```bash
cd your-project
claude
```

## Claude Code 能做什么？

### 1. 自动化繁琐任务

```bash
# 让 Claude Code 帮你写测试并修复
claude "write tests for the auth module, run them, and fix any failures"
```

自动完成：
- 编写测试代码
- 运行测试
- 修复失败用例

### 2. 构建功能和修复 Bug

```mermaid
flowchart LR
    A[描述需求] --> B[规划方案]
    B --> C[编写代码]
    C --> D[多文件修改]
    D --> E[验证运行]
```

只需用自然语言描述：
- "添加用户登录功能"
- "修复这个数组越界错误"
- "重构这个组件"

Claude Code 会：
- 规划实现方案
- 跨文件编写代码
- 验证功能正常

### 3. Git 操作自动化

```bash
# 自动创建提交
claude "commit my changes with a descriptive message"

# 创建分支并提交
claude "create a new feature branch and commit my changes"

# 创建 PR
claude "create a pull request for the new feature"

# 交互式 rebase
claude "rebase onto main and fix conflicts"
```

### 4. 项目理解与分析

```bash
# 理解项目结构
claude "explain this project's architecture"

# 分析依赖关系
claude "show me the dependency graph"

# 查找代码位置
claude "where is the user authentication logic"
```

### 5. MCP 集成

Claude Code 支持 **MCP (Model Context Protocol)**，可以连接各种外部工具：

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/directory"]
    },
    "github": {
      "command": "npx", 
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_TOKEN": "your-token"
      }
    },
    "postgres": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-postgres"],
      "env": {
        "DATABASE_URL": "postgresql://user:pass@localhost/db"
      }
    }
  }
}
```

## Claude Code 实战

### 项目初始化

```bash
# 克隆项目后，让 Claude Code 了解项目结构
claude "explain this project's architecture and dependencies"
```

Claude Code 会分析：
- 项目结构
- 依赖关系
- 技术栈

### 代码审查

```bash
# 让 Claude Code 审查 PR
claude "review this pull request for security issues and best practices"
```

### 错误排查

```bash
# 粘贴错误信息，让 Claude Code 定位问题
claude "fix this error: [paste error message]"
```

Claude Code 会：
- 追踪错误根源
- 定位相关代码
- 提供修复方案

## Claude Code vs 其他工具对比

| 特性 | Claude Code | Cursor | GitHub Copilot |
|------|-------------|--------|----------------|
| **交互方式** | 对话式 | 对话式 | 补全式 |
| **代码编辑** | ✅ | ✅ | ❌ |
| **命令执行** | ✅ | ✅ | ❌ |
| **MCP 支持** | ✅ | ✅ | ❌ |
| **多文件修改** | ✅ | ✅ | ❌ |
| **终端集成** | ✅ | ❌ | ❌ |

## Claude Code 的工作模式

```mermaid
sequenceDiagram
    participant User as 用户
    participant Claude as Claude Code
    participant Tools as 工具集
    participant LLM as Claude LLM
    
    User->>Claude: 自然语言指令
    Claude->>LLM: 分析任务
    LLM-->>Claude: 执行计划
    
    loop 执行步骤
        Claude->>Tools: 调用工具
        Tools-->>Claude: 返回结果
        Claude->>LLM: 评估结果
    end
    
    Claude-->>User: 返回完成状态
```

## 高级技巧

### 1. 使用 CLAUDE.md 定义项目规范

在项目根目录创建 `CLAUDE.md`：

```markdown
# 项目规范

## 代码风格
- 使用 ESLint
- Prettier 格式化
- TypeScript 严格模式

## 目录结构
- /src/components - 组件
- /src/hooks - 自定义 Hooks
- /src/utils - 工具函数

## 测试要求
- 组件需要 Storybook stories
- 工具函数需要单元测试
```

### 2. 使用 Artifacts 生成内容

```bash
# 让 Claude Code 生成文档或网站
claude "create an API documentation page for this project"
```

### 3. 调度周期性任务

在桌面应用中，你可以：
- 安排周期性任务
- 并行运行多个任务
- 云端会话

## Claude Code 在 AI Agent 开发中的应用

```mermaid
flowchart LR
    subgraph 开发流程
        D1[需求分析] --> D2[代码生成]
        D2 --> D3[测试验证]
        D3 --> D4[部署上线]
    end
    
    subgraph Claude Code 能力
        C1[理解需求] --> C2[编写代码]
        C2 --> C3[运行测试]
        C3 --> C4[执行部署]
    end
    
    D1 --> C1
    D2 --> C2
    D3 --> C3
    D4 --> C4
```

Claude Code 可以帮助你：
1. **理解需求** - 分析你的功能描述
2. **编写代码** - 生成高质量代码
3. **运行测试** - 验证功能正确
4. **执行部署** - 自动化部署流程

## 明日预告

**Day 4: LangGraph - 生产级 AI Agent 的构建框架**

明天我们将深入了解 LangGraph，学习如何构建可靠、可观测、可部署的 AI Agent！

---

*关注我们，每天学习 AI Agent 开发知识！从 UI 工程师转型 AI Agent 工程师！*
