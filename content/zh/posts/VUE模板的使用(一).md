---
title: VUE模板的使用(一)
date: 2021-12-30T16:32:06+09:00
description: VUE模板的使用
draft: false
hideToc: false
enableToc: true ##侧边栏目录
enableTocContent: false ##文章内部的目录
author: wty                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                
authorEmoji: 🤖
tags:
- VUE
- vue-admin-template
categories:
- 前端 ##series:-Themes Guide
image: /images/feature1/vue.jpg
---

1. ### 拉取git项目

   git地址为

   ```shell
   https://github.com/PanJiaChen/vue-element-admin.git
   ```

2. ### 安装依赖
   
   ```shell
   npm install
   ```
   
   ![image-20211231143942795](/images/vue/image-20211231143942795.png)
   
   等待结束就完事了！！
   
2. ### 目录结构
   
   ![](/images/vue/目录结构.png)
   
4. ### 配置信息

   #### vue.config.js
   
   这里面配置了项目的基本信息： 所使用的环境、端口号、对外路径、输入文件路径等信息 , 可以看到我们使用的dev开发环境，下面将查看开发环境的配置

   ![](/images/vue/vue_config.jpg)

   #### .env.development

   在这里会标注我们后台的路径， 此时因为使用的是mock数据， 所有只是提供了一下路径而已。以及标注当前文件的类型
   
   ENV = ‘development’ 此时便引入了与后端数据交互， 与后端的交互接口都在 api的文件家里面。

   ![](/images/vue/后端路径配置.jpg)

