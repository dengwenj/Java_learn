## 单元测试
* 就是针对最小的功能单元（方法），编写测试代码对其进行正确性测试

## Junit 单元测试框架
* 可以用来对方法进行测试，它是第三方公司开源出来的（很多开发工具已经集成了 Junit 框架，比如 IDEA）

## 优点
* 可以灵活的编写测试代码，可以针对某个方法执行测试，也支持一键完成对全部方法的自动化测试，且各自独立
* 不需要程序员去分析测试的结果，会自定生成测试报告出来

## 具体步骤
* 将 Junit 框架的 jar 包导入到项目中（IDEA 集成了 Junit 框架，不需要我们自己手动导入）
* 为需要测试的业务类，定义对应的测试类，并为每个业务方法，编写对应的测试方法（必须：公共、无参、无返回值）
* 测试方法上必须声明 @Test 注解，然后在测试方法中编写代码调用被测试的业务方法进行测试
* 开始测试

## Junit 单元测试框架的常用注解（4版本）
* @Test：测试类中的方法必须用它修饰才能成为测试方法，才能启动执行
* @Before：用来修饰一个实例方法，该方法会在每一个测试方法执行之前执行一次
* @After：用来修饰一个实例方法，该方法会在每一个测试方法执行之后执行一次
* @BeforeClass：用来修饰一个静态方 法，该方法会在所有测试方法之前只执行一次
* @AfterClass：用来修饰一个静态方法，该方法会在所有测试方法之后只执行一次
* 在测试方法执行前执行的方法常用于：初始化资源
* 在测试方法执行后执行的方法常用于：释放资源