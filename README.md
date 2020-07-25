# daka_03
异常处理
这次主要学习了python的异常处理

异常就是运行期检测到的错误。计算机语言针对可能出现的错误定义了异常类型，某种错误引发对应的异常时，异
常处理程序将被启动，从而恢复程序的正常运行。
如：

1. Python 标准异常总结

BaseException：所有异常的 基类
Exception：常规异常的 基类
StandardError：所有的内建标准异常的基类
ArithmeticError：所有数值计算异常的基类
FloatingPointError：浮点计算异常
OverflowError：数值运算超出最大限制
ZeroDivisionError：除数为零
AssertionError：断言语句（assert）失败
AttributeError：尝试访问未知的对象属性
EOFError：没有内建输入，到达EOF标记
EnvironmentError：操作系统异常的基类
IOError：输入/输出操作失败
OSError：操作系统产生的异常（例如打开一个不存在的文件）
WindowsError：系统调用失败
ImportError：导入模块失败的时候
KeyboardInterrupt：用户中断执行
LookupError：无效数据查询的基类
IndexError：索引超出序列的范围
KeyError：字典中查找一个不存在的关键字
MemoryError：内存溢出（可通过删除对象释放内存）
NameError：尝试访问一个不存在的变量
UnboundLocalError：访问未初始化的本地变量
ReferenceError：弱引用试图访问已经垃圾回收了的对象
RuntimeError：一般的运行时异常
NotImplementedError：尚未实现的方法
SyntaxError：语法错误导致的异常
IndentationError：缩进错误导致的异常
TabError：Tab和空格混用
SystemError：一般的解释器系统异常
TypeError：不同类型间的无效操作
ValueError：传入无效的参数
UnicodeError：Unicode相关的异常
UnicodeDecodeError：Unicode解码时的异常
UnicodeEncodeError：Unicode编码错误导致的异常
UnicodeTranslateError：Unicode转换错误导致的异常



2. Python标准警告总结

Warning：警告的基类
DeprecationWarning：关于被弃用的特征的警告
FutureWarning：关于构造将来语义会有改变的警告
UserWarning：用户代码生成的警告
PendingDeprecationWarning：关于特性将会被废弃的警告
RuntimeWarning：可疑的运行时行为(runtime behavior)的警告
SyntaxWarning：可疑语法的警告
ImportWarning：用于在导入模块过程中触发的警告
UnicodeWarning：与Unicode相关的警告
BytesWarning：与字节或字节码相关的警告
ResourceWarning：与资源使用相关的警告

3. try - except 语句

    try:
    检测范围
    except Exception[as reason]:    
    出现异常后的处理代码

    try - except - else 
    dict1 = {'a': 1, 'b': 2, 'v': 22}
    try:
        x = dict1['y']
    except KeyError:
        print('键错误')
    except LookupError:
        print('查询错误')
    else:
        print(x)

4. try - except - finally 语句

    try:
        检测范围
    except Exception[as reason]:
        出现异常后的处理代码
    finally:
        无论如何都会被执行的代码

5. try - except - else 语句

    try:
        检测范围
    except:
        出现异常后的处理代码
    else:
        如果没有异常执行这块代码

6. raise语句

    Python 使用raise语句抛出一个指定的异常
        try:
        raise NameError('HiThere')
    except NameError:
        print('An exception flew by!')
    
    # An exception flew by!

练习题：1、猜数字游戏

import random
rrr=(random.randint(0,100))
i=1
print("猜测一个0到100之间的整数\n第1次猜，请输入一个整型数字：")
while 1: 
    try:
        x= int(input())
    except ValueError:
        print('输入无效')
        i+=1
        print("这是你第%d次猜"%i)
        continue
    if x == rrr:
        print("恭喜你猜到了这个数是",rrr)
        break
    elif x < rrr:
        print("太小")
    else:
        print("太大")
    i+=1
    print("这是你第%d次猜"%i)
