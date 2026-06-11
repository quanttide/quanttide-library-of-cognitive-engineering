# depict

> 更好地分享心智模型的工具

## 基本信息

| 项目 | 内容 |
|------|------|
| 仓库 | [mstone/depict](https://github.com/mstone/depict) |
| 语言 | Rust |
| 许可证 | MIT |
| ⭐ | 41 |
| 官网 | https://mstone.info/depict/ |

## 是什么

depict 是一个从**速记符号**自动生成心智模型图的工具。使用者用一套专门设计的简写语法来描述系统中的参与者和交互关系，depict 实时渲染为可阅读的图示。

核心工作流：

```
访谈 / 分析
   ↓ 速记
简写笔记（shorthand notes）
   ↓ depict 实时渲染
心智模型图（图片）
   ↓ 与利益相关者评审
达成共识的共享心智模型
   ↓ 自动输出
可版本化、可复用的文字转录
```

## 解决了什么问题

传统的心智模型绘制工具在访谈场景中有几个痛点：

| 痛点 | depict 的解法 |
|------|-------------|
| 绘图打断访谈"流" | 用文字速记代替拖拽绘图，不打断思考 |
| 箭头交叉/碰撞 | 自动布局，无需手动调整 |
| 图片脆弱、不可版本化 | 输入是纯文本，天然可 diff、可版本化 |
| 难以复用和维护 | 修改速记笔记即可重新生成，不需重绘 |

## 速记语法示例

```
person microwave food: open, start, stop / beep : heat
person food: eat
```

表达的意思是：
- 三个实体：person、microwave、food
- person → microwave：open、start、stop（下箭头 = 控制动作）
- microwave → person：beep（上箭头 = 反馈）
- microwave → food：heat（动作）
- person → food：eat（直接关系）

关系方向约定：
- 下箭头 = 控制 / 权威
- 上箭头 = 反馈
- 右箭头 = 同级请求
- 左箭头 = 结果 / 回复
- 嵌套 = 抽象 / 分解 / 平台与承载进程的关系

## 与量潮 lab 的关系

depict 和 lab 在做同一件事——**将隐性知识结构化**——但用不同的方式：

| | depict | lab schema migration |
|--|--------|---------------------|
| 输入 | 访谈速记 | journal 日志 |
| 中间形式 | 简写语法 | schema 七要素 |
| 输出 | 可视化图示 | YAML schema → PoC 方案 |
| 核心价值 | 实时、不打断 | 可追溯、可验证 |

**两者的互补性：** lab 产出的 schema 如果能在 depict 中可视化为关系图，会比 YAML 文件更容易和客户沟通。depict 的简写语法也可以作为 lab 「数据接入」阶段的一种补充输入方式——访谈记录直接以 depict 语法录入，而不是先写 journal 再转 schema。

## 关键文献

- [Introducing depict](https://mstone.info/posts/introducing-depict/) — 设计理念
- [Real-world system depictions with depict](https://mstone.info/posts/real-world-system-depictions/) — 实际案例
