# GitHub Branch Downloader

## 项目简介

`github-branch-downloader` 是一个用于从 GitHub 下载指定项目分支为 ZIP 文件的小工具。你只需提供 GitHub 仓库路径和分支名（可选，默认为 `main`），即可一键下载对应分支的打包文件。

## 功能特性

- 支持指定仓库和分支，一键下载为 ZIP 文件
- 命令行界面，简单易用
- 自动命名下载文件，避免覆盖

## 使用方法

### 环境要求

- Python 3.x
- Windows 系统（默认使用 `curl.exe`，如需在其他系统运行请自行调整命令）
- 已安装 `curl` 工具

### 命令行用法

```bash
python gitdl.py <github仓库路径> [分支名]
```

- `<github仓库路径>` 例如 `octocat/Hello-World`
- `[分支名]` 可选，默认为 `main`

#### 示例

下载 `octocat/Hello-World` 仓库的 `main` 分支：

```bash
python gitdl.py octocat/Hello-World
```

下载指定分支 `dev`：

```bash
python gitdl.py octocat/Hello-World dev
```

下载后会在当前目录下生成 zip 文件，例如：`octocat-Hello-World_main.zip`。

## 实现原理

本工具通过调用 GitHub API 获取指定分支的 zipball，再利用 `curl` 下载文件。详情见 [`gitdl.py`](gitdl.py)。

## 注意事项

- 若下载失败，请检查网络和仓库/分支是否存在。
- 默认使用 Windows 下的 `curl.exe`，如在 Mac/Linux 下请替换为对应 `curl` 命令。

## 许可协议

MIT License

---
欢迎提交 Issue 与 PR 以完善本工具！
