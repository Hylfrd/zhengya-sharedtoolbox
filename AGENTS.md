# Commit requirements

- 使用 Angular 风格标题：`<type>(<scope>): <summary>`。
- 每次提交仅包含标题，不添加正文或 footer；不采用 Angular 的强制正文要求。
- `type` 使用 `build`、`ci`、`docs`、`feat`、`fix`、`perf`、`refactor`、`test`；撤销提交使用 `revert`。
- 必须包含有实际意义的 `scope`，按受影响的项目区域命名；本文件的提交规范变更使用 `ai-policy`。
- `summary` 使用清晰英文，以小写祈使动词开头，末尾不加句号。可以使用简短句子，不必压缩成过短短语，也不要写成长段落。

示例：

```text
docs(ai-policy): define commit title requirements
docs(project): initialize repository documentation
feat(ttlock): fetch locks from the cloud API
fix(auth): refresh expired access tokens
```

# Code formatting

- 使用空格缩进，删除行尾多余空格，并在文件末尾保留换行。保持每种语言的既有缩进宽度，不要全项目强制使用相同宽度。
- 前端 TypeScript、CSS、HTML、测试和配置使用项目配置的 Prettier：2 个空格缩进、单引号、目标行宽 100。运行 `npm --prefix frontend run format` 格式化，运行 `npm --prefix frontend run format:check` 检查。
- Python 使用项目配置的 Ruff formatter：4 个空格缩进、优先单引号、目标行宽 100。安装 `backend/requirements-dev.txt` 后，从仓库根目录运行 `python -m ruff format backend deploy/wheels.py`；检查时增加 `--check`。
- Shell 和 YAML 保持 2 个空格缩进。将过长的表达式、HTML 和样式按结构拆分，保持代码易读；行宽是目标，不要为了满足长度而破坏可读性。
- 格式调整必须保持行为不变。尤其注意字符串、HTML 模板、内联元素之间的空白、正则表达式和 Shell heredoc；不要为换行而改变其内容或语义。第三方文件、生成文件及锁文件不做无关格式化。
