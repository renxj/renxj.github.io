---
title: 项目运行部署备注
date: 2019-12-04 16:20:20
categories: 生活
tags: 工作
---

### 1.qdp-wain-web   CRM云 前后端在同一个仓库里面 
前端项目在 src/main/vue-order
```
    git@git.iqdnet.cn:qdp/qdp-wain-web.git // 仓库地址
    npm run dev // 运行项目
    npm run build // 打包项目
    npm run copy  // 把打包生成的dist文件夹里面 的 static文件和index.html 拷贝到webapp文件里面,
    // 然后按照打包后index.html的hash修改 index.jsp里对应的hash值。提交代码
```
    

<!-- more -->

### 2.qdp-polaris-webui  融侨报表项目 纯前端项目
Vue-report 
```
    git@git.iqdnet.cn:qdp-h5/qdp-polaris-webui.git //仓库地址
    npm run dev // 运行项目,提测直接提交代码即可
```

### 3. qdp-polestar-webui-standard 标品报表
```
    git@git.iqdnet.cn:qdp-h5/qdp-polestar-webui-standard.git  
    npm run dev // 运行项目,提测直接提交代码即可
```
  
### 4.qdp-oasis-webui 包含多个项目 纯前端项目
```
    git@git.iqdnet.cn:qdp-h5/qdp-oasis-webui.git // 仓库地址
```
vue是老的计费页面 （代码较老，目前只有打印页面在其中）
    直接解压 node_modules.zip 包，不用 npm 安装依赖 ，
    webpack.config.js 中，cdnPrefix = "/qdp-oasis-web/webui/vue/",// 
     本地运行的时候需要置空，打包的时候需要带上
```
    node server.js // 启动服务
    npm run dist // 打包代码
```

vueNew是老的计费页面对应新的业务（代码较老，目前只有基础数据部分页面在，没有重构的部分）

Vue-comego是计费往来增强大版的代码
```
    npm run dev // 运行项目
    npm run build // 打包代码提交即可
```

Vue-basic是计费的基础数据文件夹
直接解压 node_modules.zip 包，不用 npm 安装依赖，
```
    npm run dev // 运行项目
    npm run build // 打包代码提交即可
```

vue-redRush是计费红冲的业务

### 5.qdp-polestar-webui-jianye 建业报表项目
vue-JY  
```
    git@git.iqdnet.cn:qdp-h5/qdp-polestar-webui-jianye.git // 仓库地址
    npm run dev // 启动项目
```


### 6.qdp-rosetta-web 品质管理云
Vue 
```
    git@git.iqdnet.cn:qdp/qdp-rosetta-web.git // 仓库地址
    npm run dev // 运行项目
    npm run build  // 打包项目
```
#### 发布部署
打包之后把 dist文件夹放到webapp下面替换，并把dist文件里index.html覆盖外面的index.html

### 7.qdp-meter-web  计量表UI与接口项目
src/main/webapp/vue 
webpack.config.js 中，cdnPrefix = "/qdp-oasis-web/webui/vue/",// 
本地运行的时候需要置空，打包的时候需要带上
```
    npm install
    node server.js // 启动服务(http://localhost:8090)
    npm run dist // 发布代码
```
打包之后修改webapp下index.html静态资源的参数防止缓存

### 8.qdp-anchor-web 票据项目 
qdp-anchor-webui 新版前端代码 打包后distbill
```
    git@git.iqdnet.cn:qdp/qdp-anchor-web.git 
    git@git.iqdnet.cn:qdp-h5/qdp-anchor-webui.git

    npm run dev  // 运行
    npm run build // 打包

```

打包完之后把 src/assets/font文件夹下的文件拷贝到 distbill文件下 fronts文件下 提交代码
然后把整个distbill文件夹放到qdp-anchor-web/src/main/webapp文件下即可

### 9.qdp-JianYe-bigscreen-webui 河南建业BI大屏前端项目地址
```
    git@git.iqdnet.cn:qdp-h5/qdp-JianYe-bigscreen-webui.git
```
本地运行index.html 注释document.domain = "jianyewy.com";即可正常运行
这个项目部署的话需要建业自己部署 他们的git仓库名为 bigscreen
 
```
    https://bigscreen.jianyewy.com/parkNum.html // 线上大屏指标后台录入地址
    https://bigscreen.jianyewy.com/index.html // 建业大屏地址
```
 
正式环境没有qa,qa环境的时候需要在域名前面加上qa

还有一个假的大屏项目，目前没有git仓库地址，压缩包传递

### 10. qdp-YaHe-bigscreen-webui  雅荷大屏静态资源文件
```
    git@git.iqdnet.cn:qdp-h5/qdp-YaHe-bigscreen-webui.git
```


### 11.qdp-echo-webui   回访系统
```
    git@git.iqdnet.cn:qdp-h5/qdp-echo-webui.git 
    npm run dev // 运行
    npm run build // 打包
```
部署的话需要前端打包不用改东西只需要npm run build

### 12. qdp-pyramid-web 电梯
```
    git@git.iqdnet.cn:qdp/qdp-pyramid-web.git
    npm run dev // 运行
    npm run build // 打包
```
vue 项目对应webapp文件夹里面index.html
vuenew 项目对应webapp文件件里面的indexnew.html 
都需要前端打包，打包后的文件替换到webap文件夹里面，然后修改对应html后面的时间

### 13. qdp-spot-check-webui 品质抽查
```
    git@git.iqdnet.cn:qdp-h5/qdp-spot-check-webui.git
    npm run dev // 运行
    npm run build // 打包
```
 
 







