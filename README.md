# git

[qfvip/git](https://github.com/qfvip/git) 仓库。

## 使用

```bash
git clone https://github.com/qfvip/git.git
cd git
```

## 学习笔记

- 2026-05-19：学习 Git 的第一天 ✓

## Self-hosted：把 Mac 注册进池子

### Cursor 网页切换中文

1. 打开 Cursor 网页版。
2. 进入右上角头像或设置菜单。
3. 找到 `Language` 或 `语言`，选择 `中文`。
4. 刷新页面，确认 Self-hosted、`My Machines` 等页面显示为中文界面。

### 在 `mac.lan` 本机运行 CLI

1. 打开 Self-hosted 控制台，进入 `My Machines`。
2. 在页面上复制为当前池子生成的 CLI 安装命令。
3. 回到要注册的 `mac.lan` 本机，打开 Terminal。
4. 在 `mac.lan` 本机运行下面的代码，并把占位行替换成 `My Machines` 页面复制的完整 CLI 命令：

```bash
# 必须在 mac.lan 本机 Terminal 里运行
hostname
scutil --get LocalHostName

# 不要原样运行这一行；用 My Machines 页面复制出的完整 CLI 命令替换它
<PASTE_MY_MACHINES_CLI_COMMAND_HERE>
```

### 授权 `mac.lan` 上的 Cursor 自动化

1. 如果系统提示授权自动化操作，在 `mac.lan` 本机打开 `系统设置`。
2. 进入 `隐私与安全性`，允许 Cursor、Cursor CLI 或 self-hosted CLI 使用需要的权限：
   - `自动化`
   - `辅助功能`
   - `屏幕录制`
   - `文件与文件夹` 或 `完全磁盘访问`（如页面或 CLI 提示需要）
   - `开发者工具`（如页面或 CLI 提示需要）
3. 授权完成后，回到 `mac.lan` 的 Terminal，继续运行或重启刚才的 CLI。
4. 回到 `My Machines` 页面，确认这台 Mac 显示为在线或可用状态。

注意：页面复制的 CLI 命令通常绑定当前账号、组织或池子，可能包含一次性 token。只在要注册的 `mac.lan` 本机运行，不要在云端机器、其他电脑、README 或聊天记录中公开真实命令。
