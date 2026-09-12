# Enterprise Training Outline Designer

一个面向企业内训咨询场景的 Codex Skill。它通过逐题访谈澄清培训需求，在用户确认需求与交付形式后，生成客户可用的课程大纲、Markdown、Word 或 HTML 方案。

## 能力特点

- 每次只追问一个最影响课程设计的问题
- 将客户事实、设计判断和未确认信息分开
- 从学员工作成果倒推课程模块、练习与交付物
- 支持聊天版、Markdown、Word 和响应式 HTML
- 内置通用 Word 与 HTML 方案模板
- 对时长、模块产出、品牌资产和人工审核边界进行交付检查

## 安装

将本仓库克隆或复制到 Codex Skills 目录：

```powershell
git clone https://github.com/<your-account>/enterprise-training-outline-designer.git "$env:CODEX_HOME\skills\enterprise-training-outline-designer"
```

如果未设置 `CODEX_HOME`，Windows 默认目录通常为：

```text
C:\Users\<用户名>\.codex\skills\enterprise-training-outline-designer
```

## 使用示例

```text
Use $enterprise-training-outline-designer to help me design a four-hour enterprise AI training course.
```

Skill 会先进入需求访谈，不会在关键信息缺失时直接生成正式方案。

## 目录结构

```text
SKILL.md
agents/openai.yaml
assets/
references/
scripts/
```

## 验证

```powershell
python scripts/validate_training_brief.py references/ready-training-brief.json
python scripts/next_interview_question.py references/minimal-training-brief.json
```

## 隐私与边界

请勿将客户机密、个人数据、未授权培训材料或真实业务凭据提交到公开仓库。Skill 内置模板仅用于结构与视觉参考，生成客户方案时仍需替换所有占位信息并完成最终人工复核。

## License

MIT
