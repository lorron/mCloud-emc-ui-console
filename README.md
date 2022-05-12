# mCloud-emc-ui-console

### 项目代号
> mCloud EMC UI Console

### 项目介绍
> 简会云（租户/机构）控制台

### 项目结构
```
├── README.md
├── package.json
├── index.html
├── src
│   ├── api  # 请求接口
│   ├── assets  # 静态资源
│          └── style 全局样式
│   ├── components  # 通用业务组件
│   ├── config  # 全局配置(包含echarts主题)
│          └── settings.json  # 配置文件
│   ├── directives # 指令集（如需，可自行补充）
│   ├── filters # 过滤器（如需，可自行补充）
│   ├── hooks # 全局hooks
│   ├── layout  # 布局
│   ├── locale  # 国际化语言包
│   ├── mock  # 模拟数据
│   ├── views  # 页面模板
│   ├── router # 路由配置
│   ├── store  # 状态管理中心
│   ├── types  # Typescript 类型
│   └── utils  # 工具库
│   └── App.vue  # 视图入口
│   └── main.ts  # 入口文件
└── tsconfig.json
```

### Git Commit 强制规范(Husky校验)
> 格式：?号对应可选项，注意冒号后面须空格
```
type(scope?): subject
body?
footer?
```
> Type约定
```
build: 构建
chore: 日常
ci: 部署
docs: 文档
feat: 功能
fix: 修复
perf: 性能
refactor: 重构
revert: 回滚
style: 格式
test: 测试
```