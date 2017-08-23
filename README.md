# webpack-configuration-templates

Contains [webpack](https://webpack.js.org/) configuration templates to be
extended by my build scripts. You probably shouldn't use this.


## `webpack.config.js` example

```javascript
const extendDefaultTypeScriptConfiguration = require("webpack-configuration-templates").extendDefaultTypeScriptConfiguration;
const UglifyJSPlugin = require("uglifyjs-webpack-plugin");



module.exports = [
    
    /* Main application for execution by browser
     */
    extendDefaultTypeScriptConfiguration({
        entry: "./src/main.ts",
        
        output: {
            path: __dirname + "/target",
            filename: "main.js"
        },
        
        target: 'web',
        
        plugins: [
            new UglifyJSPlugin()
        ]
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
