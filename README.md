# Coding Standard Files
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

### PhpStorm - Configure Node.js and NPM
https://www.jetbrains.com/help/phpstorm/2016.2/using-javascript-code-quality-tools.html#installESLint
https://stackoverflow.com/questions/36223947/webstorm-error-please-specify-npm-package#36261165

Fixing specific errors
```shell
npm install eslint-plugin-import
npm install eslint-plugin-node
npm install eslint-plugin-standard
npm install ...
```

## Update composer.json in Magento projects

Until Onestic repositories be updated, they'll be loaded from github url.

mnsami/composer-custom-directory-installer is used to add repo files to /tools folder with "installer-paths" extra params.

phpro/grumphp is added to check code before commit it config file is loaded as config-default-path param says.

sstalle/php7cc, squizlabs/php_codesniffer and phpmd/phpmd are added for use by grumphp.

So add this params to composer.json:

```json
  "repositories": [
    {
      "type": "vcs",
      "url": "https://github.com/onestic/coding-standard.git"
    },
    {
      "type": "vcs",
      "url": "https://github.com/onestic/coding-standard-files.git"
    }
  ],
  "require": {
    "mnsami/composer-custom-directory-installer": "1.1.*",
    "onestic/coding-standard": "dev-master",
    "onestic/coding-standard-files": "dev-master"
  },
  "require-dev": {
    "phpro/grumphp": "^0.13.1",
    "sstalle/php7cc": "1.2.*",
    "squizlabs/php_codesniffer": "3.2.*",
    "phpmd/phpmd": "2.6.*"
  },
  "extra": {
    "installer-paths": {
      "./tools/grumphp/": ["phpro/grumphp"],
      "./tools/coding-standard/": ["onestic/coding-standard"],
      "./tools/coding-standard-files/": ["onestic/coding-standard-files"]
    },
    "grumphp": {
      "config-default-path": "tools/coding-standard-files/grumphp/grumphp.yml"
    }
  },
```

## Grumphp

Tool for validating your code before commit it to repository.

Complete info in:

https://github.com/phpro/grumphp