### userlst - список юзеров, квот и бекапов

``` 
serverctl( 'userlst' ) 
```

### useradd - создаёт юзера 
###### обязательные параметры: логин, пароль, квота; не обязательные: версия;
###### useradd "USERNAME" "PASSWORD" "QUOTA" [ "VERSION"]
``` 
serverctl( 'useradd', [
           'USERNAME' => 'test',
           'PASSWORD' => 'test',
           'QUOTA' => 100,
           'VERSION' => '2.7.0'
        ] ) 
```

### usermod - меняет параметры юзера 
###### обязательные параметры: логин, пароль; не обязательные: квота, версия; 
###### useradd "USERNAME" "PASSWORD" [ "QUOTA" ]
    ``` 
serverctl( 'usermod', [
           'USERNAME' => 'test',
           'PASSWORD' => 'test',
           'QUOTA' => 100
        ] ) 
```

### userdel - убивает юзера 
###### обязательные параметры: логин; 
###### userdel "USERNAME"
``` 
serverctl( 'userdel', [
           'USERNAME' => 'test',
        ] ) 
```

### usercnf - чистит кеш, создаёт каталог с логами, если его нет и фиксит разрешения 
###### Нe обязательные параметры: логин; 
###### usercnf ["USERNAME"]
``` 
serverctl( 'usercnf', [
           'USERNAME' => 'test',
        ] ) 
```

### userbak - если не указан логин, то бекапит всех 
###### Нe обязательные параметры: логин; 
###### userbak ["USERNAME"]
``` 
serverctl( 'userbak', [
           'USERNAME' => 'test',
        ] ) 
```

### userres - восстанавливает бекап
###### обязательные параметры: логин, дата отката; 
###### userres "USERNAME" "DATE"
``` 
serverctl( 'userres', [
                'USERNAME' => 'test',
                'DATE' => 'YYYY-MM-DD'
        ] ) 
```

### userupd - делает автоапгрейд modx
###### обязательные параметры: логин; не обязательные: версия;
###### userupd "USERNAME" [ "VERSION" ]
``` 
serverctl( 'userupd', [
                'USERNAME' => 'test',
                'VERSION' => '2.7.0'
        ] ) 
```

### hostlst - список доменов с их привязкой и состоянием
###### hostlst 
``` 
serverctl( 'hostlst') 
```

### hostadd - добавляет домен юзеру
###### обязательные параметры: логин, домен; 
###### hostadd "USERNAME" "HOSTNAME"
``` 
serverctl( 'hostadd', [
                'USERNAME' => 'test',
                'HOSTNAME' => 'test',
        ] ) 
```

### hostdel -  убивает домен
###### обязательные параметры: домен; 
###### hostdel "HOSTNAME"
``` 
serverctl( 'hostdel', [
                'HOSTNAME' => 'test',
        ] ) 
```

### hostena -  включает домен
###### обязательные параметры: домен; 
###### hostena "HOSTNAME"
``` 
serverctl( 'hostena', [
                'HOSTNAME' => 'test',
        ] ) 
```

### hostdis -  отключает домен
###### обязательные параметры: домен; 
###### hostdis "HOSTNAME"
``` 
serverctl( 'hostdis', [
                'HOSTNAME' => 'test',
        ] ) 
```

### hostcnf - делает регенерацию конфигов
###### Нужно вызывать, если в папку пользователя добавили свой SSL сертификат. домен.crt - сертификат домен.key - ключ
###### не обязательные параметры: домен; 
###### hostcnf [ "HOSTNAME" ]
``` 
serverctl( 'hostcnf', [
                'HOSTNAME' => 'test',
        ] ) 
```

### version -  "Для красоты" =)
``` 
serverctl( 'version' ) 
```
