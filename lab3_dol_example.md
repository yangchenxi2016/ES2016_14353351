<center>
###嵌入式实验报告
</center>

**姓名**：杨晨西　　　　　　　　　　　　**学号**：14353351　　　　　　　**实验**：DOL实例分析　　　　**完成日期**：2016.10.20  


#####1.修改完的dol截图  
1. example1：0~19每个数的立方  
![example1](http://i.imgur.com/E8Ay5b3.png)      

dot截图：  
![example1_dol](http://i.imgur.com/ur453hA.png)　　

2. example2：0~19每个数的四次方，两个square  
![example2](http://i.imgur.com/SafaDBD.png)    

dot截图：只剩下两个square  
![example2_dpl](http://i.imgur.com/nVuNX3m.png)
#####2.如何修改的解释
######A修改example2，让三个square变成两个
具体修改：修改example2.xml文件的迭代次数，iteration表示迭代的次数，迭代一次是一个square，改成把迭代次数改成2，就表示迭代两次，即求数的四次方。  
######B修改example1，使得输出0~19的立方
修改square.c文件，将里面的　i=i*i　改成　i=i*i*i ,就可以求得三次方  

#####3. 实验感想　　
  　　本次试验遇到了一点问题，在运行第二个example的时候，它自动复制到bin文件里面的依旧是example1，并且这个时候我发想example1被锁住了，无法对它进行删除操作，于是在网上找了修改权限的方法，  在终端输入 <pre> sudo chmod -R 777 <文件路径+文件(夹)名> </pre>就可以修改权限了.后来是把example1在bin文件下面的复制部分给删了，然后再运行example2，反反复复试了很多次就可以了。到现在也不是很明白其中的道理。  

　　dol文件的dot图使得程序结构清晰简明。