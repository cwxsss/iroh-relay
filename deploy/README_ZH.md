# UniClipboard 自建服务部署

本目录存放 UniClipboard 自建服务的部署产物。两个服务彼此独立：**不要合并到同一个 Compose 项目，也不要共用同一套数据卷。**

| 服务 | 作用 | 是否加入 Space | 对外端口 | 文档 |
| --- | --- | --- | --- | --- |
| iroh relay | 设备无法直连时转发加密的 iroh 流量；同时承担地址发布与打洞协调 | 否 | `80/tcp`、`443/tcp`、`7842/udp` | [`relay/README_ZH.md`](relay/README_ZH.md) |
| 群晖 headless 节点 | 常驻在线、持续收发剪贴板事件的 UniClipboard 节点 | 是 | `42720/tcp`、可选固定 iroh UDP | 见 UniClipboard 主仓库 |

- relay 不加入 Space，不需要 Space 口令或邀请码，不提供移动端 HTTP 网关，也不保存剪贴板历史。
- 群晖 headless 节点属于 UniClipboard 主仓库的部署内容，不在本仓库（`cwxsss/iroh-relay`）维护。
