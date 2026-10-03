# Whaleal

> 帮 Shopify 商家找回弃购订单、触达客户 —— 装得轻、装完就忘，账单直接在 Shopify 里结。  
> 同时维护一组开源 Java SDK，让发短信、接大模型、同步数据这类事情回归简单。

官网：https://whaleal.com

## 商家产品（Shopify）

- **Whaleal Cart** — AI 弃购挽回：AI 挽回邮件 + 原生 Shopify 折扣码，安装后无需日常打理。  
  https://cart.whaleal.com · [Shopify App Store](https://apps.shopify.com/whaleal-cart)
- **Whaleal SMS** — 多通道短信：同一套 API 对接 Twilio、阿里云、腾讯云等通道，按成本或到达率自动切换，适合跨境与多地区店铺。  
  https://sms.whaleal.com
- **Whaleal Support** — 工单与知识库（Beta）。  
  https://support.whaleal.com

> 我们正在把 Whaleal SMS 接入 Whaleal Cart 的挽回流程，之后同一套挽回序列可以同时走邮件与短信。

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
| 官网 | https://whaleal.com | 品牌与产品入口 |
| 文档中心 | https://docs.whaleal.com | 技术文档中心，子项目文档自动按 projectname 路径聚合 |
| Whaleal Cart | https://cart.whaleal.com | 弃购挽回与结账事件 |
| Whaleal SMS | https://sms.whaleal.com | 多通道短信发送、回执、上行 |
| Whaleal Support | https://support.whaleal.com | 工单与知识库（Beta） |
| 账户管理端 | https://account.whaleal.com | 用户与权限管理后台 |

## 文档中心

各子项目文档会自动聚合到 `docs.whaleal.com`，路径使用 projectname：

- https://docs.whaleal.com/quick-sms/
- https://docs.whaleal.com/aihub/

## 参与贡献

欢迎提交 Issue 和 PR。各仓库的贡献指南见仓库内 `CONTRIBUTING.md`。

## 联系

- 邮箱：support@mail.whaleal.com
- 工单与知识库：https://support.whaleal.com
