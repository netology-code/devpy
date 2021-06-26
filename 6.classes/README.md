# K лекции 6.«Классы и их применение в Python»

## Task 1
```
class Sheep:
    sound = 'бе бе'

    def __init__(self, name, weight):
        self.name = name
        self.weight = weight

    def say(self):
        print(self.sound)

    def feeding(self):
        print('Вы покормили', self.name)

    def shearing(self):
        print('Вы постригли', self.name)


class Goose:
    sound = 'га га'

    def __init__(self, name, weight):
        self.name = name
        self.weight = weight

    def say(self):
        print(self.sound)

    def feeding(self):
        print('Вы покормили', self.name)

    def collect_eggs(self):
        print('Вы собрали яйца у ', self.name)


class Chicken:
    sound = 'ко ко'

    def __init__(self, name, weight):
        self.name = name
        self.weight = weight

    def say(self):
        print(self.sound)

    def feeding(self):
        print('Вы покормили', self.name)

    def collect_eggs(self):
        print('Вы собрали яйца у ', self.name)


class Duck:
    sound = 'кря кря'

    def __init__(self, name, weight):
        self.name = name
        self.weight = weight

    def say(self):
        print(self.sound)

    def feeding(self):
        print('Вы покормили', self.name)

    def collect_eggs(self):
        print('Вы собрали яйца у ', self.name)


class Cow:
    sound = 'му му'

    def __init__(self, name, weight):
        self.name = name
        self.weight = weight

    def say(self):
        print(self.sound)

    def feeding(self):
        print('Вы покормили', self.name)

    def milk(self):
        print('Вы подоили', self.name)


class Goat:
    sound = 'бе бе'

    def __init__(self, name, weight):
        self.name = name
        self.weight = weight

    def say(self):
        print(self.sound)

    def feeding(self):
        print('Вы покормили', self.name)

    def milk(self):
        print('Вы подоили', self.name)
```

## Task 2
```
grey_goose = Goose('Серый', 15)
white_goose = Goose('Белый', 12)
cow = Cow('Манька', 120)
barashek = Sheep('Барашек', 59)
kudryash = Sheep('Кудрявый', 65)
koko_hen = Chicken('Ко-Ко', 8)
kuka_hen = Chicken('Кукареку', 5)
goat_0 = Goat('Рога', 37)
goat_1 = Goat('Копыта', 38)
duck = Duck('Кряква', 19)

animals = [grey_goose, white_goose, cow, barashek, kudryash, koko_hen, kuka_hen, goat_0, goat_1, duck]
common_sum = 0
max_weight = grey_goose.weight
max_weight_name = grey_goose.name

for animal in animals:
    common_sum += animal.weight
    if animal.weight > max_weight:
        max_weight = animal.weight
        max_weight_name = animal.name

print('Общий вес животных', common_sum, 'кг')
print('Самый тяжелый', max_weight_name)
```

## Task 3
```
class Track:

    def __init__(self, name, duration):
        self.name = name
        self.duration = duration

    def show(self):
        print(f'{self.name}-{self.duration}')


class Album:

    def __init__(self, name, group, tracks):
        self.name = name
        self.group = group
        self.tracks = tracks

    def get_tracks(self):
        for track in self.tracks:
            track.show()

    def add_track(self, track):
        self.tracks.append(track)

    def get_duration(self):
        album_duration = 0
        for track in self.tracks:
            album_duration += track.duration
        print('Длительность альбома', album_duration)


violator_tracks = [Track('Personal Jesus', 5), Track('Enjoy the Silence', 4), Track('Clean', 3)]
violator = Album('Violator', 'Depeche Mode', violator_tracks)
violator.get_duration()

smiths_tracks = [Track('Reel Around the Fountain', 7), Track('Miserable Lie', 4), Track('Pretty Girls Make Graves', 3)]
smiths_album = Album('The Smiths', 'The Smiths', smiths_tracks)
smiths_album.get_duration()
```

---

## Task 1
```
class Animals:
    sound = ''

    def __init__(self, name, weight):
        self.name = name
        self.weight = weight

    def say(self):
        print(self.sound)

    def feeding(self):
        print('Вы покормили', self.name)


class Bird(Animals):
    def collect_eggs(self):
        print('Вы собрали яйца у ', self.name)


class Mammal(Animals):  # млекопитающие
    def milk(self):
        print('Вы подоили', self.name)


class Sheep(Animals):
    sound = 'бе бе'

    def shearing(self):
        print('Вы постригли', self.name)


class Goose(Bird):
    sound = 'га га'


class Chicken(Bird):
    sound = 'ко ко'


class Duck(Bird):
    sound = 'кря кря'


class Cow(Mammal):
    sound = 'му му'


class Goat(Mammal):
    sound = 'бе бе'


grey_goose = Goose('Серый', 15)
white_goose = Goose('Белый', 12)
cow = Cow('Манька', 120)
barashek = Sheep('Барашек', 59)
kudryash = Sheep('Кудрявый', 65)
koko_hen = Chicken('Ко-Ко', 8)
kuka_hen = Chicken('Кукареку', 5)
goat_0 = Goat('Рога', 37)
goat_1 = Goat('Копыта', 38)
duck = Duck('Кряква', 19)

animals = [grey_goose, white_goose, cow, barashek, kudryash, koko_hen, kuka_hen, goat_0, goat_1, duck]
common_sum = 0
max_weight = grey_goose.weight
max_weight_name = grey_goose.name

for animal in animals:
    animal.say()
    common_sum += animal.weight
    if animal.weight > max_weight:
        max_weight = animal.weight
        max_weight_name = animal.name

print('Общий вес животных', common_sum, 'кг')
print('Самый тяжелый', max_weight_name)
print('----')

```

## Task 2

```
class Track:

    def __init__(self, name, duration):
        self.name = name
        self.duration = duration

    def __str__(self):
        return f'{self.name}-{self.duration}min'

    def __eq__(self, other):
        return self.duration == other.duration

    def __gt__(self, other):
        return self.duration > other.duration

    def __lt__(self, other):
        return self.duration < other.duration

    def __ge__(self, other):
        return self.duration >= other.duration

    def __le__(self, other):
        return self.duration <= other.duration


class Album:

    def __init__(self, name, group, tracks):
        self.name = name
        self.group = group
        self.tracks = tracks

    def get_tracks(self):
        for track in self.tracks:
            track.show()

    def add_track(self, track):
        self.tracks.append(track)

    def get_duration(self):
        album_duration = 0
        for track in self.tracks:
            album_duration += track.duration
        print('Длительность альбома', album_duration)

    def __str__(self):
        s = f'Name group: {self.group}\n' \
            f'Name album: {self.name}\n' \
            f'Tracks:\n'
        for track in self.tracks:
            s += f'\t {track}\n'
        return s


violator_tracks = [Track('Personal Jesus', 5), Track('Enjoy the Silence', 4), Track('Clean', 3)]
violator = Album('Violator', 'Depeche Mode', violator_tracks)
violator.get_duration()
print(violator)

smiths_tracks = [Track('Reel Around the Fountain', 7), Track('Miserable Lie', 4), Track('Pretty Girls Make Graves', 3)]
smiths_album = Album('The Smiths', 'The Smiths', smiths_tracks)
smiths_album.get_duration()
print(smiths_album)

print(violator_tracks[0] > smiths_tracks[0])
print(violator_tracks[2] == smiths_tracks[2])
```

