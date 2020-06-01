### react-blog

- server

  - 邮件通知服务 - nodemailer

  - 身份验证

    - Cookie 和 Token https://www.jianshu.com/p/ce9802589143
    - Cookie 还是 Token，这是一个问题 https://www.jianshu.com/p/8c87099f72a5
    - GitHub OAuth 第三方登录示例教程 - 阮一峰
    - GitHub ruanyf/node-oauth-demo

  - 权限管理

  - DB: mysql, ORM: sequelize
    - 使用 Sequelize 连接数据库- 掘金
    - Sequelize - 使用 Sequelize - 廖雪峰的官方网站

- client

  - 单页应用的部署方案

  https://segmentfault.com/a/1190000019205506

  先看看单页应用的部署，单页应用开发完只有一个 index.html，页面的渲染及其他页面都通过 js 来生成和控制。同时浏览器刷新页面的时候，是会发请求到服务器的，所以如果按照常规方式来部署，就会出现在/user/detail 这样的页面刷新的时候，会出现 404 错误，因为浏览器将页面发到服务器，却发现服务器上根本没有这个资源，所以就 404 了。所以单页应用的部署，需要将所有的页面请求都返回 index.html，浏览器下载了 index.html 后 js 会自动解析并导航到对应页面。

  - react hooks

### 启动本地服务

1、新建一个管理员账号

- 注册一个账号: name:admin, code: admin.

- 修改 blog 数据库 user 表，将 admin 的 role 改为 1(管理员角色)。

- 网页上退出 admin 账号，重新登录 admin，访问/admin就可以看到后台管理系统。

2、启动 mysql 服务

```sh
# 本地启动mysql服务
mysql.server start
# 或者(mac)
brew services start mysql
```

3、更新本地配置

```js
// 文件目录: ./server/config/index.js

config.DATABASE = {
  ...config.DATABASE,
  database: 'blog', // 数据库名
  user: 'root', // 账号
  password: '123456' // 密码
}

config.TOKEN.secret = 'wang-test'
```
