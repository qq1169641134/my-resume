# 个人简历生成系统

一个基于Vue 3开发的现代化个人简历系统，支持响应式布局和PDF导出功能。通过外部数据文件配置，轻松更新简历内容而无需重新构建项目。

![简历预览](/resume-preview.jpg)

## 目录

- [技术栈](#技术栈)
- [功能特点](#功能特点)
- [项目亮点](#项目亮点)
- [安装使用](#安装使用)
- [项目结构](#项目结构)
- [自定义配置](#自定义配置)
- [部署说明](#部署说明)
- [贡献指南](#贡献指南)

## 技术栈

- **前端框架**: Vue 3 (组合式API)
- **UI组件库**: Element Plus
- **图标库**: @element-plus/icons-vue
- **样式处理**: SCSS
- **文档导出**: html2pdf.js, html-to-docx
- **构建工具**: Vite
- **包管理器**: Yarn/NPM

## 功能特点

- 🌟 **完整的简历展示**：
  - 个人基本信息（姓名、联系方式、社交媒体等）
  - 教育背景
  - 工作经历
  - 专业技能评分展示
  - 项目经验详情

- 📄 **PDF导出**：一键将网页简历导出为专业PDF文档

- 🔄 **实时更新**：修改简历数据文件后无需重新构建，刷新页面即可查看更新

- 📱 **响应式设计**：适配不同设备屏幕尺寸

## 项目

1. **数据与视图分离**：
   - 简历数据存储在独立的JavaScript文件中
   - 无需编程知识即可更新简历内容
   - 修改数据后无需重新构建项目

2. **现代化组件设计**：
   - 采用Vue 3组合式API
   - 组件化结构，易于维护和扩展
   - 清晰的代码组织和注释

3. **优秀的性能优化**：
   - 按需导入Element Plus组件
   - 静态资源优化加载
   - 导出PDF时高质量渲染

4. **简洁美观的UI设计**：
   - 专业简历布局
   - 适当的空间分配
   - 清晰的信息层次结构

## 安装使用

### 前置要求

- Node.js 16+
- Yarn 或 NPM

### 安装依赖

```bash
# 使用yarn 可使用镜像源加速 --registry=https://registry.npmmirror.com
yarn install

# 或使用npm 可使用镜像源加速 --registry=https://registry.npmmirror.com
npm install
```

### 启动开发服务器

```bash
# 使用yarn
yarn dev

# 或使用npm
npm run dev
```

### 构建生产版本

```bash
# 使用yarn
yarn build

# 或使用npm
npm run build
```

### 预览生产构建

```bash
# 使用yarn
yarn preview

# 或使用npm
npm run preview
```

## 项目结构

```
resume-system/
├── public/                  # 静态资源
│   ├── js/                  # 外部JS文件
│   │   └── resumeData.js    # 简历数据配置文件
│   └── icon.jpg             # 网站图标
├── src/
│   ├── components/          # 组件目录
│   │   ├── BasicInfo.vue    # 基本信息组件
│   │   ├── Education.vue    # 教育经历组件
│   │   ├── Skills.vue       # 技能评分组件
│   │   ├── WorkExperience.vue # 工作经历组件
│   │   └── Projects.vue     # 项目经验组件
│   ├── styles/              # 样式文件
│   │   └── main.scss        # 主样式文件
│   ├── App.vue              # 主应用组件
│   └── main.js              # 入口文件
├── index.html               # HTML模板
├── package.json             # 项目依赖配置
└── vite.config.js           # Vite配置
```

## 自定义配置

### 更新简历数据

编辑 `public/js/resumeData.js` 文件来更新您的简历信息：

```javascript
window.resumeData = {
  basicInfo: {
    name: "您的姓名",
    title: "您的职位",
    // 其他基本信息...
  },
  // 教育、技能、工作经历等其他信息...
};
```

### 自定义样式

编辑 `src/styles/main.scss` 文件或相应的组件样式部分。

## 部署说明

1. 执行构建命令生成生产版本：
   ```bash
   yarn build
   ```

2. 部署 `dist` 目录到任何静态网站托管服务：
   - Nginx
   - Apache
   - Netlify
   - Vercel
   - GitHub Pages
   - 等

3. 部署后，如需更新简历内容，只需修改服务器上的 `js/resumeData.js` 文件，无需重新构建整个项目。

## 贡献指南

1. Fork 本仓库
2. 创建您的特性分支 (`git checkout -b feature/amazing-feature`)
3. 提交您的更改 (`git commit -m 'Add some amazing feature'`)
4. 推送到分支 (`git push origin feature/amazing-feature`)
5. 打开一个 Pull Request

---

项目由张铨开发和维护。欢迎提出问题和建议！
