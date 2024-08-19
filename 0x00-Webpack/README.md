# Webpack

## Overview
This project covers the basics of setting up Webpack for a project, including essential concepts like entry points, output, loaders, plugins, code splitting, and configuring a development server.

## 1. Setting Up Webpack
To set up Webpack for a basic project:
- Install Webpack and Webpack CLI: 
  ```bash
  npm install --save-dev webpack webpack-cli
  ```
- Create a `webpack.config.js` file for configuration.

## 2. Entry Points, Output, and Loaders
- **Entry Point**: Specifies the main file for Webpack to start bundling.
- **Output**: Determines the output file location and filename.
- **Loaders**: Process files other than JavaScript (e.g., CSS, images):
  ```javascript
  module: {
    rules: [
      { test: /\.css$/, use: ['style-loader', 'css-loader'] }
    ]
  }
  ```

## 3. Adding Plugins
Plugins extend Webpack's functionality:
- Install and configure in the `plugins` array of the `webpack.config.js`:
  ```javascript
  const HtmlWebpackPlugin = require('html-webpack-plugin');
  module.exports = {
    plugins: [new HtmlWebpackPlugin({ template: './src/index.html' })],
  };
  ```

## 4. Code Splitting
Split your code into smaller chunks to improve load times:
- Use dynamic imports in your code:
  ```javascript
  import(/* webpackChunkName: "my-chunk-name" */ './myModule').then(module => {
    // Use the module
  });
  ```

## 5. Setting Up a Dev Server
- Install Webpack Dev Server:
  ```bash
  npm install --save-dev webpack-dev-server
  ```
- Add `devServer` configuration in `webpack.config.js`:
  ```javascript
  devServer: {
    contentBase: './dist',
    open: true
  }
  ```
- Start the server:
  ```bash
  npx webpack serve
  ```
