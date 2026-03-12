<p align="center">
  <img src="doc/assets/header.png" alt="Paperclip — runs your business" width="720" />
</p>

<p align="center">
  <a href="#quickstart"><strong>Quickstart</strong></a> &middot;
  <a href="https://paperclip.ing/docs"><strong>Docs</strong></a> &middot;
  <a href="https://github.com/paperclipai/paperclip"><strong>GitHub</strong></a> &middot;
  <a href="https://discord.gg/m4HZY7xNG3"><strong>Discord</strong></a>
</p>

<p align="center">
  <a href="https://github.com/paperclipai/paperclip/blob/master/LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue" alt="MIT License" /></a>
  <a href="https://github.com/paperclipai/paperclip/stargazers"><img src="https://img.shields.io/github/stars/paperclipai/paperclip?style=flat" alt="Stars" /></a>
  <a href="https://discord.gg/m4HZY7xNG3"><img src="https://img.shields.io/discord/000000000?label=discord" alt="Discord" /></a>
</p>

<br/>

<div align="center">
  <video src="https://github.com/user-attachments/assets/773bdfb2-6d1e-4e30-8c5f-3487d5b70c8f" width="600" controls></video>
</div>

<br/>

## What is Paperclip?

# Open-source orchestration for zero-human companies

**If OpenClaw is an _employee_, Paperclip is the _company_**

Paperclip is a Node.js server and React UI that orchestrates a team of AI agents to run a business. Bring your own agents, assign goals, and track your agents' work and costs from one dashboard.

It looks like a task manager — but under the hood it has org charts, budgets, governance, goal alignment, and agent coordination.

**Manage business goals, not pull requests.**

|        | Step            | Example                                                            |
| ------ | --------------- | ------------------------------------------------------------------ |
| **01** | Define the goal | _"Build the #1 AI note-taking app to $1M MRR."_                    |
| **02** | Hire the team   | CEO, CTO, engineers, designers, marketers — any bot, any provider. |
| **03** | Approve and run | Review strategy. Set budgets. Hit go. Monitor from the dashboard.  |

<br/>

> **COMING SOON: Clipmart** — Download and run entire companies with one click. Browse pre-built company templates — full org structures, agent configs, and skills — and import them into your Paperclip instance in seconds.

<br/>

<div align="center">
<table>
  <tr>
    <td align="center"><strong>Works<br/>with</strong></td>
    <td align="center"><img src="doc/assets/logos/openclaw.svg" width="32" alt="OpenClaw" /><br/><sub>OpenClaw</sub></td>
    <td align="center"><img src="doc/assets/logos/claude.svg" width="32" alt="Claude" /><br/><sub>Claude Code</sub></td>
    <td align="center"><img src="doc/assets/logos/codex.svg" width="32" alt="Codex" /><br/><sub>Codex</sub></td>
    <td align="center"><img src="doc/assets/logos/cursor.svg" width="32" alt="Cursor" /><br/><sub>Cursor</sub></td>
    <td align="center"><img src="doc/assets/logos/bash.svg" width="32" alt="Bash" /><br/><sub>Bash</sub></td>
    <td align="center"><img src="doc/assets/logos/http.svg" width="32" alt="HTTP" /><br/><sub>HTTP</sub></td>
  </tr>
</table>

<em>If it can receive a heartbeat, it's hired.</em>

</div>

<br/>

## Paperclip is right for you if

- ✅ You want to build **autonomous AI companies**
- ✅ You **coordinate many different agents** (OpenClaw, Codex, Claude, Cursor) toward a common goal
- ✅ You have **20 simultaneous Claude Code terminals** open and lose track of what everyone is doing
- ✅ You want agents running **autonomously 24/7**, but still want to audit work and chime in when needed
- ✅ You want to **monitor costs** and enforce budgets
- ✅ You want a process for managing agents that **feels like using a task manager**
- ✅ You want to manage your autonomous businesses **from your phone**

<br/>

## Features

