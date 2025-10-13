# VueNpmFrame

一个从零搭建的Vue3，Vue2纯净框架，用于Npm包 <br/>
A Vue3, Vue2 pure frame build up from nothing and use for npm package

Vue2的支持在Vue2分支
support for Vue2 on branch Vue2

以package.json内的name是"vue-npm-frame"为例,首先在根目录下输入 npm run link。
然后切换到用户项目根目录下输入npm run link "vue-npm-frame"，然后启动项目。<br/>
take the name like "vue-npm-frame" in the package.json file as an example, first enter npm run link in the root directory. Then switch to the root directory of the user project, enter npm run link "vue-npm-frame" and start the project.

需要安装全局yarn
require global yarn

如果项目出现警告[Vue warn]: Invalid VNode type: Symbol("Text") (symbol) ，则需要在用户项目webpack中配置：<br/>
if warning like [Vue warn]: Invalid VNode type: Symbol("Text") (symbol) appears in the project, it needs to be configured in the user project webpack:

    resolve: {
        symlinks: false, //在yarn link 入其他模块的时候统一使用同一个vue引用，避免vue3的一个报错
        alias: {
            'vue$': 'vue/dist/vue.esm-bundler.js',
            vue: path.resolve(__dirname, `../node_modules/vue`) // 定义vue路径
        },
    },

vite:
     rollupOptions: {
        // 确保外部化处理那些你不想打包进库的依赖
        external: ['vue'],
        output: {
          // 在 UMD 构建模式下为这些外部化的依赖提供一个全局变量
          globals: {
            vue: 'Vue',
          },
        },
      },    

取消链接：npm run unlink<br/>
cancel link: npm run unlink 

查看所有全局链接的名称<br/>npm ls --global --depth 0 

构建：npm run build<br/>
build: npm run build

发布：npm publish<br/>
publish: npm publish

迭代： npm version [patch,minor,major]，然后 npm publish<br/>
patch： 修复bug、微小改动，改变版本号第三位<br/>
minor： 上线新功能，并对当前版本已有功能模块不影响，改变版本号第二位<br/>
major： 上线多个新功能模块，并对当前版本已有功能有影响，改变版本号第一位<br/>
iteration: npm version [patch,minor,major], then npm publish<br/>
patch: fix bugs, make little changes, and change the third digit of the version number. <br/>
major: new functions will be launched, and the existing function modules of the current version will not be affected. The second digit of the version number will be changed.<br/>
major: several new function modules will be launched, which will affect the existing functions of current version. The first digit of the version number will be changed.


安装：npm i vue-npm-frame<br/>
install: npm i vue-npm-frame

当使用vue样式时需要单独引入<br/>
import 'vue-npm-frame/style'<br/>
style need to be import individually when using vue style<br/>
import 'vue-npm-frame/style'

改变package.json内的name后请更新index.d.ts文件内的声明
after changing name in package.json, please update declare in file index.d.ts
