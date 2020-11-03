# Create Asp.net MVC with react js

step-1 Make an MVC PROJECT...

step-2  Open the folder where project is created...

command# 1--- > npm init -y (you have initialize packge.json file )

command # 2 ---> npm install webpack webpack-cli --save-dev (install webpack)

command # 3 ---> npm install react react-dom --save-dev (Install react libaries)

command # 4 ---->npm install @babel/core @babel/preset-react babel-loader --save-dev

(install scripts related to babel)

step-3 create a folder in script folder to create a script for all components.....

paste this code in index.js file....

-------------------------------------------------------------------------------------------------------------

import React from 'react';

import ReactDOM from 'react-dom';



const App = () => <div>Hello world!</div>;



ReactDOM.render(<App />, document.getElementById("root"));

-------------------------------------------------------------------------------------------------------------

step-4 create a config folder in script folder to configure web pack & and add webpack.config.js file and paste the follwing code.

-------------------------------------------------------------------------------------------------------------

const path = require("path");



module.exports = {

    entry: {

        index: "./Scripts/src/index.js"

    },

    output: {

        path: path.resolve(__dirname, "../dist"),

        filename: "[name].js"

    },

    module: {

        rules: [

            {

                use: {

                    loader: "babel-loader"

                },

                test: /\.js$/,

                exclude: /node_modules/ //excludes node_modules folder from being transpiled by babel. We do this because it's a waste of resources to do so.

            }

        ]

    }

}

-------------------------------------------------------------------------------------------------------------

step-5 goto root directory and create a file named as babelrc and paste the following code there



--------------------------------------------------------------

{

    "presets": [

      "@babel/preset-react"

    ],

    "plugins": [

    ]

}

------------------------------------------------------



commad # 5 ---> npm install -g webpack

command # 6---->webpack --config=Scripts/config/webpack.config.js.... done!

step-6 now paster the following code in packge.json under script object

command # 7---> npm run build

step-7 paste the following code in index.cshtml page

------------------------------------------------------



<div id="root"></div>





@Scripts.Render("~/Scripts/dist/index.js")



------------------------------------------------------

 you need to rebuild the npm......
