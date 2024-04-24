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

**<ins>My repository in Nexus<ins>**

![alt text](https://raw.githubusercontent.com/Kovrei/8-02/main/screenshots/nxs_http.PNG)

**<ins>Pipline<ins>**

```java
pipeline {
    agent any
    stages {
        stage('Git clone') {
            steps {
                git 'https://github.com/netology-code/sdvps-materials.git'
            }
        }
        stage('Run tests') {
            steps {
                sh '/usr/local/go/bin/go test .'
            }
        }
        stage('Go build app and curl upload file in Nexus to repo') {
            steps {
                sh 'CGO_ENABLED=0 GOOS=linux /usr/local/go/bin/go build -a -installsuffix nocgo -o ./app .'
                sh 'curl -u admin:admin http://51.250.67.193:8081/repository/mission3/ --upload-file /app .'
            }
        }
    }
}
```

**<ins>Build go to Nexus<ins>**

![alt text](https://raw.githubusercontent.com/Kovrei/8-02/main/screenshots/jnk_log.PNG)

**<ins>My browse repository in Nexus <ins>**

![alt text](https://raw.githubusercontent.com/Kovrei/8-02/main/screenshots/nxs_result.PNG)