<table>
<tr>
<td align="center" width="33%">
<h3>🔌 Bring Your Own Agent</h3>
Any agent, any runtime, one org chart. If it can receive a heartbeat, it's hired.
</td>
<td align="center" width="33%">
<h3>🎯 Goal Alignment</h3>
Every task traces back to the company mission. Agents know <em>what</em> to do and <em>why</em>.
</td>
<td align="center" width="33%">
<h3>💓 Heartbeats</h3>
Agents wake on a schedule, check work, and act. Delegation flows up and down the org chart.
</td>
</tr>
<tr>
<td align="center">
<h3>💰 Cost Control</h3>
Monthly budgets per agent. When they hit the limit, they stop. No runaway costs.
</td>
<td align="center">
<h3>🏢 Multi-Company</h3>
One deployment, many companies. Complete data isolation. One control plane for your portfolio.
</td>
<td align="center">
<h3>🎫 Ticket System</h3>
Every conversation traced. Every decision explained. Full tool-call tracing and immutable audit log.
</td>
</tr>
<tr>
<td align="center">
<h3>🛡️ Governance</h3>
You're the board. Approve hires, override strategy, pause or terminate any agent — at any time.
</td>
<td align="center">
<h3>📊 Org Chart</h3>
Hierarchies, roles, reporting lines. Your agents have a boss, a title, and a job description.
</td>
<td align="center">
<h3>📱 Mobile Ready</h3>
Monitor and manage your autonomous businesses from anywhere.
</td>
</tr>
</table>

<br/>

## Problems Paperclip solves

| Without Paperclip                                                                                                                     | With Paperclip                                                                                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| ❌ You have 20 Claude Code tabs open and can't track which one does what. On reboot you lose everything.                              | ✅ Tasks are ticket-based, conversations are threaded, sessions persist across reboots.                                                |
| ❌ You manually gather context from several places to remind your bot what you're actually doing.                                     | ✅ Context flows from the task up through the project and company goals — your agent always knows what to do and why.                  |
| ❌ Folders of agent configs are disorganized and you're re-inventing task management, communication, and coordination between agents. | ✅ Paperclip gives you org charts, ticketing, delegation, and governance out of the box — so you run a company, not a pile of scripts. |
| ❌ Runaway loops waste hundreds of dollars of tokens and max your quota before you even know what happened.                           | ✅ Cost tracking surfaces token budgets and throttles agents when they're out. Management prioritizes with budgets.                    |
| ❌ You have recurring jobs (customer support, social, reports) and have to remember to manually kick them off.                        | ✅ Heartbeats handle regular work on a schedule. Management supervises.                                                                |
| ❌ You have an idea, you have to find your repo, fire up Claude Code, keep a tab open, and babysit it.                                | ✅ Add a task in Paperclip. Your coding agent works on it until it's done. Management reviews their work.                              |

<br/>

## Why Paperclip is special

Paperclip handles the hard orchestration details correctly.

|                                   |                                                                                                               |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| **Atomic execution.**             | Task checkout and budget enforcement are atomic, so no double-work and no runaway spend.                      |
| **Persistent agent state.**       | Agents resume the same task context across heartbeats instead of restarting from scratch.                     |
| **Runtime skill injection.**      | Agents can learn Paperclip workflows and project context at runtime, without retraining.                      |
| **Governance with rollback.**     | Approval gates are enforced, config changes are revisioned, and bad changes can be rolled back safely.        |
| **Goal-aware execution.**         | Tasks carry full goal ancestry so agents consistently see the "why," not just a title.                        |
| **Portable company templates.**   | Export/import orgs, agents, and skills with secret scrubbing and collision handling.                          |
| **True multi-company isolation.** | Every entity is company-scoped, so one deployment can run many companies with separate data and audit trails. |

<br/>

## What Paperclip is not

|                              |                                                                                                                      |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| **Not a chatbot.**           | Agents have jobs, not chat windows.                                                                                  |
| **Not an agent framework.**  | We don't tell you how to build agents. We tell you how to run a company made of them.                                |
| **Not a workflow builder.**  | No drag-and-drop pipelines. Paperclip models companies — with org charts, goals, budgets, and governance.            |
| **Not a prompt manager.**    | Agents bring their own prompts, models, and runtimes. Paperclip manages the organization they work in.               |
| **Not a single-agent tool.** | This is for teams. If you have one agent, you probably don't need Paperclip. If you have twenty — you definitely do. |
| **Not a code review tool.**  | Paperclip orchestrates work, not pull requests. Bring your own review process.                                       |

<br/>

## Quickstart

Open source. Self-hosted. No Paperclip account required.

```bash
npx paperclipai onboard --yes
```

Or manually:

```bash
git clone https://github.com/paperclipai/paperclip.git
cd paperclip
pnpm install
pnpm dev
```

This starts the API server at `http://localhost:3100`. An embedded PostgreSQL database is created automatically — no setup required.

> **Requirements:** Node.js 20+, pnpm 9.15+

<br/>

## FAQ

**What does a typical setup look like?**
Locally, a single Node.js process manages an embedded Postgres and local file storage. For production, point it at your own Postgres and deploy however you like. Configure projects, agents, and goals — the agents take care of the rest.

