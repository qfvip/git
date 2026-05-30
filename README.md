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
2. 回到要注册的 `mac.lan` 本机，打开 `Terminal`。
3. 在 `mac.lan` 的 `Terminal` 里粘贴并运行下面整段代码。
4. 代码运行后会停下来提示你粘贴 CLI；这时再回到 `My Machines` 页面复制完整 CLI 命令，粘贴到 `Terminal` 后按回车。

```bash
#!/bin/bash
set -euo pipefail

echo "这段代码必须在 mac.lan 这台 Mac 的 Terminal 里运行。"
echo "当前机器信息："
echo "hostname: $(hostname)"
echo "LocalHostName: $(scutil --get LocalHostName 2>/dev/null || echo unknown)"
echo
echo "下一步：回到 Cursor 网页版 Self-hosted -> My Machines，复制页面给你的完整 CLI 命令。"
echo "然后回到这个 Terminal，把完整 CLI 命令粘贴到下面这一行，再按回车。"
echo
read -r -p "请粘贴 My Machines 页面复制的完整 CLI 命令，然后按回车: " CURSOR_SELF_HOSTED_CLI

if [ -z "$CURSOR_SELF_HOSTED_CLI" ]; then
  echo "没有粘贴 CLI 命令，已退出。"
  exit 1
fi

echo
echo "即将运行你粘贴的 My Machines CLI 命令。"
read -r -p "确认运行请输入 yes: " CONFIRM
if [ "$CONFIRM" != "yes" ]; then
  echo "你没有输入 yes，已取消。"
  exit 1
fi

eval "$CURSOR_SELF_HOSTED_CLI"

echo
echo "如果 macOS 弹出权限提示，请允许 Cursor、Cursor CLI 或 self-hosted CLI。"
echo "脚本会打开常用权限设置页；打开失败也没关系，可以手动进 系统设置 -> 隐私与安全性。"
open "x-apple.systempreferences:com.apple.preference.security?Privacy_Accessibility" || true
open "x-apple.systempreferences:com.apple.preference.security?Privacy_Automation" || true
open "x-apple.systempreferences:com.apple.preference.security?Privacy_ScreenCapture" || true
open "x-apple.systempreferences:com.apple.preference.security?Privacy_AllFiles" || true
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

注意：页面复制的 CLI 命令通常绑定当前账号、组织或池子，可能包含一次性 token。只在要注册的 `mac.lan` 本机运行，不要在云端机器、其他电脑、README 或聊天记录中公开真实命令。macOS 不允许脚本静默授予所有隐私权限，权限窗口打开后需要你在本机手动勾选允许。
