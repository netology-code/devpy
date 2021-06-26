# K лекции 2.1 «Функции — использование встроенных и создание собственных»

```
documents = [
    {"type": "passport", "number": "2207 876234", "name": "Василий Гупкин"},
    {"type": "invoice", "number": "11-2", "name": "Геннадий Покемонов"},
    {"type": "insurance", "number": "10006", "name": "Аристарх Павлов"}
]

directories = {
    '1': ['2207 876234', '11-2'],
    '2': ['10006'],
    '3': []
}


def get_name_by_number():
    number = input('Введите номер документа: ')
    for doc in documents:
        if doc['number'] == number:
            print('{0}'.format(doc['name']))
            break
    else:
        print('Отсутствуют документы с таким номером')


def show_documents():
    for doc in documents:
        print(doc['type'], doc['number'], doc['name'])
    for key, values in directories.items():
        print(key, '->', values)


def get_directory_by_number():
    number = input('Введите номер документа: ')
    for directory, list_docs in directories.items():
        if number in list_docs:
            print('Документ с номером {0} находится на полке {1}'.format(number, directory))
            break
    else:
        print('Отсутствуют документы с таким номером')


def add_document():
    number = input('Введите номер документа:')
    name = input('Введите имя и фамилию:')
    doc_type = input('Введите тип документа:')
    directory_number = input('Введите номер полки:')
    if number and name and doc_type and directory_number:
        documents.append({"type": doc_type, "number": number, "name": name})
        if directory_number in directories:
            directories[directory_number].append(number)
        else:
            directories[directory_number] = [number]
    else:
        print('ВНИМАНИЕ! Введены не все данные')


def remove_document():
    person_number = input('Введите номер документа: ')
    bookshelf = ''
    for elem in documents:
        if elem['number'] == person_number:
            documents.remove(elem)
    for number_shelf, number_documents in directories.items():
        if person_number in number_documents:
            number_documents.remove(person_number)
            bookshelf = number_shelf
            break
    print(f'Удален документ с номером: {person_number} из базы данных и убран с полки №{bookshelf}')


def main():
    while True:
        command = input('Введите команду: ')
        if command == 'p':
            get_name_by_number()
        elif command == 'l':
            show_documents()
        elif command == 's':
            get_directory_by_number()
        elif command == 'a':
            add_document()
        elif command == 'd':
            remove_document()
            print(documents)
            print(directories)
        elif command == 'e':
            break

main()
```
