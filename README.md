# AndroidFamily

### NumberPicker篇
- Q:如何设置只能滑动改变值，不能通过点击和键盘修改。  
  A:XML修改方法为
  >android:descendantFocusability="blocksDescendants" 
  
  代码中修改方法为
  >numberPicker.setDescendantFocusability(NumberPicker.FOCUS_BLOCK_DESCENDANTS);


### 异常篇
**Q**:如何解决Unsupported major.minor version 52.0问题？  

**A**:修改gradle命令的执行环境。一般命令行打包会出现这个问题。  
  
修改gradle.properties，  
  
添加org.gradle.java.home=/Applications/Android Studio.app/Contents/jre/jdk/Contents/Home  
  
参考  
  
[如何解决Unsupported major.minor version 52.0问题？](http://www.jianshu.com/p/5eebd3c609d6)

### 调试篇
**Q**:android开发时如何无线连接手机？

**A**:  
虽然是无线连接，但是第一次还是需要USB滴～  

1. 将手机通过USB与电脑连接。

2. 在终端输入命令：adb tcpip 5555,会看到提示restarting in TCP mode port: 5555

3. 在终端输入命令：adb shell netcfg,在显示的信息中查找wlan0所在的行，会看到一串IP值xx.xx.xx.xx。

4. 在终端输入命令：adb connect xx.xx.xx.xx:5555