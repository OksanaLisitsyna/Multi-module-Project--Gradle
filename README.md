## Multi-module-Project--Gradle

В этом задании отрабатывался навык сборки проектов с помощью системы Gradle.
</br></br>


В проекте три модуля с разделением по функциональности:

* db - модуль работы с базой данных;
* api - модуль работы с web;
* service - слой сервисов.

Для решения задачи в каждой директории создаем **build.gradle**:
```
plugins {
    id 'java'
}

group 'ru.netology'
version '1.0-SNAPSHOT'

repositories {
    mavenCentral()
}

dependencies {

}
```

Чтобы подключить новые модули к проекту, добавляем в корне проекта в settings.gradle новые созданные модули:
```
include 'db'
include 'service'
include 'api'
```

Для подключения модуля db в модуль service добавим зависимость:
```
dependencies {
    implementation project(":db")
}
```

Для подключения модуля service в модуль api добавим зависимость:
```
dependencies {
    implementation project(":db")
    implementation project(":service")
}
```
