0. **npm help**     
  查看某条命令的详细帮助，例如：npm help install系统在默认浏览器打开本地nodejs安装包的文件/nodejs/node_modules/npm/html/doc/cli/npm-install.html
1. **npm install**
  - 1.1 npm install 无参数：安装package.json中所有的依赖包
  - 1.2 npm install vue 默认安装最新版本
  - 1.3 npm install vue@2.1.0 安装指定版本的包
  > 项目对模块的依赖可以使用下面的 3 种方法来表示（假设当前版本号是 1.1.0 ）：
  >  - 兼容模块新发布的补丁版本：~1.1.0、1.1.x、1.1
  >  - 兼容模块新发布的小版本、补丁版本：^1.1.0、1.x、1
  >  - 兼容模块新发布的大版本、小版本、补丁版本：*、x 
  - 1.4 npm install gulp --save||-S 安装包信息将加入到dependencies
  - 1.5 npm install gulp --save-dev||-D 安装包信息将加入到devDependencies
  - 1.6 npm install gulp --save-exact||-E 精确安装指定模块版本

2. **npm uninstall**  
  参数参照 **npm install**

3. **npm update**  
  更新模块

4. **npm ls**  
  查看安装的模块

5. **npm init**  
  在项目中引导创建一个package.json文件， -y参数表示生成默认package.json而在命令行里不询问任何问题。

6. **npm root**  
  输出node_modules的路径，加上-g参数输出全局环境的node_modules的路径

7. **npm config**     
  对于config这块用得最多应该是设置代理，解决npm安装一些模块失败的问题.例如：    
  npm config set registry="http://r.cnpmjs.org"   
  也可以临时配置，如安装淘宝镜像    
  npm install -g cnpm --registry=https://registry.npm.taobao.org