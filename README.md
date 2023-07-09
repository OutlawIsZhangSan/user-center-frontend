# 个人踩坑

**问题**

```
yarn : 无法加载文件 D:\node\nodejs\node_global\yarn.ps1。未对文件 D:\node\nodejs\node_global\yarn.ps1 进行数字签名。无法在当前
系统上运行该脚本。
```

**解决**

这个错误通常是由于Windows对未签名的脚本文件的安全限制导致的。为了解决这个问题，你可以尝试以下方法：

1. 开启PowerShell脚本执行权限：以管理员身份打开一个PowerShell窗口，然后输入以下命令并执行：

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

此命令将允许当前用户在本地计算机上执行不带数字签名的脚本文件。

2. 重新安装Yarn：如果第一步无效，你可以尝试重新安装Yarn。在卸载现有的Yarn后，以管理员身份运行Yarn的安装程序，按照提示重新安装。

3. 使用受信任的脚本文件：如果你不希望修改PowerShell脚本执行权限，你可以使用已经经过数字签名的Yarn脚本。从Yarn的官方网站或GitHub页面下载受信任的脚本文件，然后将其放置到你的Yarn安装目录中。

请注意，在更改系统设置或使用未签名的脚本文件时，要小心并确保你知道自己在做什么。务必确保脚本文件的来源可信，以避免潜在的安全风险。



**问题**

运行 `start` 脚本出现如下错误

```
Error: error:0308010C:digital envelope routines::unsupported
```

**解决**

修改package.json，在相关构建命令之前加入 `SET NODE_OPTIONS=--openssl-legacy-provider`

```
"start": "SET NODE_OPTIONS=--openssl-legacy-provider && cross-env UMI_ENV=dev umi dev",
```







# Ant Design Pro

This project is initialized with [Ant Design Pro](https://pro.ant.design). Follow is the quick guide for how to use.

## Environment Prepare

Install `node_modules`:

```bash
npm install
```

or

```bash
yarn
```

## Provided Scripts

Ant Design Pro provides some useful script to help you quick start and build with web project, code style check and test.

Scripts provided in `package.json`. It's safe to modify or add additional script:

### Start project

```bash
npm start
```

### Build project

```bash
npm run build
```

### Check code style

```bash
npm run lint
```

You can also use script to auto fix some lint error:

```bash
npm run lint:fix
```

### Test code

```bash
npm test
```

## More

You can view full document on our [official website](https://pro.ant.design). And welcome any feedback in our [github](https://github.com/ant-design/ant-design-pro).
