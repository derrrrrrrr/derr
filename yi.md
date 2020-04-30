# 4.30小结

## git学习进度

git 都跟着教程看了一遍，但是垢面没怎么记住 

## 每天一题

题目：在一个二维数组中（每个一维数组的长度相同），每一行都按照从左到右递增的顺序排序，每一列都按照从上到下递增的顺序排序。请完成一个函数，输入这样的一个二维数组和一个整数，判断数组中是否含有该整数。           

我的思路：

```python
        if array is None:
            return False
        row = len(array)
        col = len(array[0])
        for i in range(row):
            for j in range(col):
                if target == array[i][j]:
                    return True
        return False
```

   

百度之后别人的思路：           

利用二维数组由上到下，由左到右递增的规律，选取右上角或者左下角的元素a和target进行比较，小于元素a，target必定在元素a所在行的左边col--；大于元素a，target必定在元素a所在列的下边row++；如果出了边界，则说明二维数组中不存在target元素。

```python
rows = len(array) - 1
cols = len(array[0]) - 1
i = rows
j = 0
while j<cols and i>=0:
    if target<array[i][j]:
        i -= 1
    elif target>array[i][j]:
        j += 1
    else:
        return True
 return False
        
```

