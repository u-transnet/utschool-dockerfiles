# ut-school-faucet

Данный докер представляет собой utschool-faucet и минимально необходимая среда окружения описанная в файле docker-compose.yml и запускающаяся соответствующей командой.

# Предустановки
Прежде всего необходимо создать папку configs/project и создать там локальные файлы конфигурации, которые не синхроинизируются с git'ом.

**Примеры конфигураций**

Путь: configs/project/settings.py</br>
**Файл локальных настроек проекта**
```
from .development import * 

ALLOWED_HOSTS = ['web']

DATABASES = {  
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'postgres',
        'USER': 'postgres',
        'HOST': 'db',
        'PORT': 5432,
    }
} 
```

Путь: configs/project/faucet/private_key.py</br>
Путь: configs/project/faucet/test_tokens.py</br>
Аналогичны файлам из папки faucet/configs/ из [репозитория faucet'а](https://github.com/u-transnet/utschool-faucet)

Путь: configs/nginx.conf
Конфигурация nginx сервера, который запускается как часть минимально необходимой среды окружения 

# Запуск и управление
```
docker-compose up # Запуск
docker-compose up -d # Запуск в фоновом режиме
docker-compose up --build # Запуск с пересборкой образов
docker container stop $(docker ps -a -q) # Остановка всех контейнеров
docker rm $(docker ps -a -q) # Удаление всех контейнеров
```

