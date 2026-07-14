# TripMind 行程智策 🌍✈️

用户输入目的地、旅行日期和个人偏好后，系统会结合大语言模型与高德地图服务，自动生成包含景点、住宿、餐饮、天气和交通路线的多日行程。

## ✨ 主要功能
- 根据日期、旅行天数和个人偏好生成个性化行程
- 自动搜索景点 POI，并在地图中展示位置与路线
- 查询目的地天气，辅助调整每日安排
- 提供住宿、餐饮、交通和预算建议
- 支持查看每日详细行程并导出旅行计划
- 通过 Agent 自动选择和调用地图相关工具

## 🛠️ 技术栈
**后端**

- Python
- HelloAgents
- SimpleAgent
- FastAPI
- 高德地图 MCP 服务
- DeepSeek 大模型接口
- 
**前端**
- Vue 3
- TypeScript

## 🖼️ 运行效果
### 行程信息填写

![行程信息填写](docs/images/home.png)

### 行程概览与景点地图
![行程概览与景点地图](docs/images/overview-map.png)

### 每日行程
![每日行程](docs/images/daily-itinerary.png)
### 天气信息
![天气信息](docs/images/weather.png)

## 📁 项目结构
```text
multi-agent-trip-planner/
├── backend/                 # FastAPI 后端
│   ├── app/
│   │   ├── agents/          # 旅行规划 Agent
│   │   ├── api/             # 接口路由
│   │   ├── models/          # 数据模型
│   │   └── services/        # 地图与大模型服务
│   ├── requirements.txt
│   └── run.py
├── frontend/                # Vue 3 前端
│   ├── src/
│   ├── package.json
│   └── vite.config.ts
├── docs/
│   └── images/              # 项目运行截图
└── README.md
```

## 🚀 快速开始
### 环境要求
- Python 3.10+
- Node.js 16+
- Conda
- npm

### 1. 启动后端
进入后端目录：
```bash
cd backend
```
创建并激活 Conda 环境：

```bash
conda create -n tripmind python=3.10
conda activate tripmind
```

安装依赖：

```bash
pip install -r requirements.txt
```

启动后端服务：

```bash
python run.py
```

接口文档：

```text
http://localhost:8000/docs
```

### 2. 启动前端

进入前端目录并安装依赖：

```bash
cd frontend
npm install
```

启动前端：

```bash
npm run dev
```

浏览器访问：

```text
http://localhost:5173
```

## 🔐 环境配置

项目运行前需要配置：

- DeepSeek API Key
- 高德地图 Web 服务 API Key
- 高德地图 JavaScript API Key

请将 API Key 保存在本地 `.env` 文件中，不要将真实密钥上传到 GitHub。

## 📄 主要接口

```text
POST /api/trip/plan      生成旅行计划
GET  /api/map/poi        搜索景点 POI
GET  /api/map/weather    查询天气信息
```
