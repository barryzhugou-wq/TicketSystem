## 回复语言

- 默认使用中文回复。

## 业务命名

- 业务资源命名跟随用户输入语言和当前项目已有命名风格。
- 未明确要求英文数据库字段名时，不要把中文业务名称自动改成英文或 snake_case。
- 中文业务模型中，引用默认主键 `id(Integer)` 的外键字段优先命名为 `实体名ID`，例如 `任务ID`、`项目ID`、`迭代ID`。
- 如确需英文物理列名，可使用类似 `columnName: "task_id"` 的写法，同时设置 `displayName: "任务ID"`，避免界面直接暴露技术名。

## 版本推送

- 每次完成用户提出的变更后，先用中文总结本次变更内容，作为提交说明（首行概括，正文按条目列出关键改动与影响），然后自动提交并推送到远程仓库，无需再次询问。
- 远程仓库 `origin` 指向 https://github.com/barryzhugou-wq/TicketSystem ，分支 `main`。
- 提交范围遵循仓库根目录 `.gitignore`：不提交 `server-data/`、数据库临时文件（`*-wal` / `*-shm`）与本机服务配置 `.phoenix/local-services.json`。
- 本机 Git 未加入 PATH，使用 `C:\Program Files\Git\cmd\git.exe`；该环境需通过 `Start-Process` 调用外部程序。
- 若变更涉及口令、令牌、密钥等敏感信息，先提示用户确认处理方式，不要直接推送。
