vmware

[如何设置才能提升VMware虚拟机的显卡性能](http://blog.sina.com.cn/s/blog_1731e05e00102yc59.html)

勾选  处理器/虚拟化inter...  
勾选  处理器/虚拟化cpu....


显示器   /图像内存----2GB



[虚拟机中开启dnf：](https://www.seoxiehui.cn/article-18892-1.html)


记事本打开 虚拟机目录下的  xxxx.vmx

添加如下的一段代码

isolation.tools.setVersion.disable = "TRUE"

isolation.tools.getVersion.disable = "TRUE"
