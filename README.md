# Online PAC

![](https://github.com/fanlushuai/pac/actions/workflows/build.yml/badge.svg)

## 特点

基于 IP 地址白名单设计，位于白名单中的 IP 地址走直连，白名单以外的 IP 地址走代理（暂不支持 IPv6）。

另有 GFWList 版本从 [gfwlist/gfwlist](https://github.com/gfwlist/gfwlist) 获取域名及 URL 列表，优先匹配列表中的黑白名单，有效防止 DNS 污染。

每周六 12:00 (UTC) 会自动使用 GitHub Actions 运行[生成脚本](build.py)从数据源获取 IP 地址列表并生成 PAC 文件。

## 使用

### 方式一：

在线使用。引用dist目录中的文件的raw链接。或者使用其镜像加速链接（推荐）。如：

Github Raw: https://raw.githubusercontent.com/fanlushuai/pac/master/dist/pac-gfwlist-17mon.txt

FastGit: https://raw.fastgit.org/fanlushuai/pac/master/dist/pac-gfwlist-17mon.txt

### 方式二：

在自己的github托管使用。

1. fork

2. 修改权限。给action读写仓库权限

3. 添加action变量`PAC_PROXY`。位于 settings > secrets and variables > actions 。值如："SOCKS5 127.0.0.1:7890"

这样就有了一个自己随意搞的在线PAC。 