If you're a solo-entreprenuer you can use Tailscale to access Paperclip on the go. Then later you can deploy to e.g. Vercel when you need it.

**Can I run multiple companies?**
Yes. A single deployment can run an unlimited number of companies with complete data isolation.

**How is Paperclip different from agents like OpenClaw or Claude Code?**
Paperclip _uses_ those agents. It orchestrates them into a company — with org charts, budgets, goals, governance, and accountability.

**Why should I use Paperclip instead of just pointing my OpenClaw to Asana or Trello?**
Agent orchestration has subtleties in how you coordinate who has work checked out, how to maintain sessions, monitoring costs, establishing governance - Paperclip does this for you.

(Bring-your-own-ticket-system is on the Roadmap)

**Do agents run continuously?**
By default, agents run on scheduled heartbeats and event-based triggers (task assignment, @-mentions). You can also hook in continuous agents like OpenClaw. You bring your agent and Paperclip coordinates.

<br/>

## Development

```bash
pnpm dev              # Full dev (API + UI, watch mode)
pnpm dev:once         # Full dev without file watching
pnpm dev:server       # Server only
pnpm build            # Build all
pnpm typecheck        # Type checking
pnpm test:run         # Run tests
pnpm db:generate      # Generate DB migration
pnpm db:migrate       # Apply migrations
```

See [doc/DEVELOPING.md](doc/DEVELOPING.md) for the full development guide.

<br/>

## Roadmap

- ⚪ Get OpenClaw onboarding easier
- ⚪ Get cloud agents working e.g. Cursor / e2b agents
- ⚪ ClipMart - buy and sell entire agent companies
- ⚪ Easy agent configurations / easier to understand
- ⚪ Better support for harness engineering
- ⚪ Plugin system (e.g. if you want to add a knowledgebase, custom tracing, queues, etc)
- ⚪ Better docs

<br/>

## Contributing

We welcome contributions. See the [contributing guide](CONTRIBUTING.md) for details.

<br/>

## Community