5. ### 文件分析

   #### API文件夹

   使用user.js举例 , 可以看到这个文件会向后端发送http请求， 但是它使用的是 /utils/request 里面的内容

   先说明此文件的作用， 在这个开源框架中与后端交互使用的是 axios 组件。指定请求的路径、类型、请求参数、请求体参数， 就可以执行异步亲求了。下一步介绍 /utils/request。

   ![](/images/vue/api.jpg)

   #### /utils/request

   首先创建一个axios的实例， 对于这个实例需要设定的有： 基本的URL、以及请求超时的。

   ![](/images/vue/request.jpg)

   第二步是添加拦截器， axios每次请求都会经过这个拦截器。 store.getters.token 首先从全局状态管理那里判断 token , 有的话就可以请求， 否则就抛出异常。并且可以清楚的看到如果有 token的话， 我们在请求的时候会得到当前的token 并且直接添加到请求头中， 以便后端得到当前登录的信息。
   ![](/images/vue/请求的拦截器.jpg)

   下面是对返回结果的拦截， 在这里会判断返回结果中的状态码， 根据状态码来判断这次请求的状态如何。

   ```vue
   // response interceptor
   service.interceptors.response.use(
     /**
      * If you want to get http information such as headers or status
      * Please return  response => response
     */
   
     /**
      * Determine the request status by custom code
      * Here is just an example
      * You can also judge the status by HTTP Status Code
      */
     response => {
       const res = response.data
   
       // if the custom code is not 20000, it is judged as an error.
       if (res.code !== 20000) {
         Message({
           message: res.message || 'Error',
           type: 'error',
           duration: 5 * 1000
         })
   
         // 50008: Illegal token; 50012: Other clients logged in; 50014: Token expired;
         if (res.code === 50008 || res.code === 50012 || res.code === 50014) {
           // to re-login
           MessageBox.confirm('You have been logged out, you can cancel to stay on this page, or log in again', 'Confirm logout', {
             confirmButtonText: 'Re-Login',
             cancelButtonText: 'Cancel',
             type: 'warning'
           }).then(() => {
             store.dispatch('user/resetToken').then(() => {
               location.reload()
             })
           })
         }
         return Promise.reject(new Error(res.message || 'Error'))
       } else {
         return res
       }
     },
     error => {
       console.log('err' + error) // for debug
       Message({
         message: error.message,
         type: 'error',
         duration: 5 * 1000
       })
       return Promise.reject(error)
     }
   )
   ```

   最后将 axios的实例导出 export default service， 在这里我们看到了 store.getters.token 以及文件最上面的导入

   ```vue
   import store from '@ /store'
   store.getters.token // 下一步查看  /store  这个文件夹
   ```

   #### /store

   简单介绍此文件中几个重要的知识点

    State提供唯一的公共数据源，所有共享的数据都要统一放到Store中的State中存储
    Mutation用于修改变更$store中的数据
   在mutations中不能编写异步的代码，会导致vue调试器的显示出错。在vuex中我们可以使用Action来执行异步操作。
   Getter用于对Store中的数据进行加工处理形成新的数据
   它只会包装Store中保存的数据，并不会修改Store中保存的数据，当Store中的数据发生变化时，Getter生成的内容也会随之变化

   ```vue
   token: state => state.user.token,
   ```

   在 gettes 文件中我们看到了 token 这个标识， 其中 gettes 文件就是为了我们方便从全局状态管理中获取数据的工具， 在这里可以得到当前的 token 。

   此文件主要是使用了 vuex , 而 vuex 是 vue中的全局的状态管理， 方便我们进行组件之间的数据传递。基本使用如下

   ```vue
   this.$store.state.count // 得到store中值
   
   // 调用Acton中的异步方法 user.js 中的login 方法  ， 这个是 /veew/login 文件中的代码 
   this.$store.dispatch('user/login', this.loginForm).then(() => {
        this.$router.push({path: this.redirect || '/'})
         this.loading = false
   })
   ```

   #### token 相关的

   ```vue
     RESET_STATE: (state) => {
       Object.assign(state, getDefaultState())
     },
     SET_TOKEN: (state, token) => {
       state.token = token
     },
   ```

   #### 登录相关的

   举例说明 login 方法， 首先 传入 {commit} 以及在方法中 commit(‘SET_TOKEN’, data.token) 这两个的作用是执行 action 中异步方法的简写， 组用就是设置 token 的值， 我们知道修改 store中的数据需要使用 Mutation 就是会调用上面的 SET_TOKEN 把 后端返回的token 保存到vuex中， 并且使用 setToken(data.token) 方法把 token写入到 cookie中 以便我们每次请求都可以带上这个 cookie , 并且能够解析出当前登录的用户 。

   ```vue
    // user login
     login({commit}, userInfo) {
       console.log('login')
       const {username, password} = userInfo
       console.log("user info ->>>>" + username + "=>>>" + password)
       return new Promise((resolve, reject) => {
         login({username: username.trim(), password: password}).then(response => {
           const {data} = response
           commit('SET_TOKEN', data.token)
           console.log(data.token)
   
           setToken(data.token)
           resolve()
         }).catch(error => {
   
           reject(error)
         })
       })
     },
   ```

   在这个文件中我们还可以观察到最上面存在组件的导入， 这就和之前的说明相匹配。

   ```vue
   import {login, logout, getInfo} from '@/api/user'
   import {getToken, setToken, removeToken} from '@/utils/auth'
   import {resetRouter} from '@/router'
   
   ```

   #### main.js

   这个是项目的入口文件， 在这个入口文件中， 我们看到当前是使用mock数据， 并且全局挂在 element - ui 以及在vue的实例中挂载了 路由、store (vuex) ， 那下一步开始讲解路由

   ```vue
   if (process.env.NODE_ENV === 'production') {
     const { mockXHR } = require('../mock')
     mockXHR()
   }
   
   // set ElementUI lang to EN
   // Vue.use(ElementUI, { locale })
   // 如果想要中文版 element-ui，按如下方式声明
   Vue.use(ElementUI)
   
   Vue.config.productionTip = false
   
   new Vue({
     el: '#app',
     router,
     store,
     render: h => h(App)
   })
   ```

   #### / router

   使用vue router的第一步是需要一个路由表、以及把路由表加载到路由实例中， 最后把路由实例导出。下面就是定义的路由表， 对于路由表 中包括

   path : 访问的路径
   component ： 此路由对于的组件
   hidden ： 是否在界面显示此路由
   meta ： 设置路由的属性， 图标之类的
   name : 路由名字
   children ： 该路由下的子路由， 效果就是二级菜单

   ```vue
   export const constantRoutes = [
     {
       path: '/login',
       component: () => import('@/views/login/index'),
       hidden: true,
             children: [
         {
           path: 'https://panjiachen.github.io/vue-element-admin-site/#/',
           meta: {title: 'External Link', icon: 'link'}
         }
     },
     {
       path: '/404',
       component: () => import('@/views/404'),
       hidden: true
     },
   ```

   下面就是新建路由实例， 以及添加路由表， 导出路由。 上面介绍到了组件， 下一步解释路由对应的组件

   ```vue
   const createRouter = () => new Router({
     // mode: 'history', // require service support
     scrollBehavior: () => ({y: 0}),
     routes: constantRoutes
   })
   
   const router = createRouter()
   
   // Detail see: https://github.com/vuejs/vue-router/issues/1234#issuecomment-357941465
   export function resetRouter() {
     const newRouter = createRouter()
     router.matcher = newRouter.matcher // reset router
   }
   
   export default router
   ```

   #### /view/login/login.vue

   组件的概念比较广泛，可以暂时理解为一个界面， 下面是登录的界面， name: ‘Login’, 定义的组件名称。 当在路由表中配置了此路由的信息后，就可以在使用中根据对应的path 来访问此路由。

   ```vue
   <template>
     <div class="login-container">
     </div>
   </template>
   <script>
     import {validUsername} from '@/utils/validate'
     export default {
       name: 'Login',
       data() {
       },
       watch: {
       },
       methods: {
       }
     }
   </script>
   
   <style lang="scss">
   
   </style>
   ```

   #### permission.js

   此文件是用来配合路由使用的， 对于vue router 而言它还附带了一些其他的信息， 比如路由守卫， 在路由守卫中我们可以在路由跳转之前来做一些事情的。

   对于此项目来讲；

   1、首先判断是否有token

   2、没有token ， 如果在白名单里面， 就直接放行， 否则就直接强制跳转登录。

   3、有token , 如果是 /login 就就直接到 根目录下

   4、不是 /login 就去 store 里面找 当前用户的信息， 然后在放行

   ```vue
   const whiteList = ['/login'] // no redirect whitelist
   
   router.beforeEach(async(to, from, next) => {
     // start progress bar
     NProgress.start()
     // set page title
     document.title = getPageTitle(to.meta.title)
     // determine whether the user has logged in
     //console.log(getToken())
     const hasToken = getToken()
   
     if (hasToken) {
       if (to.path === '/login') {
         // if is logged in, redirect to the home page
         next({ path: '/' })
         NProgress.done()
       } else {
         const hasGetUserInfo = store.getters.name
         if (hasGetUserInfo) {
           next()
         } else {
           try {
             // get user info
             await store.dispatch('user/getInfo')
             next()
           } catch (error) {
             // remove token and go to login page to re-login
             await store.dispatch('user/resetToken')
             Message.error(error || 'Has Error')
             next(`/login?redirect=${to.path}`)
             NProgress.done()
           }
         }
       }
     } else {
       /* has no token*/
       if (whiteList.indexOf(to.path) !== -1) {
         // in the free login whitelist, go directly
         next()
       } else {
         // other pages that do not have permission to access are redirected to the login page.
         next(`/login?redirect=${to.path}`)
         NProgress.done()
       }
     }
   })
   ```

   参考博文：https://blog.csdn.net/qq_41291945/article/details/107748231
