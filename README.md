#Coding Standard Files
This repository has files to use for code validation in PhpStorm and in Magento projects.
 
* Load _PhpStorm-settings-codings-standards.jar_ from "File > Import Settings..." option.
* Load _PhpStorm-php-code-style.xml_ from "File > Default Settings... / Settings..." and "Editor > Code Style > Import Scheme > Intellij IDEA code style XML"   


## Code sniffer & Mess detector
You'll need to install some php packages in your environment to run phar files and read xml files from PhpStorm:
```shell
sudo apt-get install php7.0 php7.0-xml -y
```

## ESLint & JSHint

### Install Node.js and NPM
From https://www.npmjs.com/package/eslint

```shell
sudo apt-get install npm
npm install eslint --save-dev
```

## Errors installing management

###PhpStorm - Configure Node.js and NPM
https://www.jetbrains.com/help/phpstorm/2016.2/using-javascript-code-quality-tools.html#installESLint
https://stackoverflow.com/questions/36223947/webstorm-error-please-specify-npm-package#36261165

Fixing specific errors
```shell
npm install eslint-plugin-import
npm install eslint-plugin-node
npm install eslint-plugin-standard
npm install ...
```