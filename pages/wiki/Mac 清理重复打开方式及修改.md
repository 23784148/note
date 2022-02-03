#### 清理重复、多余的打开方式：

>  /System/Library/Frameworks/CoreServices.framework/Versions/A/Frameworks/LaunchServices.framework/Versions/A/Support/lsregister -kill -r -domain local -domain system-domain user

#### 修改文件类型默认启动程序：

* 手动：
  
  ``` 
  需要修改类型的文件 -> 右键 -> 选择 "显示简介/GetInfo" -> 展开 弹出的窗口的"打开方式/OpenWith" -> 选择你希望的打开程序 -> 点击 "全部更改/ChangeAll" 即可。
  ```
  
  ​
  
* `RCDefaultApp`
  
  * 地址 <http://www.waerfa.com/rcdefaultapp>

#### 参考：

- <http://www.apprcn.com/clean-up-mmultiple-open-with-entries-in-os-x.html>
- <http://macbai.diandian.com/post/2012-12-05/40047107891>