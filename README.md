Среда для выполнения теста

### 1. Скачать репозитарий в корень C-диска

c:\> git clone https://github.com/metaigra/test

### 2. Прописать в host

C:\Windows\System32\drivers\etc\hosts 

127.0.0.1 test.metaigra.ru

### 3. Поднять среду

Среду можно использовать свою (см. на ютюбе, как поднять Wordpress сайт на локальной машине).

Или развернуть доккер:

1. Установить WSL (Windows): c:\> wsl --install
2. Установить доккер: https://docs.docker.com/desktop/windows/install/
3. После этого поднять среду: c:\test\docker\test\> ..\\..\utils\make build

### 4. Проверить, что всё работает

http://test.metaigra.ru

http://test.metaigra.ru:8080

#### Подсказки

Для выполнения тестового задания: https://metaigra.ru/php/?result=1

* Видео: настройка среды разработки
* Видео: описание тестового задания
* Видео: анализ результата / code review


