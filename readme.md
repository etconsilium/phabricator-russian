### Русский интерфейс для Phabricator

Данный репозиторий содержит строки интерфейса для системы [Phabricator](https://www.phacility.com/) на русском языке.

### Установка

Перейте в папку расширений Фабрикаторе и склонируйте в неё данный проект.

```bash
cd path/to/phabricator/src/extensions/
git clone git@github.com:believer-ufa/phabricator-russian.git
```

После этого вы сразу сможете открыть настройки своего пользователя и выбрать русский язык. При необходимости, вы можете просто заходить в папку
проекта и обновлять строки через выполнение команды `git pull`.

### Перевод приоритетов задач

Разработчики Фабрикатора считают, что в переводе приоритетов нет нужды. Поэтому, простым образом перевести приоритеты и статусы вы не сможете.
Но всё-таки, видеть их названия на родном языке - приятное дело.
Чтобы добиться этого, задайте для параметра `maniphest.priorities` следующее значение:

```json
{
  "100": {
    "name": "Сделать прямо сейчас!",
    "keywords": [
      "unbreak"
    ],
    "short": "Нужно вчера!",
    "color": "pink"
  },
  "90": {
    "name": "Нужно определить приоритет",
    "keywords": [
      "triage"
    ],
    "short": "Определиться",
    "color": "violet"
  },
  "80": {
    "name": "Высокий",
    "keywords": [
      "high"
    ],
    "short": "Высокий",
    "color": "red"
  },
  "50": {
    "name": "Средний",
    "keywords": [
      "normal"
    ],
    "short": "Средний",
    "color": "orange"
  },
  "25": {
    "name": "Низкий",
    "keywords": [
      "low"
    ],
    "short": "Низкий",
    "color": "yellow"
  },
  "0": {
    "name": "Мечты и желания",
    "keywords": [
      "wish",
      "wishlist"
    ],
    "short": "Мечты",
    "color": "sky"
  }
}
```

### Перевод статусов задач

Со статусами точно такая же история, как и с приоритетами: их нельзя перевести через файлы переводов.
Для перевода этих текстов необходимо задать значение параметру конфигурации `maniphest.statuses`, например, вот такое:

```json
{
  "open": {
    "name": "Открыта",
    "special": "default",
    "prefixes": [
      "открываю",
      "открыл",
      "открытие",
      "переоткрытие",
      "переоткрываю",
      "переоткрыл"
    ]
  },
  "resolved": {
    "name": "Завершена",
    "name.full": "Закрыта, завершена",
    "closed": true,
    "special": "closed",
    "transaction.icon": "fa-check-circle",
    "prefixes": [
      "закрыл",
      "закрываю",
      "исправил",
      "закрытие",
      "исправил",
      "исправление",
      "исправляю",
      "разрешил",
      "разрешаю",
      "разрешение"
    ],
    "suffixes": [
      "как завершённая",
      "как завершённую",
      "как завершённой",
      "как исправленной",
      "как завершённую",
      "как исправленная"
    ],
    "keywords": [
      "закрыто",
      "исправлено",
      "разрешено"
    ]
  },
  "wontfix": {
    "name": "Нет желания делать",
    "name.full": "Закрыта, нет желания делать",
    "transaction.icon": "fa-ban",
    "closed": true,
    "prefixes": [
      "нет желания делать"
    ],
    "suffixes": [
      "как нежеланная"
    ]
  },
  "invalid": {
    "name": "Некорректная",
    "name.full": "Закрыта, некорректная",
    "transaction.icon": "fa-minus-circle",
    "closed": true,
    "claim": false,
    "prefixes": [
      "invalidate",
      "invalidates",
      "invalidated"
    ],
    "suffixes": [
      "как некорректную",
      "как некорректное"
    ]
  },
  "duplicate": {
    "name": "Дубликат",
    "name.full": "Закрыто, дубликат",
    "transaction.icon": "fa-files-o",
    "special": "duplicate",
    "closed": true,
    "claim": false
  },
  "spite": {
    "name": "Недовольство",
    "name.full": "Закрыто, недовольство",
    "name.action": "Закрыто с недовольством",
    "transaction.icon": "fa-thumbs-o-down",
    "silly": true,
    "closed": true,
    "prefixes": [
      "недоволен",
      "недовольство"
    ],
    "suffixes": [
      "с недовольством"
    ]
  }
}
```

### О переводе

К сожалению, в Фабрикаторе невозможно перевести некоторые строки, т.к. некоторые из них слишком жёстко вшиты в код проекта, о чём, в общем-то,
[предупреждают](https://secure.phabricator.com/book/phabcontrib/article/internationalization/) и сами разработчики.

В данный момент переведена большая часть строк интерфейса, но многие строки ещё только предстоит перевести. Скорее всего, перевод будет развиваться дальше.
