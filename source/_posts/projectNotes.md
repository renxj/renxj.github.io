---
title: 项目运行部署备注
date: 2019-12-04 16:20:20
categories: 生活
tags: 工作
---

### 1.qdp-wain-web   CRM云 前后端在同一个仓库里面 
前端项目在 src/main/vue-order
```
    git@git.iqdnet.cn:qdp/qdp-wain-web.git //仓库地址
    npm run dev //运行项目
    npm run build //打包项目
    npm run copy  //把打包生成的dist文件夹里面 的 static文件和index.html 拷贝到webapp文件里面,然后按照打包后index.html的hash修改 index.jsp里对应的hash值。提交代码
```
    

<!-- more -->

### 2.qdp-polaris-webui  标品报表项目 纯前端项目
Vue-report 
```
    git@git.iqdnet.cn:qdp-h5/qdp-polaris-webui.git //仓库地址
    npm run dev // 运行项目,提测直接提交代码即可
```

### 3.qdp-oasis-webui 包含多个项目 纯前端项目
```
    git@git.iqdnet.cn:qdp-h5/qdp-oasis-webui.git //仓库地址
```
vue是老的计费页面 （代码较老，目前只有打印页面在其中）

vueNew是老的计费页面对应新的业务（代码较老，目前只有基础数据部分页面在，没有重构的部分）

Vue-comego是计费往来增强大版的代码
```
    npm run dev 运行项目
    npm run build 打包代码提交即可
```

Vue-basic是计费的基础数据文件夹

vue-redRush是计费红冲的业务

### 4.qdp-polestar-webui-jianye 建业报表项目
vue-JY  
```
    git@git.iqdnet.cn:qdp-h5/qdp-polestar-webui-jianye.git //仓库地址
    npm run dev 启动项目
```


### 5.qdp-rosetta-web 品质管理云
Vue 
```
    git@git.iqdnet.cn:qdp/qdp-rosetta-web.git //仓库地址
    npm run dev 运行项目
    npm run build  打包项目
```

### 6.sass 千丁云框架前端项目
```
     git@git.iqdnet.cn:FED/saas.git //仓库地址

```

安装redis,启动redis,根目录需要增加config.js
```
// eslint-disable-next-line no-console
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
运行方法
```
npm install yarn -g
yarn install
yarn watch //页面
node server.js //接口调试
```

### 7.qdp-meter-web  计量表UI与接口项目
src/main/webapp/vue 
```
npm install
node server.js //启动服务(http://localhost:8090)
npm run dist //发布代码
```
打包之后修改webapp下index.html静态资源的参数防止缓存

### 8.qdp-anchor-web 票据项目 
qdp-anchor-webui 新版前端代码 打包后distbill
```
git@git.iqdnet.cn:qdp/qdp-anchor-web.git 
git@git.iqdnet.cn:qdp-h5/qdp-anchor-webui.git
```
qdp-anchor-webui打包方式
```
npm run dev 
npm run build 

```

打包完之后把 src/assets/font文件夹下的文件拷贝到 distbill文件下 fronts文件下 提交代码
然后把整个distbill文件夹放到qdp-anchor-web/src/main/webapp文件下即可

### 9.qdp-JianYe-bigscreen-webui 河南建业BI大屏前端项目地址
```
git@git.iqdnet.cn:qdp-h5/qdp-JianYe-bigscreen-webui.git
```
本地运行index.html 注释document.domain = "jianyewy.com";即可正常运行




