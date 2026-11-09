请把 https://github.com/liuqun12134-bit/image-fission 的 main 分支中 `skills/image-fission` 完整安装为本机独立 Skill，不要只给教程。

使用已有 GitHub 登录读取私有仓库；不要索取或显示令牌。Git 克隆网络失败时可以使用已认证的 GitHub API 下载同一提交归档；不可把仓库改为公开。

检查该平台的用户级技能目录，Codex 使用用户 `.codex/skills/image-fission`，不要安装到插件临时缓存。本版为 1.2.0，完整技能包包含 `SKILL.md` 和 `agents/openai.yaml`，以最新发布清单为准。核验 `manifest.json` 的版本、文件 SHA-256；使用 ZIP 时同时核验压缩包 SHA-256。

现有同名安装先完整备份并比较本地改动；在保留用户改动后整体替换技能目录，避免残留旧版 `references`、`scripts`、`templates` 或 `learning-config.json`。新版不再读取或维护跨任务经验、自优化和策略库，不运行旧版 `learning.py`。安装目录之外的 `.local/share/skill-learning/image-fission` 或 `SKILL_LEARNING_HOME` 中的个人历史数据保持原样，不删除、不上传。

报告实际版本、安装路径和调用方式。仅安装不代表已验证生成效果；不自动生成图片、不上传媒体、不发起付费请求。不移除原插件。必要时提示新开对话加载新版技能。
