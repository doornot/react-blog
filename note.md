### react-blog

* server

  * 邮件通知服务 - nodemailer

  * 身份验证
    * Cookie和Token https://www.jianshu.com/p/ce9802589143
    * Cookie 还是Token，这是一个问题 https://www.jianshu.com/p/8c87099f72a5
    * GitHub OAuth 第三方登录示例教程 - 阮一峰
    * GitHub ruanyf/node-oauth-demo
    
  * 权限管理

  * DB: mysql, ORM: sequelize
    * 使用Sequelize连接数据库- 掘金
    * Sequelize - 使用Sequelize - 廖雪峰的官方网站

* client

  * 单页应用的部署方案

  https://segmentfault.com/a/1190000019205506

  先看看单页应用的部署，单页应用开发完只有一个index.html，页面的渲染及其他页面都通过js来生成和控制。同时浏览器刷新页面的时候，是会发请求到服务器的，所以如果按照常规方式来部署，就会出现在/user/detail这样的页面刷新的时候，会出现404错误，因为浏览器将页面发到服务器，却发现服务器上根本没有这个资源，所以就404了。所以单页应用的部署，需要将所有的页面请求都返回index.html，浏览器下载了index.html后js会自动解析并导航到对应页面。

  * react hooks
  
