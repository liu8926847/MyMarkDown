只用一个 SQL  更新语句，将 sex 字段反转。

```
| id | name | sex | salary |
|----|------|-----|--------|
| 1  | A    | f   | 2500   |
| 2  | B    | m   | 1500   |
| 3  | C    | f   | 5500   |
| 4  | D    | m   | 500    |
```

技巧：两个相等的数异或结果为0,0与一个数异或的结果为他本身。

```
'f' ^ ('m' ^ 'f') = 'm' ^ ('f' ^ 'f') = 'm'
'm' ^ ('m' ^ 'f') = 'f' ^ ('m' ^ 'm') = 'f'
```