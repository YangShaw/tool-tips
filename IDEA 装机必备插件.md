
### idea 插件

### **Alibaba Cloud Toolkit**

个人经常会有这样的需求, 每次自己更新完测试环境之后, 就需要 `maven` 打包`clean install`, 然后`copy` `jar` 包, 利用`ftp`工具上传`jar`包到测试服务器, 然后`kill` 服务, 在启动服务 `java -jar` , 有时更新频繁 这就是一件非常麻烦的事

`Cloud Toolkit` 是本地 `IDE` 插件，帮助开发者更高效地开发、测试、诊断并部署应用。通过插件，您可以将本地应用一键部署到云端`（ECS、EDAS 和 Kubernetes 等`）和任意服务器；并且它还内置了 `Arthas` 程序诊断、`Dubbo工具`、`Terminal Shell` 终端和 `MySQL` 执行器等工具。

[官网链接](https://www.aliyun.com/product/cloudtoolkit)

简单的说, 安装了这个插件之后, `idea` 就具备了一些`jenkins`的自动部署的功能

**0x01** 安装

在 `idea` 工具中` Plugins` 直接搜索安装

**0x02** 使用


在安装完成之后, 在工具栏中就会出现阿里云的按钮, **点击按钮**

![](http://193.112.98.8/atomImg/plugins/20190831235312.png?img)

然后点击 `Deploy to Host`, 然后下方就会出现添加主机页面
![](http://193.112.98.8/atomImg/plugins/20190831235513.png?img)


点击 `Add Host`

![](http://193.112.98.8/atomImg/plugins/20190831235536.png?img)

以我自己的[博客](www.atomblogs.com)为例, 输入完配置之后, 点击 `Test Connection`, 出现 `Succeeded`, 点击 `add`, 代表添加成功

![](http://193.112.98.8/atomImg/plugins/20190831235554.png?img)

然后再点击 `Deploy to Host`

![](http://193.112.98.8/atomImg/plugins/20190831235602.png?img)

点击`Run`, `idea` 便会, 先使用`maven`打包, 后发送到服务器的指定位置

![](http://193.112.98.8/atomImg/plugins/20190831235612.png?img)

![](http://193.112.98.8/atomImg/plugins/20190831235621.png?img)

后续还可以 监听启动日志, 很简单, 就是 `Advanced` 里面, 大家看看就知道了, 
后续有时间再完善笔记吧

### **阿里巴巴编码规范**

```
Alibaba Java Coding Guidelines 
```

> 实时监测代码的规范性, 从代码层面减少空指针等异常的出现
>
> 阿里巴巴出品的`java代码`规范插件, 可以扫描整个项目找到不规范的地方 并且大部分可以自动修复
>
> 虽说检测功能没有 `findbugs` 强大，但是可以自动修复, 阿里巴巴Java编码指南插件支持。
>
> 让代码变得更规范, 是我们每一位程序员都应该记在心中的事



`eg:`

- 变量驼峰命名规范

  ```java
  private String MyStudent;
  ```

  > 如上所示, 定义了一个 `String`  类型的变量 `MyStudent`, 而在编辑器中就会出现如下效果

  ![](http://193.112.98.8/atomImg/plugins/alibaba_lowerCameCase.png)

  当鼠标移到变量上时, 就会自动提示 不符合 `lowerCamelCase`命名风格

- 字符串比较提示 `equals`

  ```java
  public static void main(String[] args) {
      String str = null;
  
      if (str.equals("test")) {
      	System.out.println("success");
      }
  }
  ```

  > 当我们初学 `java`时, 很有可能会犯这样的错误, 这里很明显会报空指针异常, 而在编辑器中

  ![](http://193.112.98.8/atomImg/plugins/alibaba_equals.png)

  > 安装插件之后, 编辑器已经给出详细提示,` "test“` 应该做为 `equals`方法的调用方, 并给出了原因, 应为这样很容易导致空指针异常, 并给出了例子

- 当你的类命名不规范时

> 比如我创建了一个测试类 `test.java`, 这时运行规范实时扫描 `ctrl + shift + alt + j`, 就会出现如下提示

![](http://images.atomblogs.com/20190917091406.png)



### **翻译插件**

```
Translation
```



### **`mybatis` 插件**

```
Free Mybatis plugin
```

> 安装此插件后可以节约很多的开发时间,  在 `mapper` 层接口可以直接进入 `xml`文件中

### 插件

```
IntelliJ Lombok plugin
```

**Lombok pom.xml 文件配置**

```
<dependency>
    <groupId>org.projectlombok</groupId>
    <artifactId>lombok</artifactId>
    <version>1.16.18</version>
    <scope>provided</scope>
</dependency>
```

> 生命很宝贵, 没有必要浪费在这个重复的工作上, 尤其是如果我们使用传统的 `get` `set` 方法, 在实体类进行变更的时候, 或多添加了列, 或减少了列, 又要重新生成对应的 `get set`	 这难道不就是浪费时间浪费生命吗?



还不熟悉使用的可以看这篇文章

[Java 开发之 Lombok 必知必会](https://juejin.im/post/5cf3edf7e51d454f71439c79)



**`GenAllSetter` 特性**

在`Java`方法中, 根据 `new` 关键词, 为`Java Bean` 生成所有`Setter`方法。

按`GenAllSetter`键两次, 会为`Setter`方法生成默认值。



**`GenDaoCode`**

一键生成 `dao` `xml` `service`



`CodeGlance`

在右侧生成代码地图



`**RestfulToolkit**`

`RequestMapping搜索神器`



**`Grep Console`**

高亮`log`不同级别日志，看日志的时候一目了然。



`MyBatis Log Plugin`

把 `Mybatis` 输出的`sql`日志还原成完整的`sql`语句，看起来更直观。



### GsonFormat 

>快速的讲一个 `json `转换为一个实体  安装完插件后 `alt + s` 放入正确的 `json `格式

![](http://193.112.98.8/atomImg/plugins/gson_use.gif)

### `VisualVm Launcher`

> 运行`java`程序的时候启动`visualvm`，方便查看`jvm`的情况 比如堆内存大小的分配
>
> 某个对象占用了多大的内存，`jvm`调优必备工具

