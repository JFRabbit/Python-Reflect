# Python-Reflect

reflect.reflectUtil: class Reflect
```
class Reflect(builtins.object)
 |  Python 反射
 |  
 |  Methods defined here:
 |  
 |  __init__(self, module_name, from_name, method_name, args=(), class_name='')
 |      :param module_name:     模块名称 例: A.B
 |      :param from_name:       from name 例: from A.B
 |      :param method_name:     方法名
 |      :param args:            方法入参 例: (1, 2)
 |      :param class_name:      类名
 |      :return:                反射方法返回值
 |  
 |  run(self)
 |      run reflect
 |  
 |  ----------------------------------------------------------------------
```

### How to run?

```
from reflect.reflectUtil import Reflect

if __name__ == '__main__':
    # print(help(Reflect))

    module_name = "reflect.reflectTestData"
    from_list = "from reflect.reflectTestData import MethodDemo"
    args = (1, 2)
    class_name = "MethodDemo"

    print("reflect module method(include args)")
    reflect = Reflect(module_name, from_list, "method1", args)
    print(reflect.run())

    print("\nreflect class method(include args)")
    # reflect class method(include args)
    reflect = Reflect(module_name, from_list, "class_method1", args, class_name)
    print(reflect.run())

    print("\nreflect module method(no args)")
    reflect = Reflect(module_name, from_list, "method2")
    print(reflect.run())

    print("\nreflect class method(no args)")
    reflect = Reflect(module_name, from_list, "class_method2", class_name=class_name)
    print(reflect.run())

```
Result:
```
reflect module method(include args)
do method1
1 2
3

reflect class method(include args)
do class method1
1 2
3

reflect module method(no args)
do method2
method2

reflect class method(no args)
do class_method2
class_method2
```