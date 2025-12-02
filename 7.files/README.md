# K лекции «Открытие и чтение файла, запись в файл»

## Task 1
```
from pprint import pprint


def read_recipes():
    recipe = {}
    with open('recipes.txt', 'r', encoding='UTF-8') as f:
        line = f.readline().strip()
        while line != '':
            dish = line
            count_ingredients = int(f.readline().strip())
            ingredients = []
            for _ in range(count_ingredients):
                ingredient_line = f.readline().strip()
                ingredient_info = ingredient_line.split(' | ')
                name = ingredient_info[0]
                quantity = int(ingredient_info[1])
                measure = ingredient_info[2]
                ingredient_info = {'ingredient_name': name, 'quantity': quantity, 'measure': measure}
                ingredients.append(ingredient_info)
            recipe[dish] = ingredients
            f.readline()
            line = f.readline().strip()
    return recipe


pprint(read_recipes())

```

## Task 1
```python
dishes = list(input('Введите через запятую названия блюд, которые хотите приготовить: ').split(', '))
person_count = int(input('Укажите количество людей: '))


def get_shop_list_by_dishes(dishes, person_count):
    cook_book = read_recipes()
    buy_products = {}

    for dish in dishes:
        ingredients = cook_book[dish]
        for ingredient in ingredients:
            quantity = ingredient['quantity'] * person_count
            name = ingredient['ingredient_name']
            if name in buy_products:
                buy_products[name]['quantity'] += quantity
            else:
                buy_products[name] = {'measure': ingredient['measure'], 'quantity': quantity}

    print(buy_products)


get_shop_list_by_dishes(dishes, person_count)

```

## Task 2
```python
import os


def sort_files():
    files = os.listdir('sorted')
    result = []
    for file_ in files:
        with open(f'sorted/{file_}', 'r', encoding='utf8') as f:
            text = f.read()
            f.seek(0)
            result.append({'name': file_, 'count_lines': len(f.readlines()), 'text': text})

    sorted_files = sorted(result, key=lambda f: f['count_lines'])
    with open('result.txt', 'w', encoding='utf8') as f:
        for file_ in sorted_files:
            f.write(file_['name']+'\n')
            f.write(str(file_['count_lines'])+'\n')
            f.write(file_['text']+'\n')


sort_files()
```
