NIE-Broadcast
一个简单、轻量级的Minecraft定时广播消息插件，支持全版本（1.8-1.21）和全核心（Spigot、Paper等）。允许自定义广播消息和时间间隔，支持颜色代码和PlaceholderAPI占位符。

作者: NieKaiXiang
版本: v1.0.0
支持版本: Minecraft 1.8 - 1.21
支持核心: Spigot, Paper, CraftBukkit 等

功能

定时广播自定义消息，按顺序循环发送。
支持通过 config.yml 配置消息内容和广播间隔。
支持 & 颜色代码（如 &a 表示绿色）。
可选支持 PlaceholderAPI 占位符（如 %server_online%）。
提供 /nbreload 命令动态重载配置。
轻量级设计，无额外依赖，兼容性强。

安装

下载编译后的 NIE-Broadcast-v1.0.0.jar。
将 JAR 文件放入服务器的 plugins 文件夹。
启动或重启服务器，插件会自动生成默认 config.yml。
编辑 plugins/NIE-Broadcast/config.yml 配置消息和间隔时间。
（可选）安装 PlaceholderAPI 以支持占位符。
使用 /nbreload 命令应用配置更改。

配置
配置文件位于 plugins/NIE-Broadcast/config.yml：
# NIE-Broadcast 插件配置
# 作者: NieKaiXiang
# 版本: v1.0.0
#
# 配置说明:
# - interval: 广播间隔时间（分钟），必须为正整数，默认5分钟。
# - messages: 广播消息列表，支持颜色代码（&a, &b 等），按顺序循环发送。
# - 支持 PlaceholderAPI 占位符（如 %server_online%），需安装 PlaceholderAPI 插件。
# - 颜色代码参考: &a（绿色）, &b（青色）, &c（红色）, &e（黄色）, &f（白色）等。
#
interval: 5
messages:
- "&a欢迎来到服务器！输入 /help 查看帮助。"
- "&e当前在线玩家：%server_online%（需 PlaceholderAPI 支持）。"
- "&6请遵守服务器规则，享受游戏！"

配置项说明

interval：广播间隔（分钟），例如 5 表示每5分钟广播一次。
messages：消息列表，按顺序循环发送。支持 & 颜色代码和 PlaceholderAPI 占位符。

颜色代码

&a：绿色
&b：青色
&c：红色
&e：黄色
&f：白色
更多代码参考 Minecraft Wiki 或服务器文档。

命令与权限
命令

/nbreload：重载插件配置文件。
用法：/nbreload
权限：niebroadcast.reload（默认仅OP可用）



权限

niebroadcast.reload：允许使用 /nbreload 命令。
默认：仅OP（服务器管理员）可用。
可通过权限管理插件（如LuckPerms）分配给其他玩家。



示例效果
假设配置为：
interval: 3
messages:
- "&b[广播] &f服务器将于今晚8点进行维护！"
- "&a[提示] &f使用 /shop 打开商店。"
- "&e[活动] &f每周六举行PVP比赛！"

服务器将每3分钟广播一条消息，循环显示：

[广播] 服务器将于今晚8点进行维护！
[提示] 使用 /shop 打开商店。
[活动] 每周六举行PVP比赛！

开发与测试

开发环境：使用 IntelliJ IDEA 和 Maven 构建。
编译：运行 mvn package 生成 NIE-Broadcast-v1.0.0.jar。
测试：支持 MockBukkit 单元测试，或在 Spigot/Paper 服务器上测试。
兼容性：已验证兼容 Minecraft 1.8、1.12、1.16、1.20、1.21。

常见问题

插件未加载：
检查 plugin.yml 是否正确，JAR 文件是否在 plugins 文件夹。
查看服务器日志，确认是否有错误。


消息不显示：
确保 config.yml 中的 messages 列表不为空。
检查 interval 是否过长（可临时设为 1 测试）。


颜色代码无效：
确保使用 & 代码，如 &a 表示绿色。


PlaceholderAPI 占位符无效：
确认已安装 PlaceholderAPI 插件并启用相关扩展。



联系

作者: NieKaiXiang
问题反馈: 请通过 GitHub Issues 或 SpigotMC 论坛联系。

感谢使用 NIE-Broadcast！如果有建议或问题，请随时反馈。
