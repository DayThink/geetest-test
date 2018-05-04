**之前接到的一个笔试题，要求24小时内完成，要求如下：**

选用react、angular5、vue 任一框架搭建一个单页面web应用，完成登录及注册两个页面  
条件：  
1. 使用webpack  
2. 使用less 或 sass  
3. 选用任意一ui框架， 将页面进行移动端适配  
4. 使用json像后台提交表单，内容及字段自选    

**于是用vue框架，完成了此项目：**   
1. 包含登录与注册两个页面  
2. 将带有删除内容按钮的输入框、消息提示框提取为公共组件  
3. 用axios插件，整理为公用接口插件  
4. 自己仿照iview表单验证扩展的表单验证公共方法，弥补添加可部分验证的场景  
5. PC、移动端的适配，简单的使用media媒体控制

**效果如下：**  

![login](https://github.com/LanlanXu/geetest-test/blob/master/readmepic/login.png "login")  
![register](https://github.com/LanlanXu/geetest-test/blob/master/readmepic/register.png "register")