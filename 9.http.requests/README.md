# K лекции 9.«Работа с библиотекой requests, http-запросы»
```
import requests
import os
```

## Task 1
``` 
def get_smart_superhero(names):
    top_intelligence = -1
    top_name = ''
    for name in names:
        r = requests.get(f'https://www.superheroapi.com/api.php/2619421814940190/search/{name}')
        data = r.json()
        intelligence = int(data['results'][0]['powerstats']['intelligence'])
        print(name, intelligence)
        if intelligence > top_intelligence:
            top_intelligence = intelligence
            top_name = name

    print(f'{top_name} - самый умный, его интеллект равен {top_intelligence}.')


get_smart_superhero(['Hulk', 'Captain America', 'Thanos'])
```

## Task 2
```
class YaUploader:
    def __init__(self, token: str):
        self.token = token

    def upload(self, file_path: str):
        my_headers = {'Authorization': self.token}
        fname = os.path.split(file_path)[1]
        my_params = {'path': '/' + fname, 'overwrite': 'true'}
        url = 'https://cloud-api.yandex.net:443/v1/disk/resources/upload'
        r = requests.get(url, headers=my_headers, params=my_params)

        if r.status_code != requests.codes.ok:
            return f'При получении ссылки для загрузки произошла ошибка (код: {r.status_code})'

        href = r.json()['href']
        with open(file_path, 'rb') as fh:
            r = requests.put(href, data=fh.read())

        if r.status_code not in (requests.codes.created, requests.codes.accepted):
            return f'При загрузке файла произошла ошибка (код: {r.status_code})'
        return f'Файл {fname} успешно загружен на Яндекс.Диск'


if __name__ == '__main__':
    my_file_path = 'result.txt'
    auth_token = ''
    uploader = YaUploader(auth_token)
    result = uploader.upload(my_file_path)
    print(result)
```
