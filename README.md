> #### 作者主页：[舒克日记](https://blog.csdn.net/cativen)
>
>  简介：Java领域优质创作者、Java项目、学习资料、技术互助
>
> <b><font color=red>文中获取源码</font></b>

# 项目介绍

本系统分为管理员、任课老师、用户三个角色

实习管理系统针对管理员设置的功能有：添加并管理各种类型信息，管理用户账户信息，管理成绩管理、字典管理、分班管理、公告管理、任课老师管理、实训方向管理、实训方向报名管理、用户管理、学生考勤管理、学生考勤详情管理、作业管理、作业提交管理、管理员管理信息，管理公告信息等内容。

实习管理系统针对用户设置的功能有：查看并修改个人信息，查看成绩管理、字典管理、分班管理、公告管理、任课老师管理、实训方向管理、实训方向报名管理、用户管理、学生考勤管理、学生考勤详情管理、作业管理、作业提交管理、管理员管理信息，查看公告信息等内容。

# 环境要求

1.运行环境：最好是java jdk1.8,我们在这个平台上运行的。其他版本理论上也可以。

2.IDE环境：IDEA,Eclipse,Myeclipse都可以。推荐IDEA;

3.tomcat环境：Tomcat7.x,8.X,9.x版本均可

4.硬件环境：windows7/8/10 4G内存以上；或者Mac OS;

5.是否Maven项目：是；查看源码目录中是否包含pom.xml;若包含，则为maven项目，否则为非maven.项目

6.数据库：MySql5.7/8.0等版本均可；

# 技术栈

运行环境：jdk8 + tomcat9 + mysql5.7 + windows10

服务端技术：Java、Spring、SpringMVC、Mybatis，SSM

前端：jsp

# 使用说明

1.使用Navicat或者其它工具，在mysql中创建对应sq文件名称的数据库，并导入项目的sql文件；

2.使用IDEA/Eclipse/MyEclipse导入项目，修改配置，运行项目；

3.将项目中config-propertiesi配置文件中的数据库配置改为自己的配置，然后运行；

# 运行指导

idea导入源码空间站顶目教程说明(Vindows版)-ssm篇：

http://mtw.so/5MHvZq

源码地址：[http://www.codegym.top](http://www.codegym.top/)



# 运行截图

## 功能模块截图

### 项目截图

![图片2](https://i-blog.csdnimg.cn/img_convert/231768024d5b0e663c15fcb3246f9784.png)

![图片3](https://i-blog.csdnimg.cn/img_convert/74e19721d40fb4c58275e4e5aa6de773.png)

![图片4](https://i-blog.csdnimg.cn/img_convert/1f527a350a6e45018b9c73a2e699dd0b.png)

### 代码

```
 public CustomerDTO getCustomerDTO(JSONObject data) {
        CustomerDTO customerDTO = new CustomerDTO();
        customerDTO.setNickname(data.getString("nickName"));
        String gender = data.getString("gender");
        if (StringUtils.isEmpty(gender)) {
            customerDTO.setGender(GenderTypeEnum.UNKNOWN.type());
        } else {
            customerDTO.setGender(Integer.valueOf(gender));
        }
        customerDTO.setTelephone(data.getString("phone"));
        customerDTO.setBirthday(data.getLong("birthday"));
        customerDTO.setBirthAreaName(data.getString("birth"));
        customerDTO.setCity(data.getString("city"));
        customerDTO.setProvince(data.getString("province"));
        customerDTO.setDistrict(data.getString("district"));
        customerDTO.setWeight(data.getInteger("weight"));
        customerDTO.setHeight(data.getInteger("height"));
        customerDTO.setAddress(data.getString("address"));
        customerDTO.setDescription(data.getString("desc"));
        customerDTO.setCreatorId(BUSINESS_TYPE_CLIFE);
        customerDTO.setModifierId(BUSINESS_TYPE_CLIFE);
        customerDTO.setCreateTime(System.currentTimeMillis());
        customerDTO.setModifyTime(System.currentTimeMillis());
        customerDTO.setExternalCustomerId(data.getString("userId"));
        customerDTO.setExternalBusinessType(BUSINESS_TYPE_CLIFE);

        return customerDTO;
    }
```
