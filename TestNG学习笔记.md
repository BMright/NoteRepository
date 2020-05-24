#### TestNG

+ 一个测试框架，设计灵感来自于junit，但优于junit，他提供了很强大的注解，便于我们对case的各种操作。

+ TestNG提供了强大的注解，方便测试人员的使用

+ TestNG支持数据驱动测试（DDT）

+ 支持并行测试

+ 可以灵活配置测试，具有强大的执行模式

+ 可以生成多种测试报告

#### TestNG部分注解:

1. @BeforeTest:类中任何测试方法执行前都会执行，且每个类只执行一次

2. @BeforeMethod：任何测试方法执行前都会执行，每个类中可以执行多次

3. @Test：标记一个类或方法作为测试的一部分

4. @AfterMethod：与@BeforeMethod相对应

5. @AfterTest：与@BeforeTest相对应

#### TestNG常用校验方式：

+ 相等：Assert.assertEquals();

- 不等：Assert.assertNotEquals();

- 不为空; Assert.assertNotNull();

- 为空：Assert.assertNull();

#### DataProvider数据驱动用法

###### 定义数据`返回数据一定要为Object[][]`：

```
@DataProvider(name = "data")
public Object[][] testData(){
	return new Object[][]{
		{
			"test123456","123456"
		},{
			"test111111","123456"
		}
	}
}
```

###### 使用数据

```
@Test(dataProvider = "data")
public void testDp(String username,String password){

}
```



#### TestNG并发方式`通过xml文件`：

	1. thread-count="2": 并发数为2
 	2. parallel="methods": 以方法方式并发 classes：以类的方式并发
 	3. 可以通过exclude选择不跑类中的哪个case

![1589886029518](C:\Users\hp\AppData\Roaming\Typora\typora-user-images\1589886029518.png)

#### Page Object设计模式的优点：

1. 减少代码的重复

2. 提高测试用例的可读性

3. 提高测试用例的可维护性，特别是针对UI频繁变化的项目

​        核心思想是通过对界面元素的封装减少冗余代码，同时在后期维护中，若元素定位发生变化， 只需要调整页面元素封装的代码，提高测试用例的可维护性、可读性。

#### Po模式分层

1. Page层:`封装页面元素`
2. 逻辑层：`封装一个个小的功能，填写数据，点击事件什么的`
3. 业务层：`真正的case层，用来写Case测试`



#### Cucumber学习

​	 Cucumber是一个工具，用于运行以BDD格式创建的自动化验收测试。该工具最突出的特性之一是能够将纯文本功能描述(使用Gherkin语言编写)作为自动化测试执行。 

​	 行为驱动开发(BDD) ：

  1. 使用无所不在的语言编写BDD测试，这是一种围绕领域模型构建的语言，被开发人员、测试人员、BA人员和客户组成的所有团队成员广泛使用。

  2. 连接软件团队的技术人员和非技术人员

  3. 允许与开发人员的代码直接交互，但是BDD测试是用一种语言编写的，业务利益相关者也可以使用这种语言编写测试。

  4.  验收测试可以自动执行，同时也可以由业务利益相关者手动执行

     使用时：

     1. feature层
     2. step层
     3. 代码层



