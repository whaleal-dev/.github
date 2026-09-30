# Whaleal Commerce

> Shopify e-commerce apps and merchant tools.  
> 帮助商家提升转化、找回流失用户、自动化日常运营。

官网：https://whaleal.com

## 我们做什么

Whaleal Commerce 为 Shopify 商家提供一套开源、可自托管的电商工具。  
核心围绕三件事：

- **提升转化**：优化购物车与结账流程，减少放弃购物车
- **找回用户**：通过短信和自动化流程触达流失用户
- **自动化运营**：把重复的商家操作交给工具处理

## 线上服务

| 服务 | 地址 | 说明 |
|------|------|------|
| 官网 | https://whaleal.com | 品牌与产品入口 |
| 文档中心 | https://docs.whaleal.com | 技术文档中心，子项目文档自动添加 projectname 路径 |
| SMS 服务 | https://sms.whaleal.com | 多通道短信发送、回执、上行，对应 `quick-sms` |
| Cart 服务 | https://cart.whaleal.com | 购物车恢复与事件处理 |
| 身份认证（IdP） | https://idp.whaleal.com | 统一身份认证与单点登录 |
| 账户管理端 | https://account.whaleal.com | 用户与权限管理后台 |

## 开源项目

| 项目 | 说明 | 语言 | 许可证 |
|------|------|------|--------|
| [quick-sms](https://github.com/whaleal-dev/quick-sms) | 多供应商短信聚合 SDK，统一发信/回执/上行/状态查询，支持 SaaS 多租户 | Java | Apache-2.0 |
| [cart-service](https://github.com/whaleal-dev/cart-service) | 购物车恢复服务，识别放弃购物车并触发召回流程 | Java | — |
| [aihub](https://github.com/whaleal-dev/aihub) | 面向 JDK 8+ 的 Java 大模型客户端，统一各厂商 HTTP/SSE API | Java | Apache-2.0 |
| [rds-sync](https://github.com/whaleal-dev/rds-sync) | 关系型数据库同步 SDK，支持 MySQL/Oracle/PostgreSQL 全量与增量同步 | Java | — |
| [mongo-sync](https://github.com/whaleal-dev/mongo-sync) | MongoDB 文档同步 SDK，全量 + 增量、DDL 跟随与数据校验 | Java | — |
| [mongodb-log](https://github.com/whaleal-dev/mongodb-log) | MongoDB 日志相关工具 | Java | Apache-2.0 |

## 面向 Shopify 商家的场景

**场景一：放弃购物车召回**  
用户在店铺加购但未结账 → `cart-service` 触发放弃事件 → 通过 `quick-sms` 发送短信提醒 → 用户回访完成下单。

**场景二：多通道短信触达**  
同一套代码对接 Twilio、阿里云、腾讯云等通道，按成本或到达率自动切换，适合跨境和多地区店铺。

**场景三：统一账户与权限**  
`idp.whaleal.com` 保证用户身份一致，`account.whaleal.com` 管理权限与偏好，营销动作不重复触达、不误发。

## 文档中心

各子项目文档会自动聚合到 `docs.whaleal.com`，路径使用 projectname：

- https://docs.whaleal.com/quick-sms/
- https://docs.whaleal.com/cart-service/
- https://docs.whaleal.com/aihub/

## 参与贡献

欢迎提交 Issue 和 PR。各仓库的贡献指南见仓库内 `CONTRIBUTING.md`。

## 联系

- GitHub Discussions：在各仓库内发起讨论
- 商务合作：请通过官网 https://whaleal.com 联系
