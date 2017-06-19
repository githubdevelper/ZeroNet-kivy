# 编译步骤:

已在Ubuntu 16.04测试通过。

预先准备：
 - 一台手机或者armv7模拟器（目前只能在arm芯片上运行）
 - Git软件
 - Make软件
 - Docker编译环境（安装步骤见 https://docs.docker.com/engine/installation/linux/ubuntu/）

## 初始步骤
 - 首先在终端窗口中运行 `git clone https://github.com/HelloZeroNet/ZeroNet-kivy --recursive`
 - 检查 `src/zero`目录中的内容
 - 现在运行 `make prebuild`

## Docker
 - 首先需编译最新的kivy镜像，运行`make docker-build`
 - 现在运行`make docker-pre`以下载一些其他东西


### 编译
- 运行 `make docker`进行编译
- 如需测试，你需要在docker编译环境**文件夹之外**安装adb
  - 运行 `make docker-test`
  - 如果你使用模拟器在命令行之后添加`ADB_FLAG=-e`
- 如果编译成功，在bin目录中会出现ZeroNet.apk文件

### 调试
 - 运行 `make docker-test` 将记录adb logcat调试信息
 - 额外的调试信息在 `/storage/emulated/0/Android/data/net.mkg20001.zeronet/files/zero/log`文件中
