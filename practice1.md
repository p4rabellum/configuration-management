# Задание 1

```
grep ^[^:]* /etc/passwd | cut -d: -f1 | sort
```
![Screenshot_112](https://github.com/user-attachments/assets/ac5d2b58-215e-4447-8ef6-04fae9c1d4e7)

# Задание 2

```
awk '{print $2, $1}' /etc/protocols | sort -rn | head -5
```

![Screenshot_113](https://github.com/user-attachments/assets/c5694857-915b-4211-94f3-7de9159c8c2a)

# Задание 3

```
#!/bin/bash
echo -n "+-"
for ((i=0; i<${#1}; i++))
do
        echo -n "-"
done
echo "-+"
echo "| $1 |"
echo -n "+-"
for ((i=0; i<${#1}; i++))
do
        echo -n "-"
done
echo "-+"
```
![Screenshot_114](https://github.com/user-attachments/assets/e38290ed-7c6b-4579-a2dd-11d431f2f271)
