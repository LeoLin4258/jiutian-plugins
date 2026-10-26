# 九天插件市场

这是独立于 RWKV 团队市场的九天工作台插件源。支持 Codex、Claude Code，无须安装 Node.js 或配置个人令牌。

## 成员安装

1. 在 Codex 的插件页右上角选择添加插件市场，粘贴 `https://github.com/LeoLin4258/jiutian-plugins`。每台设备只需添加一次。
2. 在“个人 → 九天插件市场”中找到“九天工作台”，点击 ＋ 安装。
3. 按连接提示，在九天网站用管理员分配的账号登录，选择权限并同意连接。
4. 新建聊天，说：“列出我负责的待处理任务”。

已添加市场的 Codex 可用 `codex://plugins/install/jiutian-agent?marketplace=jiutian` 打开安装页。该链接不会为新设备自动添加市场。

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
