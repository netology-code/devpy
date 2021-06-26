# K лекции 1.3 «Введение в типы данных и циклы»

### Task 1
```
boys = ['Peter', 'Alex', 'John', 'Arthur', 'Richard']
girls = ['Kate', 'Liza', 'Kira', 'Emma', 'Trisha']
if len(boys) != len(girls):
    print('Кому-то не достанется пары!')
pairs = zip(sorted(boys), sorted(girls))
print('Идеальные пары: ')
for boy, girl in pairs:
    print(f'{boy} и {girl}')
 
 ```

### Task 2


```cook_book = [
    ['салат',
     [
         ['картофель', 100, 'гр.'],
         ['морковь', 50, 'гр.'],
         ['огурцы', 50, 'гр.'],
         ['горошек', 30, 'гр.'],
         ['майонез', 70, 'мл.'],
     ]
     ],
    ['пицца',
     [
         ['сыр', 50, 'гр.'],
         ['томаты', 50, 'гр.'],
         ['тесто', 100, 'гр.'],
         ['бекон', 30, 'гр.'],
         ['колбаса', 30, 'гр.'],
         ['грибы', 20, 'гр.'],
     ],
     ],
    ['фруктовый десерт',
     [
         ['хурма', 60, 'гр.'],
         ['киви', 60, 'гр.'],
         ['творог', 60, 'гр.'],
         ['сахар', 10, 'гр.'],
         ['мед', 50, 'мл.'],
     ]
     ]
]
person = int(input())

new_cook_book = []
for dish, ingredients in cook_book:
    print(dish)
    for ingredient in ingredients:
        ingredient_name = ingredient[0]
        ingredient_count = ingredient[1] * person
        ingredient_measure = ingredient[2]
        print(f'{ingredient_name}, {ingredient_count}{ingredient_measure}')
    print()
```
