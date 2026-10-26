# 九天插件市场

这是独立于 RWKV 团队市场的九天工作台插件源。支持 Codex、Claude Code，无须安装 Node.js 或配置个人令牌。

## 成员安装

1. 在 Codex 的插件页右上角选择添加插件市场，粘贴 `https://github.com/LeoLin4258/jiutian-plugins`。每台设备只需添加一次。
2. 在“个人 → 九天插件市场”中找到“九天工作台”，点击 ＋ 安装。
3. 安装时会自动打开浏览器。切换到新打开的“连接九天工作台”网页；若先出现登录页，使用管理员分配的九天账号登录。选择权限，点击“同意并连接”。这个按钮在九天网页中，ChatGPT / Codex App 内没有这个按钮。
4. 网页授权成功后回到 App，等待安装完成。新建聊天，说：“列出我负责的待处理任务”。

网页已登录不代表插件已获授权。App 一直显示“正在安装”时，先查看浏览器是否有等待授权的“连接九天工作台”标签页。

1.1.1 修复了 Codex 的 MCP 连接类型。1.1.0 在部分客户端会显示插件已安装却没有加载工具；1.0.0 是需要手动令牌的旧本机版。已有旧版的用户请先更新市场，再卸载旧插件并重新安装 1.1.1 或更新版本；仅更新市场不会替换旧安装。

也可以让 Codex 执行：

```sh
codex plugin marketplace add https://github.com/LeoLin4258/jiutian-plugins.git
codex plugin add jiutian-agent@jiutian
```

Claude Code 在 `/plugin` 中添加同一市场，然后安装 `jiutian-agent@jiutian`；需要连接时使用 `/mcp` 完成网页登录。

```text
/plugin marketplace add LeoLin4258/jiutian-plugins
/plugin install jiutian-agent@jiutian
```

## 发布方

将本目录**全部内容（包括隐藏目录）**发布为独立 Git 仓库，不能只上传 plugins 子目录。不需要把业务系统源码、数据库或环境变量放入市场仓库。若仓库私有，每个成员还需具备仓库读取权限。

市场出现与账号授权是两件事：只有拥有九天系统账号并授权的用户可以访问业务数据。首次分发前，服务端必须部署 OAuth 迁移及接口，地址为 `https://reexen-oa.rwkvos.com/api/mcp`。

此市场不依赖公共插件目录审核，添加来源后显示在个人插件中。小样本可通过工具提交；20 MB 文件仍可从任务页面上传。连接可以在系统设置中随时撤销。
