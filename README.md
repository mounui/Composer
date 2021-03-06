# Composer
## resource

- Composer官方网站：https://getcomposer.org/
- Composer中文站点：http://www.phpcomposer.com/

## Composer安装

### 下载 Composer

> 安装前请务必确保已经正确安装了 [PHP](http://php.net/)。打开命令行窗口并执行 `php -v` 查看是否正确输出版本号。

打开命令行并依次执行下列命令安装最新版本的 Composer：

复制

```bash
php -r "copy('https://install.phpcomposer.com/installer', 'composer-setup.php');"
```

复制

```bash
php composer-setup.php
```

复制

```bash
php -r "unlink('composer-setup.php');"
```

执行第一条命令下载下来的 `composer-setup.php` 脚本将简单地检测 `php.ini` 中的参数设置，如果某些参数未正确设置则会给出警告；然后下载最新版本的 `composer.phar` 文件到当前目录。

上述 3 条命令的作用依次是：

1. 下载安装脚本 － `composer-setup.php` － 到当前目录。
2. 执行安装过程。
3. 删除安装脚本。

### 局部安装

上述下载 Composer 的过程正确执行完毕后，可以将 `composer.phar` 文件复制到任意目录（比如项目根目录下），然后通过 `php composer.phar` 指令即可使用 Composer 了！

### 全局安装

全局安装是将 Composer 安装到系统环境变量 `PATH` 所包含的路径下面，然后就能够在命令行窗口中直接执行 `composer` 命令了。

#### Mac 或 Linux 系统：

打开命令行窗口并执行如下命令将前面下载的 `composer.phar` 文件移动到 `/usr/local/bin/`目录下面：

复制

```bash
sudo mv composer.phar /usr/local/bin/composer
```

#### Windows 系统：

1. 找到并进入 PHP 的安装目录（和你在命令行中执行的 `php` 指令应该是同一套 PHP）。
2. 将 `composer.phar` 复制到 PHP 的安装目录下面，也就是和 `php.exe` 在同一级目录。
3. 在 PHP 安装目录下新建一个 `composer.bat` 文件，并将下列代码保存到此文件中。

复制

```bash
@php "%~dp0composer.phar" %*
```

最后重新打开一个命令行窗口试一试执行 `composer --version` 看看是否正确输出版本号。

### 最后

> 提示：不要忘了经常执行 `composer selfupdate` 以保持 Composer 一直是最新版本哦！

### 关于升级 Composer

Composer 升级时是无法利用我们的镜像加速下载的，而必须连接到 Composer 国外官网的服务器上下载升级文件，某些时候就会导致升级的速度非常慢甚至失败。

这里提供一个简单的办法：

如果你的系统中已经有可以正常使用的 Composer 了，说明系统环境是符合要求的，那么只需要下载新的 Composer 文件并覆盖原来的文件即可。

首先你要确定现有的 Composer 的安装目录，然后通过下面的链接下载 `composer.phar` 文件（复制以下地址到浏览器地址栏可直接下载），

复制

```
https://install.phpcomposer.com/composer.phar
```

将前面下载的 `composer.phar` 文件覆盖系统中已经安装的 `composer.phar` 文件即可。注意，有可能在安装时将 `composer.phar` 改名为 `composer` 了，注意用同样的名字覆盖即可。