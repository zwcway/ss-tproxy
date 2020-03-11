原项目 [zfl9/ss-tproxy](https://github.com/zfl9/ss-tproxy)


## TODO LIST
- [ ] 自动安装 `dnsmasq`/`v2ray`/`ssr`
- [x] 实时速度显示
- [ ] 订阅功能，多个节点一键切换
- [ ] 同时多个节点负载均衡功能

## 更新历史

**v5.3.1 stable**
- 增加 `gfwlist`/`ignlist` 域名或ip检测，并支持管道
- 增加实时速度显示
- 修复其他问题

**v5.2.1 stable**
- 修复 iptables 错误规则
- 修复其他问题

**v5.2**
- 优化 gfwlist 导入性能
- 优化服务依赖关系
- 支持自定义 `iptables`/`ip2tables`/`dnsmasq`/`chinadns-ng`/`dns2tcp` 等可执行文件的路径

**v5.1**
- 整合参数。现在支持 `start`/`stop`/`restart`/`status`/`show`/`flush`/`reload`/`update`/`parse`/`add`/`del`/`mode`
- 支持单独启动任何一个服务 `dnsmasq`/`iptables`/`ipset`/`v2ray`/`ssr`/`ss`。**注意：一些服务之间存在依赖**
- 修复内核模块依赖提示错误的问题
- 修复一些其他bug

**v5.0**
- 增加 `v2ray`/`ssr`/`ss`进程管理
- 增加依赖内核模块的校验
- 支持修改 `gfwlist.ext`/`ignlist.ext` 文件
- 支持修改 `ss-tproxy.conf` 配置文件
- 增加 `ipset` 自动过期配置

## 群晖 DSM 6.1使用说明

#### Dnsmasq
建议使用最新版，手动编译，编译方法参考下面说明。

#### 内核模块编译
群晖中默认缺少一些必要模块，只能通过自己编译解决。
编译内核模块可以参考官方文档 [Synology DSM6.0 Developer Guide](https://help.synology.com/developer-guide/create_package/install_toolkit.html) 中的 `2.1` 和 `7.2` 章节。

#### iptables

DSM 6.1自带的iptables命令不支持mark扩展，运行提示：

```
iptables v1.6.0: Couldn't load match `mark':No such file or directory
Try `iptables -h' or 'iptables --help' for more information.
```
使用 `opkg` 中的 `iptables` 解决

