### 一步到位
```
# Windows Command Prompt
# Installation:
cd <installation-path> # the project will be cloned to <installation-path>\blog\
git clone https://gitee.com/caochenlei/blog
cd .\blog\blog-server\
mvn install
cd ..\blog-manage\
npm cache clear --force
npm install --legacy-peer-deps
cd ..\blog-front\
npm cache clear --force
npm install --legacy-peer-deps
cd ..

# Configure:
application.yml中
server.spring.datasource.username/password修改

# Run:
cd <installation-path>
cd .\blog-server\
start mvn spring-boot:run
cd ..\blog-manage\
start npm start
cd ..\blog-front\
start npm start
```

### 前端项目文件结构  
#### 前端项目运行方式
Node.js安装目录下的node.exe  
npm包管理器下常用npm start指令执行项目  
start代表的是包管理配置package.json文件中的一段脚本  
React项目下一般采用craco start指令(craco: Create React App ...)  
然后项目src目录下的index文件会被执行(扩展名好像js和tsx都可以)  
所以从index文件开始看起，一步一步搜索相关API，知道具体的逻辑，然后就可以改动了

# 项目地址1：https://github.com/Raysmond/SpringBlog/

这个有问题，不用了。
<!--
步骤:

装MySQL Server并启动（注意把对应防火墙关掉），连接到数据库并创建数据库实例（不知道能不能叫实例）：spring_blog_dev, spring_blog_prod

装Redis并启动（Redis好像要运行在\*nix系统上，可以用WSL windows subsystem for linux）

git clone

改变三个配置文件：src\main\resources\templates下的xml文件(spring:datasource.url|username|password)

.\gradlew build

cd .\build\libs\

java -jar SpringBlog-0.1.jar --spring.profiles.active=prod

最后在浏览器输入localhost:8080就可以访问了，不过可能会有一些小问题
-->

# 项目地址2： https://gitee.com/caochenlei/blog

1.用root账户连接到本地MySQL数据库，并执行blog-server项目下的blog.sql文件

装maven(或者IDE帮你装），在blog-server项目下执行`mvn install`安装依赖

配置application.yml文件（特别是数据库账户和密码）

执行`mvn spring-boot:run`

2.blog-manage项目

安装Node.js

执行`npm install --legacy-peer-deps`（后面那个参数好像是为了防止不同版本嵌套调用报错）

执行报错可以尝试先执行一遍`npm cache clear --force`

执行`npm start`运行

3.blog-front项目

`npm install -legacy-peer-deps`

`npm start`

后台地址:localhost:4000 管理员默认用户名密码:zhangsan 123456
