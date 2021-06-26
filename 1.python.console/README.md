# К лекции 1.1 «Python. Знакомство с консолью»
### Task1 - link for hackerrank - https://www.hackerrank.com/eshmargunov

### Task2

```
side_square = int(input('Введите размер стороны квадрата:'))
perimeter_square = 4 * side_square
area_square = side_square ** 2
print('Периметр', perimeter_square)
print('Площадь', area_square)

length_rectangle = int(input('Введите длину прямоугольника:'))
width_rectangle = int(input('Введите ширину прямоугольника:'))

perimeter_rectangle = 2 * (length_rectangle + width_rectangle)
area_rectangle = length_rectangle * width_rectangle
print('Периметр', perimeter_rectangle)
print('Площадь', area_rectangle)
```

### Task3

```
salary = int(input('Введите заработную плату в месяц: '))
percent_mortgage = int(input('Введите, какой процент(%) уходит на ипотеку:'))
percent_life = int(input('Введите, какой процент(%) уходит на жизнь:'))
year_mortgage = salary * percent_mortgage / 100 * 12
year_life = salary * percent_life / 100 * 12
year_capital = salary * 12 - year_mortgage - year_life
print('На ипотеку было потрачено:', year_mortgage)
print('Было накоплено:', year_capital)
```
