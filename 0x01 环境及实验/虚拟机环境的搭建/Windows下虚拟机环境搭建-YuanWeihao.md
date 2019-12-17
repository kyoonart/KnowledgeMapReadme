### 详细过程

安装VirtualBox过程正常没有出错

在部署虚拟机时出现错误，现在还未解决

Step1: 选中目标虚拟机
![Step1](https://github.com/whip1ash/KnowledgeMapReadme/blob/master/0x01%20%E7%8E%AF%E5%A2%83%E5%8F%8A%E5%AE%9E%E9%AA%8C/%E8%99%9A%E6%8B%9F%E6%9C%BA%E7%8E%AF%E5%A2%83%E7%9A%84%E6%90%AD%E5%BB%BA/YWH_log_img/Problem1.PNG)

Step2: 改变RAM
![Step2](https://github.com/whip1ash/KnowledgeMapReadme/blob/master/0x01%20%E7%8E%AF%E5%A2%83%E5%8F%8A%E5%AE%9E%E9%AA%8C/%E8%99%9A%E6%8B%9F%E6%9C%BA%E7%8E%AF%E5%A2%83%E7%9A%84%E6%90%AD%E5%BB%BA/YWH_log_img/Problem2.PNG)

Step3: 发生错误
![Step3](https://github.com/whip1ash/KnowledgeMapReadme/blob/master/0x01%20%E7%8E%AF%E5%A2%83%E5%8F%8A%E5%AE%9E%E9%AA%8C/%E8%99%9A%E6%8B%9F%E6%9C%BA%E7%8E%AF%E5%A2%83%E7%9A%84%E6%90%AD%E5%BB%BA/YWH_log_img/Problem3.PNG)


### Problem - VirtualBox导入虚拟机过程中出现“”Failed  to import appliance E:\KG_ex.ova.Result Code: E_INVALIDARG (0x80070057)

![Problem1](https://github.com/whip1ash/KnowledgeMapReadme/blob/master/0x01%20%E7%8E%AF%E5%A2%83%E5%8F%8A%E5%AE%9E%E9%AA%8C/%E8%99%9A%E6%8B%9F%E6%9C%BA%E7%8E%AF%E5%A2%83%E7%9A%84%E6%90%AD%E5%BB%BA/YWH_log_img/Problem3.PNG)

### Unsolved - E_INVALIDARG (0x80070057)
1.已尝试方法

+已尝试用notepad++打开虚拟机文件改变其uuid，但因文件过大打开失败。

+通过命令修改uuid，也无法成功
```DOS
vboxmanage internalcommands sethduuid "E:\KG_ex.ova" uuid
```