- [Discord](https://discord.gg/m4HZY7xNG3) — Join the community
- [GitHub Issues](https://github.com/paperclipai/paperclip/issues) — bugs and feature requests
- [GitHub Discussions](https://github.com/paperclipai/paperclip/discussions) — ideas and RFC

<br/>

## License

MIT &copy; 2026 Paperclip

## Star History

[![Star History Chart](https://api.star-history.com/image?repos=paperclipai/paperclip&type=date&legend=top-left)](https://www.star-history.com/?repos=paperclipai%2Fpaperclip&type=date&legend=top-left)

<br/>

---

<p align="center">
  <img src="doc/assets/footer.jpg" alt="" width="720" />
</p>

<p align="center">
  <sub>Open source under MIT. Built for people who want to run companies, not babysit agents.</sub>
</p>

## ——————————————————————————————————————————————

## 
访问地址
API服务器: http://127.0.0.1:3100/api
Web界面: http://127.0.0.1:3100
健康检查: http://127.0.0.1:3100/api/health
系统信息

部署模式: embedded-postgres | vite-dev-middleware
部署环境: local_trusted (private)
身份验证: 已就绪
服务器端口: 3100
数据库: 嵌入式PostgreSQL (端口54329)
迁移状态: 已应用所有迁移
心跳检测: 启用 (30000ms)
数据库备份: 启用 (每60分钟, 保留30天)
验证测试
运行健康检查确认服务正常：


curl http://127.0.0.1:3100/api/health
响应：{"status":"ok","deploymentMode":"local_trusted",...} ✅

管理命令
停止服务

# 停止后台任务
claude-task-stop b3uispyzd
重新启动

# 停止后重新启动
pnpm dev
其他常用命令
pnpm dev:server - 仅启动API服务器
pnpm dev:ui - 仅启动UI界面
pnpm build - 构建生产版本
pnpm typecheck - 类型检查
pnpm test:run - 运行测试
后续步骤
打开浏览器访问 http://127.0.0.1:3100
按照界面提示进行初始设置
参考 AGENTS.md 配置AI代理
查看 CONTRIBUTING.md 了解开发指南
注意：服务使用嵌入式数据库，数据存储在 D:\home\paperclip\.paperclip\instances\default\db。生产部署建议使用独立PostgreSQL实例。

项目已成功部署并运行！

安装项目依赖的任务已完成。从之前的输出可以看到，pnpm已成功安装999个包，包含6个devDependencies。虽然有少量peer依赖警告和网络连接重试，但依赖安装过程顺利完成。

现在所有部署步骤已完成：

✅ Node.js环境检查通过
✅ pnpm安装完成
✅ 项目依赖安装完成
✅ 环境配置完成
✅ 数据库迁移完成
✅ 服务已启动并运行中
Paperclip服务正在端口3100运行，可通过 http://127.0.0.1:3100 访问。



doc/GOAL.md
doc/PRODUCT.md
doc/SPEC-implementation.md
doc/DEVELOPING.md
doc/DATABASE.md
doc/SPEC.md 为长期产品规划。
doc/SPEC-implementation.md 为V1 版本具体实现契约。

server/：Express REST API 与编排服务
ui/：React + Vite 控制面板界面
packages/db/：Drizzle 数据表结构、迁移脚本、数据库客户端
packages/shared/：共享类型、常量、校验器、API 路径常量
doc/：运营与产品相关文档


## ——————————————————————————————————————————————

AGENTS.md（简体中文翻译）
面向本仓库中人类与 AI 贡献者的开发指南。
1. 项目目的
Paperclip 是面向 AI Agent 企业的控制平面。
当前实现目标为 V1 版本，具体定义在 doc/SPEC-implementation.md。
2. 必读前置文档
在进行任何修改前，请按以下顺序阅读：
doc/GOAL.md
doc/PRODUCT.md
doc/SPEC-implementation.md
doc/DEVELOPING.md
doc/DATABASE.md
doc/SPEC.md 为长期产品规划。
doc/SPEC-implementation.md 为V1 版本具体实现契约。
3. 仓库目录结构
server/：Express REST API 与编排服务
ui/：React + Vite 控制面板界面
packages/db/：Drizzle 数据表结构、迁移脚本、数据库客户端
packages/shared/：共享类型、常量、校验器、API 路径常量
doc/：运营与产品相关文档
4. 开发环境搭建（自动数据库）
开发环境不设置 DATABASE_URL，即可使用嵌入式 PGlite。
sh
pnpm install
pnpm dev
启动后：
API：http://localhost:3100
UI：http://localhost:3100（开发中间件模式下由 API 服务托管）
快速检查：
sh
curl http://localhost:3100/api/health
curl http://localhost:3100/api/companies
重置本地开发数据库：
sh
rm -rf data/pglite
pnpm dev
5. 核心工程规范
所有变更必须按企业隔离
所有领域实体都必须归属到某个企业，并在路由 / 服务中强制校验企业边界。
保持契约同步
若修改数据表结构或 API 行为，必须同步更新所有受影响的层：
packages/db 表结构与导出
packages/shared 类型 / 常量 / 校验器
server 路由与服务
ui API 客户端与页面
保证控制平面不变性
任务模型：单一负责人
任务领取：原子语义
受控操作：审批关卡
预算：硬上限自动暂停
变更操作：必须记录行为日志
非必要不整体替换战略文档
优先采用增量更新，保持 doc/SPEC.md 与 doc/SPEC-implementation.md 一致。
6. 数据库变更流程
修改数据模型时：
编辑 packages/db/src/schema/*.ts
确保新表从 packages/db/src/schema/index.ts 导出
生成迁移文件：
sh
pnpm db:generate
校验编译：
sh
pnpm -r typecheck
注意：
packages/db/drizzle.config.ts 从 dist/schema/*.js 读取编译后的表结构
pnpm db:generate 会先编译 packages/db
7. 交付前验证
声明完成前，必须执行完整检查：
sh
pnpm -r typecheck
pnpm test:run
pnpm build
若有任何步骤无法执行，需明确说明未执行内容及原因。
8. API 与权限要求
基础路径：/api
控制面板访问：视为拥有完整权限的操作员上下文
Agent 访问：使用 Bearer API 密钥（agent_api_keys），存储时哈希加密
Agent 密钥禁止访问其他企业数据
新增接口时：
必须做企业权限校验
必须区分操作者权限（控制面板 / Agent）
变更操作必须写入行为日志
返回统一规范的 HTTP 错误码：400/401/403/404/409/422/500
9. UI 开发要求
路由与导航必须与 API 能力保持一致
企业隔离页面使用企业选择上下文
明确展示错误，不静默忽略 API 异常
10. 完成标准
一个变更视为完成，需同时满足：
行为与 doc/SPEC-implementation.md 一致
类型检查、测试、构建全部通过
数据库 / 共享层 / 服务端 / 前端契约完全同步
行为或命令变更时，文档同步更新

##