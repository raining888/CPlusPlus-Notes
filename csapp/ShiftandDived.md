### 移位和除法等价的误区

对于非负数来讲，例如，`110 / 8 = 13` `110 >> 3 = 13`可见是相等的

对于负数来讲，`-110 / 8 = -13` `-110 >> 3 = -14`明显不相等，因为在c语言中是round to zero，`-110 / 8 = -13.75 = -13` 

这个时候用移位实现除法，在移位前加上`8 - 1 = 7`

```
int addNum = 7 & (multFive >> 31);
int divEight = (multFive + addNum) >> 3;
```