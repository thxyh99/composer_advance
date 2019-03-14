# Composer如何创建并发布一个自己的包

### **有哪些步骤**

1. 编写代码
1. 编写composer.json文件,选择合适的包加载方式
1. github拖管代码
1. 提交包到[packagist](https://packagist.org)
1. 配置github hook自动更新

### **编写类库代码**

作为一个使用composer的现代php程序员，建议使用 [psr4](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-4-autoloader.md) 标准 来组织代码（这不是必须，但是建议），代码参见github

### **编写composer.json文件**

    {
      "name": "thxyh99/zendframework",
      "description": "Just for fun",
      "require": {
      },
      "autoload": {
	    "psr-4": {
	      
	    }
      }
    }


### **github拖管代码**

在github上创建一个项目，提交代码。同时建议发布一个稳定的tag。

这不是必须，可以选择其他代码仓库，git或者svn都可以，但是建议放在这。

### **提交包到 packagist**

packagist 是 Composer 的主要资源库，原生支持。任何支持 Composer 的开源项目应该发布自己的包在 packagist 上。

当然这也不是必须，但是建议，毕竟 packagist 使用的人最多，资源最丰富。

登录[packagist.org](https://packagist.org/packages/submit) 官方站点，如果没有账号，直接选择 github 账号登录就好了

输入项目的 github 地址，点击check，判断项目代码中包含 composer.json 文件，包名不重复，就可以直接 submit 了。

### **配置github hook自动更新**

配置自动更新的好处是，如果提交了代码，或者发布了新的版本，packagist 会自动拉取最新的代码供他人使用。

    To do so you can:
	1.Go to your GitHub repository 
    2.Click the “Webhooks” button 
    3.Add Webhooks

### **使用**


 `composer require thxyh99/zendframework dev-master`
