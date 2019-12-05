---
title: sass 千丁云框架前端项目
date: 2019-12-05 14:30:26
categories: 生活
tags: 工作
---

```
     git@git.iqdnet.cn:FED/saas.git //仓库地址 标品release分支 建业saas_jianye_private_wy分支

```

#### 环境准备工作
+ 根目录需要增加config.js，配置分为标品和建业，内容如下
```
// 标品
// module.exports = {
//   // 后台接口
//   // whost: 'https://devwx-api.qdingnet.com',
//   // whost: 'https://qagw.qdingnet.com',
//   whost: 'http://qagw.qdingnet.com',
//   wxhost: 'https://devwx-api.qdingnet.com',
//   // whost: 'http://10.39.72.243:8080',
//   // whost: 'https://qawx-api.qdingnet.com',
//   // whost: 'https://wx-api.qdingnet.com',
//   // 静态资源cdn
//   publicPath: 'http://devfront.qdingnet.com/saas-web/dist/',
//   // publicPath: 'http://devb.qdingnet.com:9003/dist/',
//   // publicPath: 'https://qafront.qdingnet.com/saas-web/dist/',
//   // publicPath: 'https://front.qdingnet.com/saas-web/dist/',
//   mpublicPath: 'http://devfront.qdingnet.com/saas-web/mobile/dist/',
//   shost: 'https://qacmsp.qdingnet.com',
//   // shost: 'https://cmsp.qdingnet.com',
//   watch: true,
//   // 进程数
//   cluster: '4',
//   // REDIS
//   redis: {
//     host: '127.0.0.1',
//     port: '6379',
//   },
//   logger: '/Users/renxiaojuan/qianding/saas-master/log/',
// };

// 建业👇
module.exports = {
  // 后台接口
  // whost: 'https://jygw.jianyewy.com',
  whost: 'http://qagw.jianyewy.com',
  // 微信授权
  wxhost: 'https://qawx-api.jianyewy.com',
  shost: 'https://qacmsp.jianyewy.com',
  // 静态资源
  // publicPath: 'https://jyp.jianyewy.com/saas-web/dist/',
  publicPath: 'http://devfront.qdingnet.com/saas-web/dist/',
  mpublicPath: 'https://jyp.jianyewy.com/saas-web/mobile/dist/',
  watch: true,
  cluster: '4',
  redis: {
    host: '127.0.0.1', // 172.17.20.16
    port: '6379', // 6380
  },
  logger: '/Users/renxiaojuan/qianding/saas/log/',
};
```

+ 安装redis,启动redis,
+ 安装nginx,配置nginx,配置文件如下
    ```
    #======qianding-sass  start========= 
    server {
        listen 80;
        server_name front.qdingnet.com devfront.qdingnet.com qafront.qdingnet.com;
        autoindex on;
        add_header Access-Control-Allow-Origin *;
        location /public/ {
            alias /Users/renxiaojuan/qianding/qding-boss/front/public/;
            index index.html;
        }

        location /saas-web/ {
          alias /Users/renxiaojuan/qianding/saas/;  #改成自己的项目路径
        }

        location / {
            rewrite ^/([\w-]+)/(.*)$ /$1/temp/$2 break;
            root /Users/renxiaojuan/qianding/qding-boss/front/; #改成自己的项目路径
        }
    }

    server {
      listen  80;
      server_name  dev.qdingnet.com dev.jianyewy.com;
      #server_name  localhost;
      location / {
        proxy_pass http://localhost:9003;
      }
    }
    ```
+ hosts文件增加 127.0.0.1  dev.qdingnet.com dev.jianyewy.com devfront.qdingnet.com        

#### 运行方法
```
npm install yarn -g
yarn install
yarn watch //页面
node server.js //接口调试
```

#### 发布部署
直接提交代码即可