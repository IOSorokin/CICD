# Знакомоство с SonarQube
## Основная часть

### 1.    Создайте новый проект, название произвольное.
  Создал новый проект CICD
  ![изображение](https://github.com/IOSorokin/CICD/assets/148979909/b97f6654-d8d3-4560-94c0-8ccd7194a55b)

### 2.    Скачайте пакет sonar-scanner, который вам предлагает скачать SonarQube.
  Скачал пакет sonar-scanner
  ![изображение](https://github.com/IOSorokin/CICD/assets/148979909/c0ecb857-aeef-4107-845d-e3a0ec030cc3)
  Далее распаковал его

### 3.    Сделайте так, чтобы binary был доступен через вызов в shell (или поменяйте переменную PATH, или любой другой, удобный вам способ).
  Добавил временную переменную PATH
  root@dev:/tmp/sonar-scanner-5.0.1.3006-linux/bin# export PATH=$(pwd):$PATH

### 4.    Проверьте sonar-scanner --version.
  Проверено
```
root@dev:/home/isadm/CICD/03/example# sonar-scanner -v
INFO: Scanner configuration file: /tmp/sonar-scanner-5.0.1.3006-linux/conf/sonar-scanner.properties
INFO: Project root configuration file: NONE
INFO: SonarScanner 5.0.1.3006
INFO: Java 17.0.7 Eclipse Adoptium (64-bit)
INFO: Linux 6.5.0-17-generic amd64
```

### 5.    Запустите анализатор против кода из директории example с дополнительным ключом -Dsonar.coverage.exclusions=fail.py.
  Анализатор запущен 
```
sonar-scanner \
  -Dsonar.projectKey=CICD \
  -Dsonar.sources=. \
  -Dsonar.host.url=http://178.154.203.250:9000 \
  -Dsonar.login=115b8a8adc5db596cef953702a9ba69b2250a466 \
  -Dsonar.coverage.exclusions=fail.py
```
### 6.    Посмотрите результат в интерфейсе.
  После обработки вывод следующего результата
  ![изображение](https://github.com/IOSorokin/CICD/assets/148979909/f54fa1d9-69cd-41aa-b98a-6f72984672d7)

### 7.    Исправьте ошибки, которые он выявил, включая warnings.
  Ошибки исправлены
```
def increment(index=1):
    index += 1
    return index
def get_square(numb):
    return numb*numb
def print_numb(numb):
    print("Number is {}".format(numb))

index = 0
while (index < 10):
    index = increment(index)
    print(get_square(index))
```

### 8.    Запустите анализатор повторно — проверьте, что QG пройдены успешно.
   Запустил, после проверки 
   ![изображение](https://github.com/IOSorokin/CICD/assets/148979909/37049ef4-7d7e-43ff-912f-808fb78acfce)

### 9.    Сделайте скриншот успешного прохождения анализа, приложите к решению ДЗ.
  Скриншот выше.

# Знакомство с Nexus
  ## Основная часть

   ### 1. В репозиторий maven-public загрузите артефакт с GAV-параметрами:
Загрузил артефакт с указанными параметрами ниже.
    groupId: netology;
    artifactId: java;
    version: 8_282;
    version: 8_102;
    classifier: distrib;
    type: tar.gz.

### 3. Проверьте, что все файлы загрузились успешно.
Файлы загрузились успешно: 
![изображение](https://github.com/IOSorokin/CICD/assets/148979909/2135f977-9144-4352-b3db-cfcbd55d511b)


### 4. В ответе пришлите файл maven-metadata.xml для этого артефекта.
Файлы загужены в моем репозитории Github



Знакомство с Maven
Подготовка к выполнению

    Скачайте дистрибутив с maven.
    Разархивируйте, сделайте так, чтобы binary был доступен через вызов в shell (или поменяйте переменную PATH, или любой другой, удобный вам способ).
    Удалите из apache-maven-<version>/conf/settings.xml упоминание о правиле, отвергающем HTTP- соединение — раздел mirrors —> id: my-repository-http-unblocker.
    Проверьте mvn --version.
    Заберите директорию mvn с pom.

Основная часть

    Поменяйте в pom.xml блок с зависимостями под ваш артефакт из первого пункта задания для Nexus (java с версией 8_282).
    Запустите команду mvn package в директории с pom.xml, ожидайте успешного окончания.
    Проверьте директорию ~/.m2/repository/, найдите ваш артефакт.
    В ответе пришлите исправленный файл pom.xml.

