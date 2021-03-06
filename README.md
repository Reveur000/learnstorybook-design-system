# 统一组件库文档说明

## 项目说明
该项目是一个基于 [react](https://reactjs.org/) 的UI组件库，提供满足多种业务场景的UI组件。  
项目基于[storybook](https://storybook.js.org/)框架开发，主要开发语言为[typescript](https://www.typescriptlang.org/)。

## 目录结构
```
|-- .circleci                # circle-ci相关配置  
|-- .storybook               # storybook相关配置
|-- public                   # 公共资源
|-- build                    # 编译脚本相关
|-- src                      # 项目源代码
|-- |-- assets               # 资源文件
|   |-- components           # 公共组件
|   |   |-- 。。。
|   |   |-- _utils           # 公共方法
|   |   |-- _hooks           # 自定义hooks
|   |   |-- style            # 组件样式
|   |   |-- store.ts         # 组件状态管理
|   |   |-- .stories.mdx     # 组件故事
|   |-- examples             # 示例组件代码，开发学习使用
|   |-- index.js             # 入口文件，打包入口
|   |-- Into.stories.mdx     # 介绍页
```       

## 脚本说明 -- package.json

```js
{
  // 开发环境，运行react项目，本项目无需使用
  "start": "react-scripts start", 
  // 生成环境，打包react项目，本项目无需使用
  "build": "cross-env BABEL_ENV=production babel src -d dist",
  // 执行项目中测试用例
  "test": "react-scripts test",
  // 输出项目中关于webpack的相关配置，禁止使用！！！
  "eject": "react-scripts eject",
  // 开发环境，运行storybook，项目开发时请使用这条指令
  "storybook": "start-storybook -p 9009 -s public",
  // 生产环境，打包storybook项目，项目部署时请使用这条指令
  "build-storybook": "build-storybook -s public",
  // 生产环境，打包storybook项目文档，项目部署文档说明时请使用这条指令
  "build-storybook-docs": "build-storybook -s public --docs",
  // 项目发布到npm时，请使用这条指令
  "release": "auto shipit"
}
```

## 开发指南
**开发分支--dev，请在dev分支上进行开发**

1. 启动
```
yarn storybook
```

2. 组件开发  
    * 每个组件创建一个单独文件夹，所有于组件相关代码都放在这个文件夹下。

## 部署
。。。。。。。

## Storybook插件说明
* [@storybook/addon-actions](https://github.com/storybookjs/storybook/tree/master/addons/actions) -- 组件交互时，打印相关日志
* [@storybook/addon-storysource](https://github.com/storybookjs/storybook/blob/master/addons/storysource) -- 展示组件源码
* [@storybook/addon-knobs](https://github.com/storybookjs/storybook/tree/master/addons/knobs) -- 可视化修改组件属性，便于组件开发
* [@storybook/addon-a11y](https://github.com/storybookjs/storybook/blob/master/addons/a11y) -- 验证组件的可访问性
* [@storybook/addon-viewport](https://github.com/storybookjs/storybook/tree/master/addons/viewport) -- 切换屏幕分辨率，测试组件自适应性
* [@storybook/addon-docs](https://github.com/storybookjs/storybook/tree/master/addons/docs) -- 自动生成组件文档说明
* [更多组件。。。](https://github.com/storybookjs/storybook/tree/master#Addons)

## 学习资源
* [Storybook官方文档](https://storybook.js.org/docs/basics/introduction/)
* [Storybook教程](https://www.learnstorybook.com/intro-to-storybook/react/en/get-started/)
* [Storybook源码](https://github.com/storybookjs/storybook/tree/master)