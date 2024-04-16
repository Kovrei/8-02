# Что такое DevOps. СI/СD. Осипенков Андрей.
## Задание 1
Что нужно сделать:

1. Установите себе jenkins по инструкции из лекции или любым другим способом из официальной документации. Использовать Docker в этом задании нежелательно.
2. Установите на машину с jenkins golang.
3. Используя свой аккаунт на GitHub, сделайте себе форк репозитория. В этом же репозитории находится дополнительный материал для выполнения ДЗ.
4. Создайте в jenkins Freestyle Project, подключите получившийся репозиторий к нему и произведите запуск тестов и сборку проекта go test . и docker build ..  
В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.

**<ins>My config Jenkins<ins>**

![alt text](https://raw.githubusercontent.com/Kovrei/8-02/main/screenshots/1.1-config.PNG)

**<ins>My config Jenkins<ins>**

![alt text](https://raw.githubusercontent.com/Kovrei/8-02/main/screenshots/1.2-config.PNG)

**<ins>My finish resultat<ins>**

![alt text](https://raw.githubusercontent.com/Kovrei/8-02/main/screenshots/1-fin.PNG)

## Задание 2
Что нужно сделать:

1. Создайте новый проект pipeline.
2. Перепишите сборку из задания 1 на declarative в виде кода.  
В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.

**<ins>My config Jenkins<ins>**

![alt text](https://raw.githubusercontent.com/Kovrei/8-02/main/screenshots/2.1-config.PNG)

**<ins>My finish resultat<ins>**

![alt text](https://raw.githubusercontent.com/Kovrei/8-02/main/screenshots/2.2-finish.PNG)

## Задание 3
Что нужно сделать:

1. Установите на машину Nexus.
2. Создайте raw-hosted репозиторий.
3. Измените pipeline так, чтобы вместо Docker-образа собирался бинарный go-файл. Команду можно скопировать из Dockerfile.
4. Загрузите файл в репозиторий с помощью jenkins.  
В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.

**<ins>It is my trubble:
docker: Error response from daemon: driver failed programming external connectivity on endpoint nexus (9a430ad65fe204d53bf221b39d4d1e865d149474166d17016e9c2553991d1264): 
Error starting userland proxy: listen tcp4 84.201.157.43:8082: bind: cannot assign requested address.<ins>**

![alt text](https://raw.githubusercontent.com/Kovrei/8-02/main/screenshots/3.1%20truble.PNG)
