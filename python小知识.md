# python

```python
a,b=input().split()
```

用空格分隔输入，分别赋值给a，b

##### if __name__ == '__main__':的作用

一个python文件通常有两种使用方法,即：

- 作为脚本直接执行
- import 到其他的 python 脚本中被调用（模块重用）执行

在 if __name__ == 'main': 下的代码只会在作为当前执行模块的时候执行，在调用的时候不会执行

```python
if __name__ =='__main--':
```

