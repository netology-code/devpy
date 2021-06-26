# K лекции 1.2 «Условные конструкции. Операции сравнения»

###  Task 1 - hackerrank - https://www.hackerrank.com/eshmargunov


### Task 2

```
age = int(input('Введите возраст призывника: '))
height = int(input('Введите рост призывника в см: '))
children = int(input('Введите количество детей у призывника: '))
study = input('Учится ли сейчас призывник (да/нет)? ')
if 18 < age < 27:
    if height < 170:
        print('Танкисты')
    elif children >= 2:
        print('Отсрочка. Нужног ходить каждый год и предоставлять документы о том, что есть более 1 ребенка')
    elif study == 'да':
        print('Осрочка на время обучения')
    else:
        print('Любые другие войска')
else:
    print('Не призывной возраст')
```

### Task 3
*Эта задача имеет большое количество решений. Здесь представлено самое простое*

```
month = input('введите месяц:')

date = int(input('введите число:'))

print('вывод:')

if (month == 'март' and date >= 21) or (month == 'апрель' and date <= 19):
    print('овен')
elif (month == 'апрель' and date >= 20) or (month == 'май' and date <= 20):
    print('телец')
elif (month == 'май' and date >= 21) or (month == 'июнь' and date <= 21):
    print('близнецы')
elif (month == 'июнь ' and date >= 22) or (month == 'июль' and date <= 22):
    print('рак')
elif (month == 'июль' and date >= 23) or (month == 'август' and date <= 22):
    print('лев')
elif (month == 'август' and date >= 23) or (month == 'сентябрь' and date <= 22):
    print('дева')
elif (month == 'сентябрь' and date >= 23) or (month == 'октябрь' and date <= 23):
    print('весы')
elif (month == 'октябрь' and date >= 24) or (month == 'ноябрь' and date <= 22):
    print('скорпион')
elif (month == 'ноябрь' and date >= 23) or (month == 'декабрь' and date <= 21):
    print('стрелец')
elif (month == 'декабрь' and date >= 22) or (month == 'январь' and date <= 20):
    print('козерог')
elif (month == 'январь' and date >= 21) or (month == 'февраль' and date <= 18):
    print('водолей')
elif (month == 'февраль' and date >= 19) or (month == 'март' and date <= 20):
    print('рыбы')
else:
    print('Знак зодиака не найден')
    
```
