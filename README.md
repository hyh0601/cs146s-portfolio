# CS146S 学习作品集

跟随 Stanford **CS146S: The Modern Software Developer**（2026 版）的学习记录与动手作品。

主线不是"看完课程"，而是回答一个问题：**当写代码的从人变成 agent，我还需要会什么、怎么验证它做对了。**

## 作品

| 作品 | 内容 | 状态 |
|---|---|---|
| [unit-test-lab](https://github.com/hyh0601/unit-test-lab) | 手写函数 + 测试，走通 红 → 绿 → 红，理解"测试是 agent 的反馈信号" | ✅ |
| [http-lab](https://github.com/hyh0601/http-lab) | 手写 HTTP echo server；用 mitmproxy 拦下 Claude Code 的真实请求并逐层拆解 | ✅ |
| [cs146s-lab](https://github.com/hyh0601/cs146s-lab) | W1 抓包用的练手仓库：版本号解析 + 测试，在代理下让 agent 完整走一遍"撞红 → 诊断 → 计划 → 修复" | ✅ |
| W2 · MCP server | 给第三方 API 写 MCP server（OAuth + ≥3 个可串联工具） | ☐ |
| W3 · Skill | 把一个反复手打的提示词沉淀成 skill | ☐ |
| W4 · AGENTS.md | 让一个陌生开源仓库变成 agent-ready | ☐ |
| W5 · 就绪度报告 | 横评 3 个仓库的 agent-readiness | ☐ |

## 目录里的 writeup

每周作业的判断、踩坑和"我会改成不同做法的地方"都写在 `writeups/` 下：

- [`writeups/w1.md`](writeups/w1.md) — 拆解一次真实的 Claude Code 会话：14 条 `POST /v1/messages`，从 `system` 六段结构到工具 schema 取舍，再到缓存命中与失效的实测数据 ✅

## 一个例子：为什么要先把地基补上

W1 卡住时以为缺的是 agent 知识，实际缺的是 HTTP、git、单元测试。补完这三块之后再看抓到的请求，`system` / `tools` / `messages` 三层才读得懂。

结论记在这里：**agent 写代码不会让地基消失，只会让"地基没打牢"暴露得更快。**

## 环境

macOS + conda（`cs146s`, Python 3.12）+ Poetry + mitmproxy。抓包文件（含鉴权头）一律不进仓库，`.gitignore` 按 `*.flows` 全后缀排除。
