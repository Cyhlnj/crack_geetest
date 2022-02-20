# geetest极验第三代空间推理验证码破解
在网上看到很多破解了极验的滑动验证码和文字点选验证码，但是没怎么见破解空间推理的，就训练了个yolo模型，试试破解这个每次都要要思考好久的验证码。
同时通过反爬极验的接口获取的加密方法，使用requests模拟请求，比网上已有的selenium自动化浏览器点击滑动破解验证码的方法相比，速度极快，需要的依赖也少。   
     
![image](https://github.com/cycyup/crack_geetest/blob/main/images/test1.jpg)     
       
训练的模型的精度为0.96 预测速度在GTX1070ti上能达到30ms，就算在最低配1核cpu 2G内存最低配的服务器上也能达到200ms，足够一定量并发预测   

## **声明**
**本项目仅供学习交流使用，严禁用于商业和违法行为，否则产生的一切后果与本人无关！！！！**

### [测试接口](https://github.com/cycyup/crack_geetest/blob/main/%E6%B5%8B%E8%AF%95%E6%8E%A5%E5%8F%A3.md)（仅供学习使用）

## **破解思路**     
1、对从存在验证码的网页抓包获取验证码的gt和challenge   
2、使用gt和challenge的获取验证码类型，获取图片、文字信息和一些生成。   
3、使用yolo对图片物体进行分类定位，得到文字描述的物体坐标   
4、点击坐标后提交，将坐标等信息加密post给服务器，返回validate的值表示验证成功。     
5、有了validate就可以和gt，challenge一起交给需要登录的网站做验证了。    

## 细教程（图文并茂）已发表在cdns
[geetest极验空间推理验证码破解与研究](https://mp.csdn.net/mp_blog/creation/editor/122953184)

## 觉得不错帮忙Star一下，谢谢！
