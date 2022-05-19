# 1. HJ107 求解立方根
描述
计算一个浮点数的立方根，不使用库函数。
保留一位小数。

数据范围：∣val∣≤20 

输入描述：
待求解参数，为double类型（一个实数）

输出描述：
输出参数的立方根。保留一位小数。
```python
#使用泰勒公式
while True:
  try:
    a=float(input().strip())
    e=0.001
    t=a
    while (abs(t*t*t-a)>e):
      t=t-(t*t*t-a)*1.0/(3*t*t)
    print('%.1f %t)
  except:
    break
```

```python
#使用二分法
while True:
    try:
        a=float(input().strip())
        e=0.0001
        low=min(-1.0,a)
        high=max(1.0,a)
        ans=(low+high)/2
        while abs(ans**3-a)>=e:
            if ans**3<a:
                low=ans 
            else:
                high=ans 
            ans=(low+high)/2
        print('%.1f' %ans)
    except:
        break 
```
