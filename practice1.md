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

# Задание 4

```
#!/bin/bash
 
if [ -z "$1" ]; then
        echo "Usage: $0 filename"
        exit 1
fi
filename="$1"
grep -oE '\b[a-zA-Z_][a-zA-Z0-9_]*\b' "$filename" | sort -u
```

![Screenshot_115](https://github.com/user-attachments/assets/d8ce887f-e5e4-4afa-aa78-f8ba5647ab99)


# Задание 5

```
#!/bin/bash
sudo cp $1 /usr/local/bin/
sudo chmod 755 /usr/local/bin/$1
```

# Задание 6

```
#!/bin/bash
line=$(head -n 1 $1)
extension="${1##*.}"
if [[ "$extension" == "js" ]] || [[ "$extension" == "cpp" ]]; then
        comm="${line:0:2}"
        if [[ "$comm" == "//" ]]; then
                echo "Comment is present"
        else
                echo "Comment is absent"
        fi
else
        comm="${line:0:1}"
        if [[ "$comm" == "#" ]]; then
                echo "Comment is present"
        else
                echo "Comment is absent"
        fi
fi
```

![Screenshot_117](https://github.com/user-attachments/assets/075cdbfc-7aeb-474c-b588-1bf1783fddca)

# Задание 8

```
#!/bin/bash
find ./ -maxdepth 1 -name "*.$1" -exec tar -rf compressed.tar {} \;
```

![Screenshot_118](https://github.com/user-attachments/assets/7820f129-57fe-4683-8fc0-4a610338e608)
