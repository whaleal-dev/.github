# Whaleal 内部信息

> 此页面仅对 `whaleal-dev` 组织成员可见。  
> 非成员访问组织主页时，只会看到公开的 Profile 视图。

## 线上服务

| 服务 | 地址 | 说明 |
|------|------|------|
| 主站 | https://www.whaleal.com | 品牌与产品入口 |
| 文档中心 | https://docs.whaleal.com | 技术文档中心，子项目文档自动添加 projectname 路径 |
| SMS 服务 | https://sms.whaleal.com | 多通道短信发送、回执、上行，对应 `quick-sms` |
| Cart 服务 | https://cart.whaleal.com | 购物车恢复与事件处理 |
| 身份认证（IdP） | https://idp.whaleal.com | 统一身份认证与单点登录 |
| 账户管理端 | https://account.whaleal.com | 用户与权限管理后台 |
| GitHub 组织 | https://github.com/whaleal-dev | 开源仓库与协作 |

## 文档中心与 GitHub Pages

文档中心部署在 `https://docs.whaleal.com`，从 `whaleal-docs` 仓库构建。  
各子项目文档会自动添加 projectname 作为路径，例如：

- `https://docs.whaleal.com/quick-sms/`
- `https://docs.whaleal.com/aihub/`
- `https://docs.whaleal.com/rds-sync/`

成员更新文档时，只需向对应子仓库的 `docs/` 目录提交 Markdown 文件，CI 会自动触发文档中心重新构建并聚合。

## 仓库清单

### 核心开源项目

| 仓库 | 用途 | 语言 | 许可证 | 地址 |
|------|------|------|--------|------|
| `quick-sms` | 多供应商短信聚合 SDK，统一发信/回执/上行/状态查询，支持 SaaS 多租户 | Java | Apache-2.0 | https://github.com/whaleal-dev/quick-sms |
| `aihub` | 面向 JDK 8+ 的 Java 大模型客户端，统一各厂商 HTTP/SSE API | Java | Apache-2.0 | https://github.com/whaleal-dev/aihub |
| `alpha4j` | 纯 Java 实现 Alpha101/158/360 因子计算，无 Python 依赖 | Java | — | https://github.com/whaleal-dev/alpha4j |
| `rds-sync` | 关系型数据库同步 SDK，支持 MySQL/Oracle/PostgreSQL 全量与增量同步 | Java | — | https://github.com/whaleal-dev/rds-sync |
| `mongo-sync` | MongoDB 文档同步 SDK，全量 + 增量、DDL 跟随与数据校验 | Java | — | https://github.com/whaleal-dev/mongo-sync |
| `mongodb-log` | MongoDB 日志相关工具 | Java | Apache-2.0 | https://github.com/whaleal-dev/mongodb-log |

### 站点与个人项目

| 仓库 | 用途 | 语言 | 地址 |
|------|------|------|------|
| `whaleal-dev.github.io` | 文档站页面，目前与 www.whaleal.com 一致 | — | https://github.com/whaleal-dev/whaleal-dev.github.io |
| `resume-site` | 个人公开简历与项目展示网站 | CSS | https://github.com/whaleal-dev/resume-site |
| `ielts` | 雅思相关 | HTML | https://github.com/whaleal-dev/ielts |

### 内部仓库

| 仓库 | 用途 | 状态 | 地址 |
|------|------|------|------|
| `.github-private` | 组织内部信息与协作规范 | 内部 | https://github.com/whaleal-dev/.github-private |

> 注：公开仓库共 9 个；私有仓库匿名不可见，可随时补充。

## 内部协作规范

- **分支策略**：`main` 分支保护；功能开发使用 `feature-xxxx`（如 `feature-sso-login`）；修复使用 `fix-xxxx`（如 `fix-sms-timeout`）；发版推荐使用 `release-x.x.x`（如 `release-1.2.0`），从 `main` 切出，验证通过后合并回 `main` 并打版本 Tag。
- **提交信息**：遵循 Conventional Commits（如 `feat: 增加多租户支持`）
- **Issue / PR**：请使用仓库内 `.github/ISSUE_TEMPLATE` 和 PR 模板
- **合并要求**：至少一人 Review，CI 通过后方可合并
- **敏感信息**：严禁在代码或文档中提交密钥、Token、生产环境配置；Packages 发布 Token 仅存放于 GitHub Secrets。

## 私有项目与 Packages

- 私有项目可以发布 GitHub Packages，供组织内部使用。
- 组织 Packages 入口：https://github.com/orgs/whaleal-dev/packages
- 包命名建议：`@whaleal-dev/<project-name>`，例如 `@whaleal-dev/quick-sms`、`@whaleal-dev/aihub`。
- 发布权限：通过 GitHub Actions 或组织级 Personal Access Token（fine-grained）发布，Token 仅存于 Secrets，不写入代码或文档。
- 版本规则：与 `release-x.x.x` 对应，遵循 SemVer；发布前更新 CHANGELOG。
- 内部周期性维护：定期更新依赖、检查安全告警、清理废弃版本、确认包仅对组织内有权限的成员可见。
- 安装方式：组织成员通过 GitHub Packages 仓库地址安装；具体见各项目 README。

## 待办与规划

- [ ] 完善 SMS API 自助定价页与用量看板
- [ ] 开发 Cart Shopify 插件 MVP（放弃购物车短信提醒）
- [ ] 在 `docs.whaleal.com` 增加技术博客板块
- [ ] 配置 MkDocs + multirepo 自动构建多仓库文档站
- [ ] 整理 MongoDB 企业咨询与支持服务包
- [ ] 完善 IdP 与账户管理端的接入文档和 SSO 示例
- [ ] 为私有项目配置 GitHub Packages 发布流程
- [ ] 建立内部包周期性维护清单

## 联系方式

- 内部讨论：GitHub Discussions（各仓库内），成员可自由创建讨论
- 文档站问题：请加群或微信联系
- 加群 / 微信：请查看组织内部公告，或联系管理员获取二维码
- 紧急联系：组织管理员
