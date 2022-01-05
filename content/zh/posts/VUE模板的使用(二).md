### 后端接口

- 配置跨域

  **已拦截跨源请求：同源策略禁止读取位于 http://127.0.0.1:8080/user/login 的远程资源。（原因：CORS 请求未能成功）** 需要添加如下配置解决跨域问题！

  1. 不同主机
  2. 不同端口
  3. 不同协议

  都会产生跨域问题！

  ```java
  @Configuration
  public class CorsConfiguration implements WebMvcConfigurer {
      @Override
      public void addCorsMappings(CorsRegistry registry) {
          registry.addMapping("/**")
                  .allowedMethods("*")
                  .allowedOrigins("*")
                  .allowedHeaders("*");
      }
  }
  ```

- 登录接口

  此处需要返回的是用户信息以及登录后的token ， 后端配置：

  1. port : 8001

  2. 路径：/api

     ```java
         @GetMapping("/user/info")
         public ResultVO<HashMap> getInfo(String token) {
             log.info("get user info : " + token);
             String username = jwtConfig.getUsernameFromToken(token);
             log.info("user name : " + username);
             HashMap<Object, Object> map = new HashMap<>();
             map.put("roles", "admin");
             map.put("introduction", "I am a superadministrator");
             map.put("avatar", "https://wpimg.wallstcn.com/f778738c-e4f8-4870-b634-56703b4acafe.gif");
             map.put("name", "Super Admin");
             return ResultVOUtil.successWith(map);
         }
     
         @PostMapping("/user/login")
         public ResultVO<String> login(@RequestBody User user) {
             String token = jwtConfig.createToken(user.getUsername());
             log.info("user  " + user.toString());
             log.info("token " + token);
             return ResultVOUtil.successWith(token);
         }
     ```

  
  ## 前端修改
  
  此时我们只需要把前端的 访问 url 以及端口 请求的路径做出对应的修改即可。
  
  ### .env.development
  
  ```vue
  # just a flag
  ENV = 'development'
  # base api
  # VUE_APP_BASE_API = '/dev-api'
  VUE_APP_BASE_API = 'http://127.0.0.1:8001/api/'
  ```
  
  ### vue.config.js
  
  ```js
    devServer: {
      port: port,
      open: true,
      overlay: {
        warnings: false,
        errors: true
      }/*,
      before: require('./mock/mock-server.js')*/
    },
  ```
  
  ### [api](https://so.csdn.net/so/search?q=api)/user.js
  
  ```vue
  import request from '@/utils/request'
  
  
  export function login(data) {
    return request({
      url: '/user/login',
      method: 'post',
      data
    })
  }
  
  export function getInfo(token) {
    return request({
      url: '/user/info',
      method: 'get',
      params: { token }
    })
  }
  ```
  
  