
### Инструкция по выполнению домашнего задания

1.  Сделайте fork [репозитория c шаблоном решения](https://www.google.com/url?q=https://github.com/netology-code/sys-pattern-homework&sa=D&source=editors&ust=1787045313894520&usg=AOvVaw02brPMn_yBtwBvI4mU0uwz) к себе в GitHub и переименуйте его по названию или номеру занятия, например, [https://github.com/имя-вашего-репозитория/gitlab-hw](https://www.google.com/url?q=https://github.com/%25D0%25B8%25D0%25BC%25D1%258F-%25D0%25B2%25D0%25B0%25D1%2588%25D0%25B5%25D0%25B3%25D0%25BE-%25D1%2580%25D0%25B5%25D0%25BF%25D0%25BE%25D0%25B7%25D0%25B8%25D1%2582%25D0%25BE%25D1%2580%25D0%25B8%25D1%258F/gitlab-hw&sa=D&source=editors&ust=1787045313894829&usg=AOvVaw2bHqj-9OSydhv_zM4xXY2u) или [https://github.com/имя-вашего-репозитория/8-03-hw](https://www.google.com/url?q=https://github.com/%25D0%25B8%25D0%25BC%25D1%258F-%25D0%25B2%25D0%25B0%25D1%2588%25D0%25B5%25D0%25B3%25D0%25BE-%25D1%2580%25D0%25B5%25D0%25BF%25D0%25BE%25D0%25B7%25D0%25B8%25D1%2582%25D0%25BE%25D1%2580%25D0%25B8%25D1%258F/8-03-hw&sa=D&source=editors&ust=1787045313895057&usg=AOvVaw1gIBXgJRk8VOJVQMHTX3sx).
2.  Выполните клонирование этого репозитория к себе на ПК с помощью команды git clone.
3.  Выполните домашнее задание и заполните у себя локально этот файл README.md:

*   впишите сверху название занятия, ваши фамилию и имя;
*   в каждом задании добавьте решение в требуемом виде — текст, код, скриншоты, ссылка.
*   для корректного добавления скриншотов используйте [инструкцию «Как вставить скриншот в шаблон с решением»](https://www.google.com/url?q=https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md&sa=D&source=editors&ust=1787045313896023&usg=AOvVaw0IzW-YMgurtjgWtoaJAYEw);
*   при оформлении используйте возможности языка разметки md. Коротко об этом можно посмотреть в [инструкции по MarkDown](https://www.google.com/url?q=https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md&sa=D&source=editors&ust=1787045313896407&usg=AOvVaw3ekihA1R7rNA_YesG6bML0).

4.  После завершения работы над домашним заданием сделайте коммит git commit -m "comment" и отправьте его на GitHub git push origin.
5.  Для проверки домашнего задания в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем GitHub.
6.  Любые вопросы по выполнению заданий задавайте в разделе «Вопросы по заданию» в личном кабинете.

Желаем успехов в выполнении домашнего задания!

* * *

### Задание 1

Что нужно сделать:

1.  Установите себе jenkins по инструкции из лекции или любым другим способом из официальной документации. Использовать Docker в этом задании нежелательно.
2.  Установите на машину с jenkins [golang](https://www.google.com/url?q=https://golang.org/doc/install&sa=D&source=editors&ust=1787045313897634&usg=AOvVaw0c1CPMyG_48XtyIND0hsJO).
3.  Используя свой аккаунт на GitHub, сделайте себе форк [репозитория](https://www.google.com/url?q=https://github.com/netology-code/sdvps-materials.git&sa=D&source=editors&ust=1787045313897871&usg=AOvVaw1EAVPKFhwiOMQPfVarA6-j). В этом же репозитории находится [дополнительный материал для выполнения ДЗ](https://www.google.com/url?q=https://github.com/netology-code/sdvps-materials/blob/main/CICD/8.2-hw.md&sa=D&source=editors&ust=1787045313898065&usg=AOvVaw0mj-qJEUKgtyBGPVIZEH3D).
4.  Создайте в jenkins Freestyle Project, подключите получившийся репозиторий к нему и произведите запуск тестов и сборку проекта go test . и docker build ..

В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.

### Задание 2

Что нужно сделать:

1.  Создайте новый проект pipeline.
2.  Перепишите сборку из задания 1 на declarative в виде кода.

В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.

### Задание 3

Что нужно сделать:

1.  Установите на машину Nexus.
2.  Создайте raw-hosted репозиторий.
3.  Измените pipeline так, чтобы вместо Docker-образа собирался бинарный go-файл. Команду можно скопировать из Dockerfile.
4.  Загрузите файл в репозиторий с помощью jenkins.

В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.

### Задание 4\*

Придумайте способ версионировать приложение, чтобы каждый следующий запуск сборки присваивал имени файла новую версию. Таким образом, в репозитории Nexus будет храниться история релизов.

Подсказка: используйте переменную BUILD\_NUMBER.

В качестве ответа пришлите скриншоты с настройками проекта и результатами выполнения сборки.

### Задание 1

version: '3.8'

services:

  jenkins:

    user: root

    image: jenkins/jenkins:lts-jdk17

    container\_name: jenkins

    restart: unless-stopped

    ports:

      - "8085:8080" # Веб-интерфейс Jenkins

      - "50000:50000" # Порт для подключения агентов (JNLP)

    volumes:

      - jenkins\_data:/var/jenkins\_home

      - /usr/local/go:/usr/local/go:ro

      - /var/run/docker.sock:/var/run/docker.sock

      - /usr/bin/docker:/usr/bin/docker

      - jenkins\_data:/var/jenkins\_home

      - ${SSH\_AUTH\_SOCK}:/run/ssh-agent

      - /usr/bin/git:/usr/bin/git:ro

      # Пробрасываем системные библиотеки и шаблоны Git (необходимы для работы):

      - /usr/share/git-core:/usr/share/git-core:ro

    environment:

      - TZ=Europe/Moscow # Настройка часового пояса (опционально)

      - SSH\_AUTH\_SOCK=/run/ssh-agent

    networks:

      - devops-net

  nexus:

    image: sonatype/nexus3

    container\_name: nexus

    restart: unless-stopped

    volumes:

      - "nexus-data:/sonatype-work"

    ports:

      - "8081:8081"

      - "8082:8082"

    networks:

      - devops-net

volumes:

  jenkins\_data:

  nexus-data:

networks:

  devops-net:

    driver: bridge

![](images/image2.png)

eval $(ssh-agent -s)

docker compose -f docker-compose-j-n.yml up -d

![](images/image23.png)

Настройка nexus

ip:

docker compose -f docker-compose-j-n.yml logs -f nexus

docker exec -it nexus cat /nexus-data/admin.password

![](images/image20.png)

![](images/image18.png)

![](images/image7.png)

Создадим свой репозиторий для докера

![](images/image11.png)

![](images/image12.png)

![](images/image22.png)

Настройка  jenkins

docker exec -it jenkins bash

![](images/image25.png)

![](images/image24.png)

![](images/image19.png)

![](images/image17.png)

/usr/local/go/bin/go test .

docker build . -t ubuntu-bionic:8082/hello-world:v$BUILD\_NUMBER

docker login ubuntu-bionic:8082 -u admin -p admin && docker push ubuntu -bionic:8082/hello-world:v$BUILD\_NUMBER && docker logout

![](images/image15.png)

ИНСТРУКЦИЯ ДЛЯ РУЧНОЙ УСТАНОВКИ, все прописано в docer-compose-j-n.yml устанавливать не нужно

ИНСТРУКЦИЯ ДЛЯ РУЧНОЙ УСТАНОВКИ go в контейнер

docker exec -it jenkins bash

apt update && apt install wget

wget [https://go.dev/dl/go1.17.5.linux-amd64.tar.gz](https://www.google.com/url?q=https://go.dev/dl/go1.17.5.linux-amd64.tar.gz&sa=D&source=editors&ust=1787045313906804&usg=AOvVaw298MkIKngLGsLPpdB7e0gt)

tar -C /usr/local -xzf [go1.17.5.linux-amd64.tar.gz](https://www.google.com/url?q=http://go1.17.5.linux-amd64.tar.gz&sa=D&source=editors&ust=1787045313907104&usg=AOvVaw3LpNV76Q28NEXY6vbGttxC)

echo 'export PATH=$PATH:/usr/local/go/bin' | tee -a /etc/profile

![](images/image16.png)

![](images/image14.png)

![](images/image6.png)

нужно прописать домен в хостовой машине

ubuntu-bionic 192.168.0.104

так же нужно поменять пароль в конфигурации на тот что указали при авторизации nexus

![](images/image9.png)

А так же что-то сделать с ssl

/etc/docker/daemon.json

Создадим необходимые директории и пропишем ВНУТРИ контейнера:

{ "insecure-registries" : \["ubuntu-bionic:8082"\]}

![](images/image13.png)

Конфиг на хосте

![](images/image3.png)

Удалить все не использованные образы

docker system prune -a --volumes

docker images

сделать копию образа для сохранения всех изменений

docker commit jenkins jenkins\_back

sudo dockerd --config-file /etc/docker/daemon.json --validate

sudo systemctl reload docker

![](images/image4.png)

Задание 2

![](images/image8.png)

![](images/image1.png)

ошибка:

![](images/image10.png)

нужно явно указать путь к go в пайплане

pipeline {

 agent any

 environment {

        // Добавляем путь к Go в начало системного PATH

        PATH = "/usr/local/go/bin:${env.PATH}"

        // Если приложению нужен настроенный GOPATH, можно раскомментировать строку ниже:

        // GOPATH = "${WORKSPACE}/go"

}

 stages {

  stage('Git') {

   steps {git 'https://github.com/Evgn1855/sdvps-materials.git'}

  }

  stage('Test') {

   steps {

    sh 'go test .'

   }

  }

  stage('Build') {

   steps {

    sh 'docker build . -t ubuntu-bionic:8082/hello-world:v$BUILD\_NUMBER'

   }

  }

  stage('Push') {

   steps {

    sh 'docker login ubuntu-bionic:8082 -u admin -p 12345678 && docker push ubuntu-bionic:8082/hello-world:v$BUILD\_NUMBER && docker logout'   }

  }

 }

}

![](images/image21.png)

Задание 3

![](images/image5.png)

pipeline {

 agent any

 environment {

    // Добавляем путь к Go в начало системного PATH

    PATH = "/usr/local/go/bin:${env.PATH}"

    // Если приложению нужен настроенный GOPATH, можно раскомментировать строку ниже:

    // GOPATH = "${WORKSPACE}/go"

  }

 stages {

    stage('Git') {

   steps {

//ветка main а не master

        checkout(\[$class: 'GitSCM',

          branches: \[\[name: '\*/main'\]\],

          userRemoteConfigs: \[\[url: 'https://github.com/Evgn1855/sdvps-materials.git'\]\]

        \])

      }

    }

    stage('Test') {

   steps {

    sh 'go test .'

      }

    }

    stage('Build') {

   steps {

    sh 'go build -o hello-world:v$BUILD\_NUMBER .'

    sh 'curl -u admin:12345678 http://192.168.0.104:8081/repository/my\_raw-hosted/ --upload-file hello-world:v$BUILD\_NUMBER'

      }

    }

  }
![](images/image555.png)
}

синтаксис go:

go build -o myapp [main.go](https://www.google.com/url?q=http://main.go&sa=D&source=editors&ust=1787045313914888&usg=AOvVaw17ZEh-Z3es9fWTw-lkXjaI) - сохранит программу под именем myapp
