遵循[JEP 322](https://openjdk.org/jeps/322)的版本号方案，设计一款管理jdk版本的工具，全名Java Version Manager，简称jvm。

该仓库的jdk-versions分支用于存储和管理可供下载的jdk信息，信息文件为json格式，计划由github-actions自动生成与更新。可参考apt的设计。
由于计划使用github来提供信息，所以用户可能无法访问github，所以参考其他软件提供一个环境变量用于替换请求地址。

目前计划的jdk下载地址为官方下载地址，即openjdk、temurin、bellsoft等厂商的下载链接。需要提供代理配置，避免用户无法访问这些地址。

本地存储目录目前有两个选项：~/.jvm 和 ~/.jdks，其中.jdks与IDEA的目录冲突，所以~/.jvm的可能性更大。
该项目计划使用链接的方式，用来在不同的版本之间切换，要做到这个需要更新用户的PATH、JAVA_HOME环境变量。

该项目使用Java开发，前期只考虑windows平台，但设计时要考虑到对其他平台的兼容，后期再考虑受否支持其他平台。
