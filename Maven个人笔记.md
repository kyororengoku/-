# Maven

## 仓库

> 存储各式各样的jar包

### 仓库分类

1. 本地仓库
2. 远程仓库

### 本地仓库配置

```xml
<localRepository>/Users/shawn/developKits/apache-maven-3.8.4/conf/repository</localRepository>
```

### 仓库镜像配置

```xml
<!-- 配置具体仓库的下载镜像 -->
<mirror>
    <!-- 此镜像的唯一标识符，用来区分不同的mirror元素 -->
    <id>ali-maven</id>
    <!-- 对哪种仓库进行镜像，简单说就是代替哪个仓库 -->
    <mirrorOf>central</mirrorOf>
    <!-- 镜像的名称 -->
    <name>aliyun maven</name>
    <!-- 镜像的URL -->
    <url>http://maven.aliyun.com/nexus/content/groups/public/</url>
</mirror>
```

## 坐标

可以根据坐标在仓库中精准定位到资源

### Maven坐标的组成

```pom
<groupId>org.kyojurorengoku</groupId> 组织Id
<artifactId>MyProject</artifactId> 项目名称
<version>1.0-SNAPSHOT</version> 项目名称
```

## Maven项目构建命令

### Maven构建生命周期

| 阶段          | 处理     | 描述                                                     |
| :------------ | :------- | :------------------------------------------------------- |
| 验证 validate | 验证项目 | 验证项目是否正确且所有必须信息是可用的                   |
| 编译 compile  | 执行编译 | 源代码编译在此阶段完成                                   |
| 测试 Test     | 测试     | 使用适当的单元测试框架（例如JUnit）运行测试。            |
| 包装 package  | 打包     | 创建JAR/WAR包如在 pom.xml 中定义提及的包                 |
| 检查 verify   | 检查     | 对集成测试的结果进行检查，以保证质量达标                 |
| 安装 install  | 安装     | 安装打包的项目到本地仓库，以供其他项目使用               |
| 部署 deploy   | 部署     | 拷贝最终的工程包到远程仓库中，以共享给其他开发人员和工程 |

其他详情：[Clean、Site](https://www.runoob.com/maven/maven-build-life-cycle.html)

## 依赖

### 依赖管理

```xml
<dependencies>
    //单个依赖
  <dependency>
    <groupId>junit</groupId>
    <artifactId>junit</artifactId>
    <version>4.11</version>
    <scope>test</scope>
  </dependency>
</dependencies>
```

