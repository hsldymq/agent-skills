# agent-skills

个人维护的通用 Agent Skills 集合。每个 Skill 都是独立目录，可以按需安装到具体项目或个人
环境，不需要一次引入整个仓库。

## 查看可用 Skills

```bash
npx skills add hsldymq/agent-skills --list
```

## 安装到当前项目

项目级 Skill 会写入当前仓库的 `.agents/skills/`，适合随项目提交并与团队共享。

### 使用 skills CLI

需要本机已安装 Node.js。将 `your-skill-name` 替换为需要安装的 Skill：

```bash
npx skills add hsldymq/agent-skills \
  --skill your-skill-name \
  --agent codex \
  --copy \
  -y
```

一次安装多个 Skill：

```bash
npx skills add hsldymq/agent-skills \
  --skill first-skill-name \
  --skill second-skill-name \
  --agent codex \
  --copy \
  -y
```

### 使用 Codex 内置 Skill Installer

在 Codex 中可以直接请求：

```text
$skill-installer 请从 https://github.com/hsldymq/agent-skills/tree/main/skills/your-skill-name
安装 your-skill-name。
```

也可以调用 Codex 自带脚本，明确安装到当前项目：

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo hsldymq/agent-skills \
  --path skills/your-skill-name \
  --dest "$PWD/.agents/skills"
```

内置脚本在目标目录已存在时会停止，不会覆盖现有 Skill。

## 安装到个人环境

如果希望 Skill 对本机所有项目可用：

```bash
npx skills add hsldymq/agent-skills \
  --skill your-skill-name \
  --agent codex \
  --copy \
  --global \
  -y
```

Codex 内置安装脚本不指定 `--dest` 时，也会安装到当前用户的 Codex Skills 目录：

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo hsldymq/agent-skills \
  --path skills/your-skill-name
```

新安装或更新的 Skill 通常会被自动发现；如果没有出现，重启 Codex。

## 使用 Skill

安装完成后，可以在 Codex 中通过名称显式调用：

```text
使用 $your-skill-name 完成当前任务。
```

当请求与某个 Skill 的适用范围匹配时，Codex 也可能自动选择它。

## 更新与移除

使用 skills CLI 更新当前项目中的 Skill：

```bash
npx skills update your-skill-name --project -y
```

移除当前项目中的 Skill：

```bash
npx skills remove your-skill-name --agent codex -y
```

如果使用 Codex 内置脚本复制安装，需要手动删除旧目录后重新安装；操作前先确认目标路径和
未提交修改。

## 安全说明

Skill 是会影响 Agent 行为的可执行说明，且可能包含脚本。安装前应检查 `SKILL.md`、`scripts/`
及其引用资源；不要在 Skill 中提交 Token、私钥、密码、内部地址或项目敏感数据。

## 参考

- [OpenAI：Build skills](https://learn.chatgpt.com/docs/build-skills)
- [Agent Skills specification](https://agentskills.io/)
- [skills CLI](https://github.com/vercel-labs/skills)
