# GitHub 进阶学习笔记：

一、深入理解 Git 基础

- 分支模型：掌握分支的创建、合并和删除。例如， git branch <new-branch> 创建新分支， git checkout <branch> 切换分支， git merge <branch> 合并分支。理解不同的合并策略，如 fast - forward （快进式合并，用于线性分支）和 --no - ff （非快进式合并，保留分支历史）。
- 重置和回滚： git reset 用于将当前分支的 HEAD 指针移动到指定的提交，有 --soft （只移动 HEAD，暂存区和工作区不变）、 --mixed （默认，移动 HEAD，重置暂存区）、 --hard （移动 HEAD，重置暂存区和工作区）三种模式。 git revert 则是创建一个新的提交来撤销指定的提交。

二、GitHub 协作流程

- Fork 和 Pull Request：当要为其他开源项目贡献代码时，先 fork 项目到自己的 GitHub 仓库。在本地修改代码后， push 到自己的 fork 仓库，然后在 GitHub 界面创建 Pull Request 。在 Pull Request 中详细描述修改内容和目的，方便原项目维护者审查。
- 代码审查（Code Review）：如果是项目维护者，要建立有效的代码审查流程。可以利用 GitHub 的评论功能，对 Pull Request 中的代码逐行审查，提出修改建议。同时，也可以使用一些 GitHub 集成的第三方代码审查工具。

三、GitHub 高级功能

- GitHub Actions：实现自动化工作流程。例如，可以设置在 push 代码到特定分支时自动运行测试、构建项目、部署到服务器等。通过编写 yaml 配置文件来定义工作流的触发条件和步骤。
- GitHub Pages：用于搭建项目的静态网站。可以将 html 、 css 、 js 等静态文件部署到 GitHub Pages 上，方便展示项目文档、示例等。每个仓库都可以有自己的 GitHub Pages 站点，通过特定的分支（通常是 gh - pages ）来部署。
- 使用标签（Labels）和里程碑（Milestones）：标签可用于对 issue 和 Pull Request 进行分类，如 bug 、 enhancement 等。里程碑则可以将相关的 issue 和 Pull Request 组合在一起，代表项目的一个阶段目标。

四、安全与最佳实践

- 保护分支（Protected Branches）：对于重要的分支（如 master ），设置保护规则。可以限制谁能直接 push 到该分支，要求 Pull Request 必须通过指定的检查（如代码审查、测试通过）后才能合并。
- SSH 密钥管理：使用 SSH 密钥而不是 HTTPS 来与 GitHub 交互，提高安全性。生成 SSH 密钥对，并将公钥添加到 GitHub 账户设置中。在本地配置好 SSH 连接，避免每次操作都输入用户名和密码。
- 遵循开源协议：如果项目是开源的，要明确选择合适的开源协议（如 MIT、GPL 等），并确保项目中的代码和依赖都符合协议要求。同时，在使用其他开源项目时，也要遵守其开源协议。