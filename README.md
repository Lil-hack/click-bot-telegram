# Deploy [Heroku](https://www.heroku.com/) Bot

## Подготовка
* Регистрируемся по [ссылке](https://signup.heroku.com/)

* Далее скачиваем [Heroku CLI](https://devcenter.heroku.com/articles/getting-started-with-python#set-up)

* Клонируем репозиторий
```
git clone https://github.com/deploy-your-bot-everywhere/heroku.git
```
> ВАЖНО!: Если вы создаете проект с нуля, то инициализируйте репозиторий командой `git init`

## Работа с Heroku CLI
* Логинимся
```bash
╰─ heroku login
heroku: Enter your login credentials
Email: example@gmail.com
Password: ******
Logged in as example@gmail.com

```
* Создаем приложение, где указываем нужный **buildpack** и регион **eu** или **us**
```bash
╰─ heroku create -b heroku/python --region eu deploy-heroku-bot 
Creating ⬢ deploy-heroku-bot... done, region is eu
Setting buildpack to heroku/python... done
https://deploy-heroku-bot.herokuapp.com/ | https://git.heroku.com/deploy-heroku-bot.git
```
* Связываем наш репозиторий с Heroku
```bash
heroku git:remote deploy-heroku-bot
```
* Прописываем токен бота в переменную окружения
```bash
╰─ heroku config:set TOKEN=123429417:AAEG39dbtyy4UrUDkvE7L5hIKuoIuQp9pfs
Setting TOKEN and restarting ⬢ deploy-heroku-bot... done, v4
TOKEN: 123429417:AAEG39dbtyy4UrUDkvE7L5hIKuoIuQp9pfs
```
* Деплоим
```bash
╰─ git push heroku master
Подсчет объектов: 11, готово.
Delta compression using up to 4 threads.
Сжатие объектов: 100% (5/5), готово.
Запись объектов: 100% (11/11), 1.61 KiB | 0 bytes/s, готово.
Total 11 (delta 0), reused 0 (delta 0)
remote: Compressing source files... done.
remote: Building source:
remote: 
remote: -----> Python app detected
remote:        Using supported version of Python 3.7 (python-3.7.0)
remote: -----> Installing python-3.7.0
remote: -----> Installing pip
remote: -----> Installing SQLite3
remote: -----> Installing requirements with pip
remote:        Collecting aiogram (from -r /tmp/build_13d2e83f9268344ff0a66817c2ec5878/requirements.txt (line 1))
remote:          Downloading https://files.pythonhosted.org/packages/59/f0/a6212f62fce3da9a530ad4dd25e5c049627fc10107b99a53a874a90009c5/aiogram-2.0-py3-none-any.whl (130kB)
remote:        Collecting aiohttp (from -r /tmp/build_13d2e83f9268344ff0a66817c2ec5878/requirements.txt (line 2))
remote:          Downloading https://files.pythonhosted.org/packages/97/29/9d1912f2746d171fc2fc0042a9edd117d386d53382a3aa12f7853466d52e/aiohttp-3.4.4-cp37-cp37m-manylinux1_x86_64.whl (1.1MB)
remote:        Collecting certifi>=2018.8.24 (from aiogram->-r /tmp/build_13d2e83f9268344ff0a66817c2ec5878/requirements.txt (line 1))
remote:          Downloading https://files.pythonhosted.org/packages/56/9d/1d02dd80bc4cd955f98980f28c5ee2200e1209292d5f9e9cc8d030d18655/certifi-2018.10.15-py2.py3-none-any.whl (146kB)
remote:        Collecting Babel>=2.6.0 (from aiogram->-r /tmp/build_13d2e83f9268344ff0a66817c2ec5878/requirements.txt (line 1))
remote:          Downloading https://files.pythonhosted.org/packages/b8/ad/c6f60602d3ee3d92fbed87675b6fb6a6f9a38c223343ababdb44ba201f10/Babel-2.6.0-py2.py3-none-any.whl (8.1MB)
remote:        Collecting multidict<5.0,>=4.0 (from aiohttp->-r /tmp/build_13d2e83f9268344ff0a66817c2ec5878/requirements.txt (line 2))
remote:          Downloading https://files.pythonhosted.org/packages/a7/57/cefa7a7f30b03006506dd0f44988613d40efbc987d82f34dfe9027800347/multidict-4.4.2-cp37-cp37m-manylinux1_x86_64.whl (386kB)
remote:        Collecting chardet<4.0,>=2.0 (from aiohttp->-r /tmp/build_13d2e83f9268344ff0a66817c2ec5878/requirements.txt (line 2))
remote:          Downloading https://files.pythonhosted.org/packages/bc/a9/01ffebfb562e4274b6487b4bb1ddec7ca55ec7510b22e4c51f14098443b8/chardet-3.0.4-py2.py3-none-any.whl (133kB)
remote:        Collecting yarl<2.0,>=1.0 (from aiohttp->-r /tmp/build_13d2e83f9268344ff0a66817c2ec5878/requirements.txt (line 2))
remote:          Downloading https://files.pythonhosted.org/packages/43/b8/057c3e5b546ff4b24263164ecda13f6962d85c9dc477fcc0bcdcb3adb658/yarl-1.2.6.tar.gz (159kB)
remote:        Collecting attrs>=17.3.0 (from aiohttp->-r /tmp/build_13d2e83f9268344ff0a66817c2ec5878/requirements.txt (line 2))
remote:          Downloading https://files.pythonhosted.org/packages/3a/e1/5f9023cc983f1a628a8c2fd051ad19e76ff7b142a0faf329336f9a62a514/attrs-18.2.0-py2.py3-none-any.whl
remote:        Collecting async-timeout<4.0,>=3.0 (from aiohttp->-r /tmp/build_13d2e83f9268344ff0a66817c2ec5878/requirements.txt (line 2))
remote:          Downloading https://files.pythonhosted.org/packages/e1/1e/5a4441be21b0726c4464f3f23c8b19628372f606755a9d2e46c187e65ec4/async_timeout-3.0.1-py3-none-any.whl
remote:        Collecting pytz>=0a (from Babel>=2.6.0->aiogram->-r /tmp/build_13d2e83f9268344ff0a66817c2ec5878/requirements.txt (line 1))
remote:          Downloading https://files.pythonhosted.org/packages/f8/0e/2365ddc010afb3d79147f1dd544e5ee24bf4ece58ab99b16fbb465ce6dc0/pytz-2018.7-py2.py3-none-any.whl (506kB)
remote:        Collecting idna>=2.0 (from yarl<2.0,>=1.0->aiohttp->-r /tmp/build_13d2e83f9268344ff0a66817c2ec5878/requirements.txt (line 2))
remote:          Downloading https://files.pythonhosted.org/packages/4b/2a/0276479a4b3caeb8a8c1af2f8e4355746a97fab05a372e4a2c6a6b876165/idna-2.7-py2.py3-none-any.whl (58kB)
remote:        Installing collected packages: multidict, chardet, idna, yarl, attrs, async-timeout, aiohttp, certifi, pytz, Babel, aiogram
remote:          Running setup.py install for yarl: started
remote:            Running setup.py install for yarl: finished with status 'done'
remote:        Successfully installed Babel-2.6.0 aiogram-2.0 aiohttp-3.4.4 async-timeout-3.0.1 attrs-18.2.0 certifi-2018.10.15 chardet-3.0.4 idna-2.7 multidict-4.4.2 pytz-2018.7 yarl-1.2.6
remote: 
remote: -----> Discovering process types
remote:        Procfile declares types -> web
remote: 
remote: -----> Compressing...
remote:        Done: 56.7M
remote: -----> Launching...
remote:        Released v5
remote:        https://deploy-heroku-bot.herokuapp.com/ deployed to Heroku
remote: 
remote: Verifying deploy... done.
To https://git.heroku.com/deploy-heroku-bot.git
 * [new branch]      master -> master
```
* Проверяем, что все работает 🎉 🎊
```bash
╰─ heroku ps         
Free dyno hours quota remaining this month: 548h 51m (99%)
Free dyno usage for this app: 0h 0m (0%)
For more information on dyno sleeping and how to upgrade, see:
https://devcenter.heroku.com/articles/dyno-sleeping

=== web (Free): python main.py (1)
web.1: up 2018/11/04 17:00:27 +0300 (~ 51s ago)
```

## Деплой через GitHub
1. На [странице](https://dashboard.heroku.com/apps) создаем новое приложение
![Create app](https://i.imgur.com/1jBnzNG.png)
![Create app](https://i.imgur.com/jYYiSFe.png)
> Не забываем добавить токен бота `heroku config:set TOKEN=123429417:AAEG39dbtyy4UrUDkvE7L5hIKuoIuQp9pfs`
2. Подключаем наш репозиторий
![Create app](https://i.imgur.com/yu6ePUK.png)
3. Включаем **Automatic deploys** ветки **master**

![Create app](https://i.imgur.com/HK0o5v0.png)
4. Так же выбираем нужную нам ветку и жмем **Deploy Branch**
![Create app](https://i.imgur.com/zaufuoh.png)

## Пояснение к коду
1. [main.py](https://github.com/deploy-your-bot-everywhere/heroku/blob/master/main.py)
```python
TOKEN = os.environ['TOKEN']  # Берем токен из переменной окружения, которую добавили ранее
WEBHOOK_HOST = 'https://deploy-heroku-bot.herokuapp.com'  # Здесь указываем https://<название_приложения>.herokuapp.com
WEBAPP_HOST = '0.0.0.0'  # Слушаем все подключения к нашему приложению
WEBAPP_PORT = os.environ.get('PORT')  # тк в Procfile мы указали process_type web, heroku сгенерирует нам нужный порт, его достаточно взять из переменной окружения
```
2. В [runtime.txt](https://github.com/deploy-your-bot-everywhere/heroku/blob/master/runtime.txt) указываем версию python
3. В [Procfile](https://github.com/deploy-your-bot-everywhere/heroku/blob/master/Procfile) `<process type>: <command>`
4. И не забываем указывать зависимости в файле [requirements.txt](https://github.com/deploy-your-bot-everywhere/heroku/blob/master/requirements.txt)
