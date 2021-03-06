# 代码混淆

下面详细介绍安卓代码混淆的技术方案。

最常见的做法是，用`ProGuard`去实现代码混淆。

## ProGuard

### ProGuard的作用

* 压缩=Shrinking
  * 移除未被使用的类、属性、方法等，并且会在优化动作执行之后再次执行（因为优化后可能会再次暴露一些未被使用的类和成员
* 优化=Optimization
  * 优化字节码，并删除未使用的结构
* 混淆=Obfuscation
  * 将类名、属性名、方法名混淆为难以读懂的字母，比如a,b,c等，增大反编译难度

### ProGuard的输出文件说明

* `dump.txt`：说明 APK 中所有类文件的内部结构
* `mapping.txt`：提供原始与混淆过的类、方法和字段名称之间的转换和对应关系
* `seeds.txt`：列出未进行混淆的类和成员
* `usage.txt`：列出从 APK 移除的代码
