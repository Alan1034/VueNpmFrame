# VueNpmFrame

一个从零搭建的Vue3纯净框架，用于Npm包 <br/>
A Vue3 pure frame build up from nothing and use for npm package

以package.json内的name是"money-sign"为例,首先在根目录下输入 yarn link。然后切换到用户项目根目录下输入yarn link "money-sign"，然后启动项目。<br/>
take the name like "money-sign" in the package.json file as an example, first enter yarn link in the root directory. Then switch to the root directory of the user project, enter yarn link "money-sign" and start the project.


如果项目出现警告[Vue warn]: Invalid VNode type: Symbol("Text") (symbol) ，则需要在用户项目webpack中配置：<br/>
if warning like [Vue warn]: Invalid VNode type: Symbol("Text") (symbol) appears in the project, it needs to be configured in the user project webpack:

    resolve: {
        symlinks: false, //在yarn link 入其他模块的时候统一使用同一个vue引用，避免vue3的一个报错
        alias: {
            'vue$': 'vue/dist/vue.esm-bundler.js',
            vue: path.resolve(__dirname, `../node_modules/vue`) // 定义vue路径
        },
    },

取消链接输入yarn unlink<br/>
cancel link enter yarn unlink 