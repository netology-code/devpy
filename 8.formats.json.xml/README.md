# K лекции 8.«Работа с разными форматами данных»

## Task 1
```
import json
import collections
from pprint import pprint
import xml.etree.ElementTree as ET


def read_json(file_path, len_word=6, top_words=10):
   with open(file_path, 'r', encoding='utf-8') as news_file:
       news = json.load(news_file)
       description_words = []
       for item in news['rss']['channel']['items']:
           description = [word for word in item['description'].split(' ') if len(word) > len_word]
           description_words.extend(description)
       counter_words = collections.Counter(description_words)
       pprint(counter_words.most_common(top_words))
```

## Task 2.
```
def read_xml(file, len_word=6, top_words=10):
   tree = ET.parse(file)
   root = tree.getroot()
   xml_items = root.findall('channel/item')
   description_words = []
   descriptions = [item.find('description').text.split() for item in xml_items]
   for description in descriptions:
       description = [word for word in description if len(word) > len_word]
       description_words.extend(description)
   counter_words = collections.Counter(description_words)
   pprint(counter_words.most_common(top_words))


if __name__ == '__main__':
   read_json('newsafr.json')
   print('------')
   read_xml('newsafr.xml')

```
