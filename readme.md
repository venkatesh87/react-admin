[![CircleCI branch](https://img.shields.io/circleci/project/github/duxianwei520/react/master.svg?style=flat-square)](https://circleci.com/gh/duxianwei520/react)
[![GitHub forks](https://img.shields.io/github/forks/duxianwei520/react.svg)](https://github.com/duxianwei520/react/network)
[![GitHub stars](https://img.shields.io/github/stars/duxianwei520/react.svg)](https://github.com/duxianwei520/react/stargazers)
[![GitHub issues](https://img.shields.io/github/issues/duxianwei520/react.svg)](https://github.com/duxianwei520/react/issues)
[![GitHub license](https://img.shields.io/github/license/duxianwei520/react.svg)](https://github.com/duxianwei520/react/blob/master/LICENSE)
[![Coverage Status](https://coveralls.io/repos/github/duxianwei520/react/badge.svg)](https://coveralls.io/github/duxianwei520/react)

## 项目技术栈

node8.7.0 + react@16.5.2 + redux@3.7.2 + react-router@3.2.0 + webpack@3.10.0 + axios@0.18.0 + less@2.7.1 + antd@3.18.2

## 交流
QQ群：159697743

## 项目运行


```
git clone --depth 1 https://github.com/duxianwei520/react.git  

cd react (进入项目)

npm install (安装依赖包)

npm run dll (生成持久化存储的公用js文件)

npm start (启动服务)

```
>  由于对公用的npm库做了dll化，所以要先运行npm run dll生成相应的代码,这么做的目的只是为了让静态资源缓存，目前默认是把'babel-polyfill','react', 'react-dom', 'react-router', 'axios','redux', 'redux-thunk', 'react-redux', 'react-router-redux',这几个公共库dll化了，关于这个dll命令大家可以根据需求自行去scripts/webpack.dll.config.js里自己做配置,生成自己想要的dll文件
>  现在start命令默认运行npm run dev命令和npm run mock两个命令，目的是可以直接用模拟的数据让整个项目的逻辑可以运行

### 如果有小伙伴因为网络原因npm包下载不下来，那么可以试用我已经下载好的安装包，地址在

```
https://github.com/duxianwei520/resource/blob/master/react/node_modules.rar

```

## screenshots



### login

<img src="https://github.com/duxianwei520/resource/blob/master/react/screenshots/login.gif" width="973" height="557"/>

### echart

<img src="https://github.com/duxianwei520/resource/blob/master/react/screenshots/echart.gif" width="973" height="557"/>


### set center

<img src="https://github.com/duxianwei520/resource/blob/master/react/screenshots/set.gif" width="973" height="557"/>


### webpack bundle analysis

<img src="https://github.com/duxianwei520/resource/blob/master/react/screenshots/analysis.gif" width="973" height="557"/>

### build dist folder

<img src="https://github.com/duxianwei520/resource/blob/master/react/screenshots/dist.gif" width="973" height="557"/>


最后的构建命令
```
npm run build (正式环境的打包部署)
npm run testing (测试环境的打包部署命令，可以根据需求配置)

```

服务端返回的数据格式也是标准的json，如下所示

```
{
  data: {
    totalCount: 100,
    currentPage: 1,
    pageSize: 10,
    'list': [
    ],
  },
  msg: '',
  status: 1,
}

```
所有异步请求返回都会经过configs里面的ajax.js做处理，如果请求没有任何问题，那status返回值是1；
如果请求错误，比如说参数错误或者其他报错之类的，那status返回值就是0；
如果status值是-1，表示登录超时，那么就会跳出登录。
这些参数都可以根据实际情况进行调整，报错或者成功的提示信息放在msg里面返回。
当前项目集成了完整的用户管理、角色管理、模块管理等基本的权限管理功能，小伙伴们一定要同时启动npm run mock才可以看到噢

这个react的项目我有在跟nodejs的express框架配合做接口的开发，可以不靠后端输出数据库真实的数据，仓库地址在

```
https://github.com/duxianwei520/express

```
还有一个原生的nodejs版本的，仓库库地址是

```
https://github.com/duxianwei520/node

```
基本功能差不多，目前实现了注册登录以及获取用户信息等3个接口的真实api


## 说明

>  开发环境 win10  Chrome 63.0.3239.132（正式版本） （32 位） nodejs 8.7.0

>  如果npm install太慢导致有些npm依赖包下载失败 你可以看控制台的报错信息，再手动npm install 具体的开发包，可以使用淘宝的注册源，命令如下

```
npm install -g cnpm --registry=https://registry.npm.taobao.org 

```


>  如有问题请直接在 Issues 中提，或者您发现问题并有非常好的解决方案，欢迎 PR 👍

### 大部分人项目启动不起来的原因，要么是node版本太高后者太低，要么就是npm安装的时候有些依赖包没有下载完全，当前的demo肯定是可以跑起来的

### 取消http请求示例：
```
import axios from 'axios'
const axiosHandle = axios.CancelToken.source()

login(){
  this.props.dispatch(fetchLogin(values, (res) => {},(error)=>{},axiosHandle)
  取消请求的操作
  setTimeout(() => {
    axiosHandle.cancel('手动取消。')
  }, 3000)
}

```


## 功能一览
- [√] 登录，以及登录权限控制
- [√] 项目公用npm模块dll化
- [√] redux完整示范
- [√] mockjs模拟后端返回接口
- [√] axios异步请求跨域的设置
- [√] 实时的webpack包大小预览,方便优化
- [√] draftjs编辑器



## License

[MIT](https://github.com/duxianwei520/react/blob/master/LICENSE)


## 交流
想跟其他的使用react的小伙伴们交流的话，可以加入我创建的reactQQ群：159697743

## 转发 
duxianwei520
