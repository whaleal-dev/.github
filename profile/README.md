# Whaleal

> 把已经流失的订单找回来，再让每一条消息真正发出去。
> 一边做 Shopify 弃购挽回，一边把短信 / 邮件 / WhatsApp 收发做扎实 —— 用的都是**你自己的供应商账号**。
> 同时维护一组开源 Java SDK，让发短信、接大模型、同步数据这类事情回归简单。

官网：https://www.whaleal.com

## 商家产品

- **Whaleal Cart** — Shopify 弃购挽回：定时邮件序列（默认约 1 小时、约 24 小时两封）+ 可选的单次短信，配原生 Shopify 折扣码，装完不用日常打理。
  折扣决策层**三档都有**、**默认关闭**：打开后先只给建议（`advise`），你确认后才真正参与发送判定（`active`），而且只能把折扣**收紧**、不会把你自己关掉的折扣打开。Growth / Pro 档另可选 AI 邮件草稿 —— 只写主题、标题与开头三段，生成后要你手动启用。
  https://cart.whaleal.com · [Shopify App Store](https://apps.shopify.com/whaleal-cart)

- **Whaleal Messaging** — 自持账号（BYOL）的消息编排层：在控制台把**你自己的** SMS / 邮件 / WhatsApp 账号接进来，拿到一个发送日志、一套回执口径、一份按通道隔离的抑制名单。**我们不是 BSP、不持有通道资质、不转卖消息额度、不在供应商账单上加价 —— 消息费你直接付给供应商，平台只收订阅费。**
  https://app.whaleal.com

  Cart 与 Messaging 是两条产品线：Cart 负责把弃购找回来，Messaging 负责让消息可靠地发出去。Cart 的短信通过 Whaleal Messaging 走商家自己的短信账号 —— 所以那部分额度、费率与合规仍然在商家与自己的供应商之间。

  现在可自助接入的三通道（控制台里点「Add connection」即可，不需要联系销售）：

  | 通道 | 供应商 |
  |------|--------|
  | SMS | Twilio、Vonage、Infobip、MessageBird、Plivo、AWS End User Messaging |
  | Email | Resend、Mailgun、SendGrid、Postmark |
  | WhatsApp | Meta、360dialog、Twilio |

  **三个通道一致的部分**：发送、消息日志、按通道隔离的抑制检查、统一错误码，以及同一套 API Key 与开放接口（靠 `channel` 参数指定走哪条）。

  **只有 SMS 才有的部分**：跨账号自动故障切换（一条失败换下一条重试）、按发信号码限速与轮询、分段与编码**记账**（GSM-7 / UCS-2，段数留在消息记录里、供你对上游账单）、**STOP / HELP / START 回信自动写名单**，以及批量与计划发送。

  **按供应商、而非按通道的部分**：回执只有已经接了入站端点的供应商推得回来 —— 短信全部、Resend（邮件）、Meta（WhatsApp）；Mailgun / SendGrid / Postmark 与 360dialog / Twilio WhatsApp 目前只记录受理结果与错误码。抑制名单在控制台按通道可见、可解除，但**新增只有短信那条关键词链路**，邮件与 WhatsApp 侧还没有写入者。

  **不做的部分**：模板变量渲染；邮件 / WhatsApp 的附件与 HTML；自动跨通道路由或降级；代你提交供应商侧审批（WABA 资质、号码申请、模板审核都在 BSP 后台完成）。三家 WhatsApp 目前只发文本，出 24 小时会话窗口所需的模板要在 BSP 侧备好。

  上面这些是快照，**权威来源是控制台本身**：https://www.whaleal.com/integrations/

- **Whaleal Support** — 工单与知识库（Beta）。
  https://support.whaleal.com

## 开源项目（Java SDK）

| 项目 | 说明 |
|------|------|
| [quick-sms](https://github.com/whaleal-dev/quick-sms) | 多供应商短信聚合 SDK：统一 API 完成发信、回执与上行 |
| [aihub](https://github.com/whaleal-dev/aihub) | 面向 JDK 8+ 的 Java 大模型客户端，统一各厂商 HTTP / SSE API |
| [mongo-sync](https://github.com/whaleal-dev/mongo-sync) | MongoDB 文档同步 SDK：全量 + 增量、DDL 跟随与数据校验 |
| [rds-sync](https://github.com/whaleal-dev/rds-sync) | 关系型数据库同步 SDK：MySQL / Oracle / PostgreSQL 全量与增量 |
| [alpha4j](https://github.com/whaleal-dev/alpha4j) | 纯 Java 实现的 Stocks Alpha SDK（Qlib / WorldQuant Alpha101 系） |

## 线上服务

| 服务 | 地址 | 说明 |
|------|------|------|
| 官网 | https://www.whaleal.com | 品牌与产品入口 |
| 文档中心 | https://docs.whaleal.com | 技术文档中心，子项目文档自动按 projectname 路径聚合 |
| Whaleal Cart | https://cart.whaleal.com | 弃购挽回与结账事件 |
| Whaleal Messaging | https://app.whaleal.com | 三通道连接、发送、回执与消息日志 |
| Whaleal Support | https://support.whaleal.com | 工单与知识库（Beta） |
| 账户管理端 | https://account.whaleal.com | 用户与权限管理后台 |

> `whaleal.com` 会 301 到 `www.whaleal.com`，两个地址都能用。

## 文档中心

各子项目文档会自动聚合到 `docs.whaleal.com`，路径使用 projectname：

- https://docs.whaleal.com/quick-sms/
- https://docs.whaleal.com/aihub/

## 参与贡献

欢迎提交 Issue 和 PR。各仓库的贡献指南见仓库内 `CONTRIBUTING.md`。

## 联系

- 邮箱：support@mail.whaleal.com
- 工单与知识库：https://support.whaleal.com
