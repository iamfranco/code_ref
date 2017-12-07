# MATLAB Reference

#### Import data with different lengths for each row
If `dataset.txt` contains
```
1
2 2
3 3 3
```
then
```matlab
>> A = dlmread('dataset.txt')

A =

     1     0     0
     2     2     0
     3     3     3
```

#### Export plot to eps
```matlab
x = 1:10;
y = 1:10;
plot(x,y);
set(gcf, 'PaperPosition', [0 0 20 10]);
print('-depsc', 'figure.eps');
```
