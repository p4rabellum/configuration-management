# Задание 1

```
local groups = [
  "ИКБО-1-24",
  "ИКБО-2-24",
  "ИКБО-3-24",
  "ИКБО-4-24",
  "ИКБО-5-24",
  "ИКБО-6-24",
  "ИКБО-7-24",
  "ИКБО-8-24",
  "ИКБО-9-24",
  "ИКБО-10-24",
  "ИКБО-11-24",
  "ИКБО-12-24",
  "ИКБО-13-24",
  "ИКБО-14-24",
  "ИКБО-15-24",
  "ИКБО-16-24",
  "ИКБО-17-24",
  "ИКБО-18-24",
  "ИКБО-19-24",
  "ИКБО-20-24",
  "ИКБО-21-24",
  "ИКБО-22-24",
  "ИКБО-23-24",
  "ИКБО-24-24"
];

local student(name, age, group, subject) = {
  name: name,
  age: age,
  group: group,
  subject: subject,
};

local students = [
  student("Иванов И.И.", 19, "ИКБО-4-24", "Конфигурационное управление"),
  student("Петров П.П.", 18, "ИКБО-5-24", "Конфигурационное управление"),
  student("Сидоров С.С.", 18, "ИКБО-5-24", "Конфигурационное управление"),
  student("Лазаренко С.А.", 19, "ИКБО-6-24", "Конфигурационное управление")
];

{
  groups: groups,
  students: students,
}
```

# Задание 3

```
import random


def parse_bnf(text):
    '''
    Преобразовать текстовую запись БНФ в словарь.
    '''
    grammar = {}
    rules = [line.split('=') for line in text.strip().split('\n')]
    for name, body in rules:
        grammar[name.strip()] = [alt.split() for alt in body.split('|')]
    return grammar


def generate_phrase(grammar, start):
    '''
    Сгенерировать случайную фразу.
    '''
    if start in grammar:
        seq = random.choice(grammar[start])
        return ''.join([generate_phrase(grammar, name) for name in seq])
    return str(start)


BNF = '''
E = "0" E | "1" E | "1" | "0"
'''

for i in range(10):
    phrase = generate_phrase(parse_bnf(BNF), 'E')
    if phrase:
        print(phrase.replace('"', ''))
```

# Задание 4

```
import random


def parse_bnf(text):
    '''
    Преобразовать текстовую запись БНФ в словарь.
    '''
    grammar = {}
    rules = [line.split('=') for line in text.strip().split('\n')]
    for name, body in rules:
        grammar[name.strip()] = [alt.split() for alt in body.split('|')]
    return grammar


def generate_phrase(grammar, start):
    '''
    Сгенерировать случайную фразу.
    '''
    if start in grammar:
        seq = random.choice(grammar[start])
        return ''.join([generate_phrase(grammar, name) for name in seq])
    return str(start)


BNF = '''
E = E | "(" E ")" | "{" E "}" | "()" | "{}" | E "()" | E "{}"
'''

for i in range(10):
    phrase = generate_phrase(parse_bnf(BNF), 'E')
    if phrase:
        print(phrase.replace('"', ''))
```

# Задание 5
```
import random


def parse_bnf(text):
    '''
    Преобразовать текстовую запись БНФ в словарь.
    '''
    grammar = {}
    rules = [line.split('=') for line in text.strip().split('\n')]
    for name, body in rules:
        grammar[name.strip()] = [alt.split() for alt in body.split('|')]
    return grammar


def generate_phrase(grammar, start):
    '''
    Сгенерировать случайную фразу.
    '''
    if start in grammar:
        seq = random.choice(grammar[start])
        return ''.join([generate_phrase(grammar, name) for name in seq])
    return str(start)


BNF = '''
E = "~" E | E "&" E | E "|" E | "(" E ")" | "x" | "y" | "(x)" | "(y)"
'''

for i in range(10):
    phrase = generate_phrase(parse_bnf(BNF), 'E')
    if phrase:
        print(phrase.replace('"', ''))
```
