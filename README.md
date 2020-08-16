# Currency
Парсер курса валюты с поисковой выдачи Google
_________________________________________
Программа написана на Python с использованием:
- BeautifulSoup (парсинг данных в формате HTML, XML)
- requests (направление http-запроса на сервер)
- python-dotenv (загрузка и считывание переменных окружения из файла .env)
- smtplib (модуль для работы с почтой)

## Как запустить программу:
1) Клонируйте репозитроий с программой:
```
git clone https://github.com/leks20/currency
```
2) В созданной директории установите виртуальное окружение, активируйте его и установите необходимые зависимости:
```
python3 -m venv venv

. venv/bin/activate

pip install -r requirements.txt
```
3) Создайте в директории файл .env и поместите туда вашу электронную почту с паролем в формате email = 'ххххххххх', password = 'ххххххххххх'
4) Откройте файл main.py и в заголовке описание клиента укажите значение, идентифицирующее браузер и операционную систему для веб-сервера (его можно получить, если ввести в Google "My User Agent")
```
headers = {'User-Agent': 'xxxxxxxx'}
```
5) Запустите код

## Как работает программа:
Программа получает из поисковой выдачи Google html-код с текущим курсом доллара, который выводится на экран каждую минуту.

При сильном изменении курса доллара (более, чем на 3 рубля) на указанную электронную почту направляется письмо с текстом:

*"Курс доллара сильно вырос!"* либо *"Курс доллара сильно упал!"*
