# Gomoku Mini Program

## 一、项目简介

**Gomoku Mini Program** 是一个基于 **微信小程序** 平台开发的五子棋游戏小程序，采用 **uni-app + Vue 3** 技术栈开发。该小程序支持玩家与 AI 或其他玩家进行实时对战，提供简单、易用且具有挑战性的娱乐体验。后端服务部署在 **阿里云服务器** 上，使用 **Node.js + Express** 提供游戏逻辑和 AI 支持。

本项目使用 **Monorepo** 管理前后端代码，所有代码统一存储在一个仓库中，便于管理和版本控制。

### 主要功能

* **联机对战**：支持玩家与其他人进行实时联网对战，也可以邀请微信好友对战。
* **AI 对战**：玩家可以与 AI 对战，AI 使用剪枝算法（如 `Minimax` 和 `Alpha-Beta` 剪枝）优化决策过程。
* **游戏记录**：记录玩家的胜负记录和每局的棋盘布局。
* **游戏设置**：提供设置功能，调整 AI 难度和其他游戏选项。
* **国际比赛规则**：后续版本将考虑引入禁手、交换等国际比赛规则。

## 二、技术栈

* **前端**：

  * **Vue 3**：用于构建用户界面，采用响应式的数据绑定和组件化开发。
  * **uni-app**：跨平台框架，用于将 Vue 3 代码编译为微信小程序。
  * **Pinia**：Vue 3 推荐的状态管理库，用于管理游戏状态。
  * **Vue Router**：用于页面路由和导航管理。
  * **ESLint & Prettier**：用于代码质量检测和自动格式化。

* **后端**：

  * **Node.js + Express**：用于构建后端服务，处理游戏数据和 AI 逻辑。
  * **Docker**：用于容器化部署，确保后端服务环境一致性。
  * **阿里云服务器**：用于部署后端服务，提供稳定的云计算资源。

* **测试**：

  * **Vitest**：用于单元测试，确保代码功能的正确性。

* **CI/CD**：

  * **GitHub Actions**：用于自动化构建、测试和部署，确保每次提交的代码都经过验证并能成功部署。

## 三、安装与运行

### 3.1 克隆项目

```bash
git clone https://github.com/你的用户名/gomoku-mini-program.git
cd gomoku-mini-program
````

### 3.2 安装前端依赖

进入 `frontend` 目录并安装前端依赖：

```bash
cd frontend
yarn install
```

### 3.3 安装后端依赖

进入 `backend` 目录并安装后端依赖：

```bash
cd backend
yarn install
```

### 3.4 运行前端开发模式

在 `frontend` 目录中运行开发模式：

```bash
yarn dev
```

运行后，微信开发者工具会自动加载该小程序，你可以在工具中看到游戏的效果。

### 3.5 运行后端服务

在 `backend` 目录中启动后端服务：

```bash
yarn start
```

后端服务将会在指定端口启动，并与前端进行连接。

### 3.6 Docker 部署

如果需要在 Docker 环境中部署后端服务：

1. 构建 Docker 镜像：

   ```bash
   docker build -t gomoku-backend .
   ```

2. 启动容器：

   ```bash
   docker run -d -p 3000:3000 gomoku-backend
   ```

## 四、项目结构

本项目采用 Monorepo 结构，前后端代码集中在一个仓库中。以下是项目的目录结构：

```bash
gomoku-mini-program/
├── docs/                 # 开发过程文档
├── frontend/             # 前端小程序代码
│   ├── src/              # Vue 3 源代码
│   ├── pages/            # 页面目录
│   └── components/       # 组件目录
├── backend/              # 后端服务代码
│   ├── src/              # 后端服务源代码
│   └── Dockerfile        # 后端 Docker 配置文件
├── .gitignore            # Git 忽略文件
├── package.json          # 项目依赖配置
├── README.md             # 项目说明文档
└── .github/              # GitHub Actions 配置
    └── workflows/        # CI/CD 流水线配置
```

## 五、贡献与其他

欢迎大家为本项目贡献代码。您可以通过以下步骤贡献：

1. Fork 本仓库。

2. 克隆到本地：

   ```bash
   git clone https://github.com/你的用户名/gomoku-mini-program.git
   ```

3. 创建一个新的分支：

   ```bash
   git checkout -b feature/你的功能
   ```

4. 提交代码：

   ```bash
   git commit -am "Add new feature"
   ```

5. 推送分支：

   ```bash
   git push origin feature/你的功能
   ```

6. 提交 Pull Request。

### 5.1 开源协议

本项目采用 [MIT 开源协议](https://opensource.org/licenses/MIT)。

### 5.2 Issues

如果在使用过程中遇到问题或有任何建议，欢迎通过 [Issues](https://github.com/idevebi/gomoku-mini-program/issues) 提出，我们会尽快回应并解决。

### 5.3 其他

如果你有任何问题或者想与我们讨论更多的功能或改进，欢迎通过 GitHub 或邮件与我们联系。
