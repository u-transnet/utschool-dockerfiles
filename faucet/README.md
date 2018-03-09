# ut-school-faucet

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

