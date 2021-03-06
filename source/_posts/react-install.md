---
title: React快速入门教程(1)——React的安装
tags: React
date: 2020-06-05 15:06:25
---

### react简介
react是一个由Facebook公司开发，于2013年发布，用来方便开发视觉界面的js库，它的主要目标是通过将UI划分成组件的方式，让管理界面状态在任何时刻都变的简单。

为什么react能够流行开来？第一，相比之前的前端框架，Ember.js和Angular 1.x这些，它没那么复杂；第二，和同时期的Angular 2.x相比，它的性能更好，同时比较好上手，而Angular 2.x和Angular 1.x更像是两种框架；第三，Facebook的推动也是一个重要原因。

react比较容易上手，只要理解组件，JSX语法，state和props这4个基础方面，而这些也是接下来的内容。
### 如何安装react
react是一个js库，说设置可能比安装更适合些。根据自己项目实际情况，一般有两种使用react的方式：
#### 1. 使用create-react-app
creact-react-app是一个帮助你快速构建react项目的脚手架工具。在使用create-react-app之前，确保你的电脑中已经安装了node环境(https://nodejs.org)，node>=6 并且npm>=5.2。然后执行以下指令：
```
1. npx create-react-app my-app
2. cd my-app
3. npm start
```
![安装.png](https://pic.downk.cc/item/5ed9f2d1c2a9a83be5089ba2.png)

安装成功后：

![安装成功.png](https://pic.downk.cc/item/5ed9f31ac2a9a83be5094357.png)

create-react-app创建了一个react项目，同时在package.json中添加了一些命令，在进入项目目录后可以执行npm start来启动项目（也可通过yarn start来启动，如果你安装了yarn的话）。

![启动.jpg](https://pic.downk.cc/item/5ed9f34fc2a9a83be509adbe.jpg)

![浏览器打开.jpg](https://pic.downk.cc/item/5ed9f38fc2a9a83be50a311e.jpg)

除了npm start，create-react-app和添加了其它的指令：
```
1. npm run build：构建react项目到build文件夹里，为部署到服务器上做准备；
2. npm test：使Jest跑单元测试；
3. npm eject：还原create-react-app的配置，自定义项目配置。
```
#### 2. 直接在页面中引入react
这种方式在你的页面只有一个页面，没有导航条的时候使用最合适。只要在body标签中新增两个script标签，引入react.js和react-dom.js，如果需要使用jsx语法，还需要引入babel。([示例](https://codesandbox.io/s/rw3n309z0o))
```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>Static Template</title>
  </head>
  <body>
    <div id="root"></div>
    <!--
      Note: when deploying, replace "development.js" with "production.min.js".
    -->

    <script
      src="https://unpkg.com/react@16/umd/react.development.js"
      crossorigin
    ></script>
    <script
      src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"
      crossorigin
    ></script>
    <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>

    <!-- Load our React component. -->

    <script type="text/babel">
      const Button = () => {
        return <div>Click</div>;
      };
      ReactDOM.render(<Button />, document.getElementById("root"));
    </script>
  </body>
</html>
```