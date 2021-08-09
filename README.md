# ddd-web-archetype
采用领域驱动设计的web项目脚手架

## infrastructure模块
基础设施层，包括http，gRPC，数据库访问、消息、缓存组件，同时依赖domain层实现其定义的各种接口

## domain模块
领域层，负责定义领域模型，不依赖web框架和其他模块，通过定义接口并由infra模块实现来访问外部资源

## application模块
应用层，负责领域层的调度和数据查询，依赖domain模块和infra模块，

## ui模块
网络层，负责定义和提供对外的各种协议的接口，例如：HTTP、gRPC、Dubbo等，只依赖app模块

# maven archetype
## 使用maven-archetype-archetype生成maven-archetype的脚手架
```
mvn archetype:generate \
    -DarchetypeGroupId=org.apache.maven.archetypes \
    -DarchetypeArtifactId=maven-archetype-archetype \
    -DarchetypeVersion=1.4
```

## 修改 archetype-metadata.xml

## 安装到本地
`mvn install`

## 使用
```
mvn archetype:generate \
    -DarchetypeGroupId=com.jingqingyun \
    -DarchetypeArtifactId=ddd-web-archetype \
    -DarchetypeVersion=1.0-SNAPSHOT \
    -DgroupId=com.jingqingyun \
    -DartifactId=demo \
    -Dversion=1.0-SNAPSHOT \
    -Dpackage=com.jingqingyun.demo
```
或者使用交互模式: `mvn archetype:generate -DarchetypeCatalog=local`