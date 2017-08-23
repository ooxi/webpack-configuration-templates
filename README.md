# webpack-configuration-templates

Contains [webpack](https://webpack.js.org/) configuration templates to be
extended by my build scripts. You probably shouldn't use this.



## `webpack.config.js` example

```javascript
const extendDefaultTypeScriptConfiguration = require("webpack-configuration-templates")
    .extendDefaultTypeScriptConfiguration;


module.exports = [
    
    /* Main application for execution by browser
     */
    extendDefaultTypeScriptConfiguration({
        entry: "./src/main.ts",
        
        output: {
            path: __dirname + "/target",
            filename: "main.js"
        },
        
        target: 'web'
    }),
    
    /* Test case for execution by node.js
     */
    extendDefaultTypeScriptConfiguration({
        entry: "./src/test.ts",

        output: {
            path: __dirname + "/target",
            filename: "test.js"
        },

        target: 'node'
    })
];
```


## Changelog

 * [0.1.1](https://github.com/ooxi/webpack-configuration-templates/releases/tag/v0.1.1)
   * Published on npm
   * [mini-cross](https://github.com/ooxi/mini-cross) support
   * Extended [package.json](package.json) with `repository` information

 * [0.1.0](https://github.com/ooxi/webpack-configuration-templates/releases/tag/v0.1.0)
   * Initial development
