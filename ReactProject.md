87447089lGV!
87447089!Lgv
87447089!Lgv
#创建typescript项目
yarn create react-app my-app --template typescript  

#阻止默认打开浏览器
创建.env文件  BROWSER=none

# .gitignore 
(webstorm) 去除/.idea      用git status查看状态  如果发现/.idea 有变更  需要运行 git rm -r --cached .idea 从git中删除
(vs code)去除/。vscode

#css normalize 
在index.css 添加@import-normalize 可以保证在不同的浏览器默认样式基本上相似
normalize 是让css在不同浏览器 默认样式保持一致   reset是把默认样式去掉

#使用SCSS
由于node sass不太好用  所以使用dart sass代替  但是react 不支持dart sass   最后使用偷梁换柱法   运行命令安装node sass 实际安装的是dart sass
yarn add node-sass@npm:dart-sass

1.我想让React 应用sass
2.而node-sass 有两个缺点，下载速度慢，本地编译慢
3.于是我使用dart-sass,去替代node sass
4.但是react不支持dart-sass  
5.后来我发现npm 6.9的新功能  叫做package alias
6.npm install node-sass@npm:dart-sass 可以做到偷梁换柱 


# 优化import
css @import 是不用优化的 react支持直接使用src目录下的目录直接引入
js import 需要绝对引入  修改tsconfig.json   compilerOptions 选项添加 "baseUrl": "src"


# styled-component
npm install --save styled-components
yarn  add --save styled-components
因为使用的是ts 所有还需要下载声明文件 yarn add --dev @types/styled-components
安装styled-components 是有提示的哦


#安装router
yarn add react-router-dom  如果使用了ts别忘了安装声明文件哦
Nav记得用NavLink哦


#导航栏 封装Layout 

# 安装svg sprite  
弹出eject 
安装  yarn add svg-sprite-loader -D     yarn add svgo svgo-loader -D
配置test svg

#引入一个目录 
const importAll = (requireContext:__WebpackModuleApi.RequireContext)=>requireContext.keys().forEach(requireContext)
try{
    importAll(require.context('../assets/icon',true,/\.svg$/))
}catch(error){
    console.log(error)
}
类型会报错，安装yarn add --dev @types/webpack-env

# 删除svg颜色 
svgo-loader的options 选项加入plugins:[{removeAttrs:{attrs:'fill'}]



