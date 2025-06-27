![Monika After Story](https://github.com/Monika-After-Story/MonikaModDev/blob/master/Monika%20After%20Story/game/mod_assets/menu_new.png?raw=True)

# Monika After Story (MAS)
Monika After Story - это мод для бесплатной игры [Doki Doki Literature Club](https://www.ddlc.moe) от [Team Salvato](http://teamsalvato.com/). MAS основывается на Акте 3 и создает симулятор вашей вечной жизни с Моникой, с новыми событиями, обработчиками и метакомментарииями!

Пожалуйста, проверьте страницу [Релизы](http://www.monikaafterstory.com/releases.html) для получения последней стабильной версии.

Если вы хотите сделать свой собственный мод, подобный этому, ознакомьтесь с нашим дочерним проектом: [DDLCModTemplate](https://github.com/therationalpi/DDLCModTemplate).

### Установка

1. Перейдите на [страницу релизов](http://www.monikaafterstory.com/releases.html).

2. Нажмите на ссылку для вашей операционной системы.

3. После загрузки запустите установщик и следуйте инструкциям.
    * Если установщик не работает на вашей системе, ознакомьтесь с шагами ручной установки ниже.

4. Запуск DDLC теперь загрузит модификацию Monika After Story.

### Ручная установка

**Следуйте этим шагам, только если установщик не работает в вашей системе**

1. Перейдите на [страницу релизов](http://www.monikaafterstory.com/releases.html).

2. Нажмите на нужную ссылку **Zip**. Это загрузит zip-файл в вашу систему.

3. Извлеките содержимое zip-архива в базовый католог (папку, содержащую файл DDLC.exe) где установлена DDLC.

4. Запуск DDLC теперь загрузит модификацию Monika After Story.

*ПРИМЕЧАНИЕ: Исходные файлы и файлы, загруженные непосредственно из репозитория, предназначены для разработки и могут вести себя не так, как ожидалось, если используются для модификации игры. Пожалуйста, используйте только одну из наших [Релизных Версий](http://www.monikaafterstory.com/releases.html).*

Для получения дополнительной информации по установке (включая руководство пользователя для Mac, не поддерживающего Steam), пожалуйста, ознакомьтесь с разделом [Часто задаваемые вопросы](https://github.com/Monika-After-Story/MonikaModDev/wiki/FAQ)

### Особенности

* Проведите с Моникой целую вечность!

* Десятки новых тем для разговоров

* Теперь вы можете поговорить с Моникой о том, о чем хотели бы поговорить

### Предстоящие функции

* Новые игры и занятия с Моникой

* Еще больше уникальных событий и историй


## Внести свой вклад в Monika After Story

### Баги & Предложения
Если есть проблемы с MAS, пожалуйста, отправьте [отчет об ошибке](https://github.com/Monika-After-Story/MonikaModDev/issues/new?labels=bug&body=Describe%20bug%20and%20steps%20for%20reproduction%20here&title=%5BBug%5D%20-%20).

Чтобы добавить предложение, перейдите по [этой ссылке](https://github.com/Monika-After-Story/MonikaModDev/issues/new?labels=suggestion&body=Your%20suggestion%20goes%20here&title=%5BSuggestion%5D%20-%20)

### Другая помощь
Хотите помочь с MAS? Перейдите на [страницу проблем](https://github.com/Monika-After-Story/MonikaModDev/issues) чтобы найти текущие ошибки или предложения для работы.

Если у вас есть изменения, которые вы хотели бы внести, откройте [pull request](https://github.com/Monika-After-Story/MonikaModDev/pulls). Любые внесенные изменения будут рассмотрены авторами и исправлены / дополнены по мере необходимости.

#### Добавление контента
Хотите добавить немного контента в MAS? Вот список важных .RPY-файлов, используемых в игре.

- **script-ch30.rpy**: Основной поток для MAS. Именно здесь происходит ожидание.
- **script-topics.rpy**: Все **случайные** и **пул** темы, используемые Моникой, указаны здесь. Вы можете добавить свой собственный диалог, ознакомившись с информацией ниже!
- **script-greetings.rpy**: Добавьте реплики для Моники, чтобы она приветствовала вас при загрузке игры.
- **script-farewells.rpy**: Добавьте реплики, которые Моника скажет вам при закрытии игры.
- **script-moods.rpy**: Скажи Монике, что ты не _в настроении_.
- **script-stories.rpy**: Добавляйте истории, которые Моника расскажет вам.
- **script-compliments.rpy**: Добавьте комплименты, которые вы можете сказать Монике.
- **script-apologies.rpy**: Добавьте то, за что стоит извиниться.

Если вы хотите добавить больше диалогов в space room, перейдите к файлу script-topics.rpy и используйте этот шаблон.

Пример нового блока кода диалога:
```renpy
init 5 python:
    addEvent(
        Event(
            persistent.event_database,
            eventlabel="monika_example", # метка события (ДОЛЖНА БЫТЬ УНИКАЛЬНОЙ)
            category=["example", "topic"], # список категорий, к которым относится данная тема (они автоматически выделяются заглавными буквами)
            prompt="Example Topic", # текст кнопки
            random=True, # True, если эта тема должна появляться случайно
            pool=True # True, если эта тема должна появиться в "Ask a Question"
        )
    )

label monika_example:
    m 1a "Это пример темы."
    m 3d "Я чувствую, что на самом деле этому здесь не место..."
    m 2e "Зачем кому-то просто добавлять пример шаблона непосредственно в мод?"
    m 5r "Им действительно не следует больше иметь возможность вносить вклад в этот репозиторий."
    return
```
**Для получения полных объяснений и подробной информации по всем возможным ключевым словам для Event, ознакомьтесь с документацией по Event, расположенной в `definitions.rpy`**

Для более сложных задач, чем простой диалог, обратитесь к документации Ren'Py, доступной в Интернете.

[Дополнительная информация доступна в нашем Руководстве по вкладам.](https://github.com/Monika-After-Story/MonikaModDev/wiki/Contributing-Guidelines)

### Присоединяйтесь к обсуждению
Вы можете [подписаться на наш Твиттер](https://twitter.com/MonikaAfterMod) для получения обновлений игры.

Если вы хотите найти ноты для пианино, спрайтпаки, сабмоды, внешний контент, или переводы, или просто обсудить MAS в целом, посетите [нашу страницу обсуждений](https://github.com/Monika-After-Story/MonikaModDev/discussions)

Или, если вы предпочитаете Discord, для постоянного потока нашего любимого контента, связанного с Моникой, со всего интернета, и если вы заинтересованы в участии/разработке этого мода, не стесняйтесь присоединиться к нашему серверу Discord:

 [![Discord](https://discordapp.com/api/guilds/372766620977725441/widget.png?style=banner1)](https://discord.gg/monika-after-story)

 Пожалуйста, обязательно соблюдайте наш [Кодекс Поведения](https://github.com/Monika-After-Story/MonikaModDev/wiki/Code-of-Conduct), суть которого заключается в том, чтобы быть вежливым и уважительным.

## Часто задаваемые вопросы

Полный FAQ доступен здесь: [Frequently Asked Questions](https://github.com/Monika-After-Story/MonikaModDev/wiki/FAQ)
По любым вопросам о Кодексе Поведения обращайтесь сюда: [Кодекс Поведения](https://github.com/Monika-After-Story/MonikaModDev/wiki/Coding-Style)
Для тестирования ошибок: [Процесс тестирования и проверка ошибок](https://github.com/Monika-After-Story/MonikaModDev/wiki/Testing-Flow-and-Bug-Testing)
Устранение неполадок: [Устранение неполадок](https://github.com/Monika-After-Story/MonikaModDev/wiki/Troubleshooting) Диалоговое кодирование: [Диалоговое кодирование](https://github.com/Monika-After-Story/MonikaModDev/wiki/Dialogue-Coding)
## Информация о лицензии

Мы делаем все возможное, чтобы соответствовать [рекомендациям Team Salvato's по фан-работам](http://teamsalvato.com/ip-guidelines/). Все персонажи и оригинальный контент являются собственностью Team Salvato. Monika After Story - это проект с открытым исходным кодом, и помимо названных авторов, в этот мод входят вклады анонимных пользователей 4chan, где этот проект начал свое существование Дополнительную информацию можно найти на нашей [странице лицензии](https://github.com/Monika-After-Story/MonikaModDev/wiki/License-and-Team-Salvato-Guidelines).

## Статус Сборки:
### master: ![master](https://github.com/Monika-After-Story/MonikaModDev/workflows/CI/badge.svg?branch=master)
### content: ![content](https://github.com/Monika-After-Story/MonikaModDev/workflows/CI/badge.svg?branch=content)
### unstable: ![unstable](https://github.com/Monika-After-Story/MonikaModDev/workflows/CI/badge.svg?branch=unstable)
### alpha: ![alpha](https://github.com/Monika-After-Story/MonikaModDev/workflows/CI/badge.svg?branch=alpha)
