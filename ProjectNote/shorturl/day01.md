maven、xml、yml文件基础补习：

pom文件解析：
    <project>：pom文件的根标签，表示当前maven项目
    <modelVersion>：声明项目描述遵循哪一个POM模型版本
坐标相关：
    <groupId>
    > 组织/包归属|定义当前Mvaen项目李树组织名称
    > 
    <artifactId>
    > 某个具体构建或模块名|定义当前Maven项目名称
    <version>
    > 版本|定义当前项目版本号
        SNAPSHOT：功能性不稳定、尚处于开发中的版本、即快照版本
        RELEASE：功能趋于稳定、当前更新停止、可以用于发行的版本

 

Maven配置：
在pom.xml中编写<dependencies>标签
<dependencies>标签中使用<dependency>引入坐标
定义坐标的groupId、artifactId、version