# GuidePref 临床指南患者偏好问卷平台

## 项目概述

GuidePref 是一个专业的临床指南患者偏好问卷调查平台，旨在帮助医疗研究人员收集和分析患者对不同治疗方案的价值观和偏好。该平台通过结构化的问卷设计流程，结合AI智能辅助功能，为临床决策提供科学依据。

## 核心功能

### 1. 用户管理系统
- 用户注册与登录
- JWT Token认证机制
- 用户信息管理
- 权限控制（管理员/普通用户）

### 2. 问卷项目管理
- 六步创建流程：
  1. 选择问卷目标类型
  2. 填写疾病和治疗方案信息
  3. 自动生成问卷内容
  4. AI智能审核与润色
  5. 发布问卷（支持问卷网集成）
  6. 数据分析与报告生成

### 3. 智能问卷生成
- 基于疾病名称和治疗方案自动生成专业问卷
- AI辅助润色问卷题目和内容
- 支持多种题型：单选、多选、评分、填空等
- 自动生成治疗方案对比表格

### 4. 问卷网集成
- 一键发布到问卷网（wenjuan.com）
- 自动同步答卷数据
- 支持公共链接多人填写
- 二维码分享功能

### 5. 数据分析与报告
- 自动生成患者偏好分析报告
- AI智能解读数据趋势
- 支持Excel数据导入生成报告
- PDF/Excel格式导出功能

### 6. 响应式前端界面
- 现代化Vue3 + Element Plus界面
- 移动端适配
- 流畅的用户体验

## 技术架构

### 后端技术栈
- Spring Boot 3.4.10
- Java 17
- MyBatis + MySQL 8.0
- Redis（草稿存储）
- JWT认证
- OpenAI集成（AI服务）

### 前端技术栈
- Vue 3.5.22
- Element Plus UI组件库
- Vue Router路由管理
- Pinia状态管理
- Axios HTTP客户端

### 第三方服务集成
- 问卷网API集成（wenjuan.com）
- OpenAI API（智能问卷生成与分析）

## 数据库设计

系统包含以下核心数据表：
- 用户表（user）
- 问卷项目表（survey_project）
- 问卷表（survey_questionnaire）
- 问卷题目表（survey_question）
- 问卷回复表（survey_response）
- 问卷答案明细表（survey_answer）
- 分析报告表（survey_report）

## 部署要求

### 后端环境
- Java 17+
- MySQL 8.0+
- Redis 6.0+
- Maven 3.6+

### 前端环境
- Node.js 20.19.0+
- npm 10.0+

## 项目特色

### 1. 医学专业性
- 针对临床指南设计的专业问卷模板
- 医学术语AI润色，确保表述准确
- 治疗方案对比信息结构化展示

### 2. AI智能辅助
- 自动生成问卷内容
- 智能审核与优化题目表述
- 数据分析报告自动生成

### 3. 灵活部署
- 支持本地部署和问卷网集成
- 公共链接支持多人填写
- 二维码分享便于传播

### 4. 数据安全
- JWT Token认证保护API安全
- 数据加密存储
- 权限控制确保数据隔离

## 适用场景

1. 医学院校科研项目
2. 医院临床研究
3. 医药企业产品调研
4. 公共卫生政策研究
5. 患者满意度调查

## 快速开始

### 后端启动
```bash
cd Backend/Penal_Survey
mvn spring-boot:run
```

### 前端启动
```bash
cd Front/Panel_Survey
npm install
npm run dev
```

## 配置说明

### 数据库配置
在application.properties中配置MySQL连接信息：
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/panel_survey
spring.datasource.username=root
spring.datasource.password=your_password
```

### Redis配置
```properties
spring.data.redis.host=localhost
spring.data.redis.port=6379
```

### 问卷网集成配置
```properties
wenjuan.api.app-key=your_app_key
wenjuan.api.app-secret=your_app_secret
```

### OpenAI配置
```properties
spring.ai.openai.base-url=https://api.xty.app
spring.ai.openai.api-key=your_api_key
