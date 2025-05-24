# cyber-record
纯python代码实现的cyber-record读写工具，支持bazel构建。
基于cyber-record 0.1.12的whl包源码，如果你的项目没有protobuf高版本兼容性问题，可以继续使用`pip install cyber-record`安装。

# 为什么创建这个代码仓库？
1. 阿波罗项目官方的cyber record的python读写库基于C++，并且需要引入bazel编译环境和对应的apollo自定义构建规则，对于较为轻量的record分析项目不友好。
2. 第三方的纯python实现的pip包已长时间不更新，上次更新的时间是2022年且限制最高使用protobuf的pip包版本为0.1.12，与我使用的版本发生了冲突。
- 因此我需要一个轻量的纯python实现的cyber record读写工具，支持任意的protobuf版本。
- 没有将其打包成新的whl，是因为这样直接将源码拷贝到项目中，方便用户根据自己的protobuf版本进行更新，部分API也需要根据protobuf的版本进行调整。

# 如何使用？
- bazel环境：
1. 安装bazel环境，准备好`WORKSPACE`文件和对应的`requirements`配置（`BUILD`文件中需要调用`requirement(protobuf)`）；
2. 将本仓库克隆到本地，并将`cyber_record`复制到项目顶层目录（可以调整路径，但需要修改源文件中的`import`路径和`BUILD`文件中的依赖路径）；
3. 使用bazel命令编译；
- 非bazel环境：
1. 克隆这个仓库，并将，并将`cyber_record`复制到项目顶层目录；
2. 安装protobuf的pip包：`pip install protobuf==6.31.0`；
3. 可选项：使用protoc（本地安装过proto的compiler）编译仓库内的proto文件，生成pb2.py并替换仓库内对应文件：`protoc --python_out=. *.proto`

# 更新日志:
## 日期 2025.05.24，版本 0.0.2
1. 更新获取`message_type`方法以适配新的protobuf版本；
2. 修复`README.md`中更新日志的版本信息；
## 日期 2025.05.24，版本 0.0.1
1. 基于cyber-record 0.1.12提取源码；
2. 增加相应的`BUILD`文件用于编译；
3. 从阿波罗项目中找到对应的`.proto`文件用于编译中替换`pb2.py`文件（使用libprotoc 28.3生成`pb2.py`未发现与原始包中文件区别，并可正常使用）; 
6. 删除没有调用过的`.py`文件；
7. 删除多余的`.pyc`文件；
8. 使用black-formatter格式化代码；
