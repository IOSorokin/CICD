## 1.    Создайте новый проект в teamcity на основе fork.
   ![изображение](https://github.com/IOSorokin/CICD/assets/148979909/d06814c6-31cc-4c9b-8435-fb219a3f6bd1)

## 2.    Сделайте autodetect конфигурации.
  Определилась конфигурация maven 
  ![изображение](https://github.com/IOSorokin/CICD/assets/148979909/33d7fac8-f132-4cd8-9054-054a53c9c697)

## 3.    Сохраните необходимые шаги, запустите первую сборку master.
  Первая сборка запустилась 
  ![изображение](https://github.com/IOSorokin/CICD/assets/148979909/71d067e2-59c2-4644-b96d-272b1617b3a5)

## 4.    Поменяйте условия сборки: если сборка по ветке master, то должен происходит mvn clean deploy, иначе mvn clean test.
  Поменял условия сборки по ветке master видно что были изменения в файле
  ![изображение](https://github.com/IOSorokin/CICD/assets/148979909/0ff63d5d-1054-403b-bea2-512f488cacb7)

## 5.    Для deploy будет необходимо загрузить settings.xml в набор конфигураций maven у teamcity, предварительно записав туда креды для подключения к nexus.
   Загрузил файл конфигурации 
   ![изображение](https://github.com/IOSorokin/CICD/assets/148979909/17837d80-f325-4e31-84b2-3c69dee45e04)

## 6.    В pom.xml необходимо поменять ссылки на репозиторий и nexus.
   В pom файле поменял адрес nexus и номер сборки файл во вложении 
   
## 7.    Запустите сборку по master, убедитесь, что всё прошло успешно и артефакт появился в nexus.
   Сборка прошла успешно и артефакт появился в сборке Nexus 
   ![изображение](https://github.com/IOSorokin/CICD/assets/148979909/e36613f2-5f3c-4e76-bd23-1c13b5fc29ee)

## 8.    Мигрируйте build configuration в репозиторий.
   Мигрировал build configuration в свой репозиторий
   ![изображение](https://github.com/IOSorokin/CICD/assets/148979909/138d5f5d-507f-4775-aad6-5fbc7a35aac8)

## 9.    Создайте отдельную ветку feature/add_reply в репозитории.
   Создал новую ветку командой git branch feature/add_reply
   ![изображение](https://github.com/IOSorokin/CICD/assets/148979909/cf2d676f-12d3-4b80-9a9d-2b07a5580887)


## 10.    Напишите новый метод для класса Welcomer: метод должен возвращать произвольную реплику, содержащую слово hunter.
   Добавил новый метод класса Wecomer.java
   ```
package plaindoll;

public class Welcomer{
	public String sayWelcome() {
		return "Welcome home, good hunter. What is it your desire?";
	}
	public String sayFarewell() {
		return "Farewell, good hunter. May you find your worth in waking world.";
	}
	public String sayNeedGold(){
		return "Not enough gold";
	}
	public String saySome(){
		return "something in the way";
	}
	public String sayHunter(){
		return "There is a deer on the hunter's path"
	}
}
   ```

## 11.    Дополните тест для нового метода на поиск слова hunter в новой реплике.
   ![изображение](https://github.com/IOSorokin/CICD/assets/148979909/745c2662-e0d4-46e6-a062-4ae06fc46a89)

## 12.    Сделайте push всех изменений в новую ветку репозитория.
   Сделал
## 13.    Убедитесь, что сборка самостоятельно запустилась, тесты прошли успешно.
   Сборка запустилась автоматически и прошла успешно 
   ![изображение](https://github.com/IOSorokin/CICD/assets/148979909/267480d7-e60d-46be-b6a3-7c72aae5a4be)

## 14.    Внесите изменения из произвольной ветки feature/add_reply в master через Merge.
   Внес изменения в мастер через Merge

## 15.    Убедитесь, что нет собранного артефакта в сборке по ветке master.
   В сборке нет собранного артефакта:
   для того чтобы он появился необходимо изменить версию артефакта в pom.xml

## 16.    Настройте конфигурацию так, чтобы она собирала .jar в артефакты сборки.
   Перенастроил 
   
## 17.    Проведите повторную сборку мастера, убедитесь, что сбора прошла успешно и артефакты собраны.
   Сборка прошла успешно 
   ![изображение](https://github.com/IOSorokin/CICD/assets/148979909/e8960450-15b3-4e76-9246-add8a5f0516c)

   Артефакты собраны 
   ![изображение](https://github.com/IOSorokin/CICD/assets/148979909/f0158b64-dd59-4772-a70a-cc63121ab714)

## 18.    Проверьте, что конфигурация в репозитории содержит все настройки конфигурации из teamcity.
   Все настройки сохранены
   ![изображение](https://github.com/IOSorokin/CICD/assets/148979909/54969164-4a04-47ac-8812-bed2d5807e28)


## 19.    В ответе пришлите ссылку на репозиторий.
   https://github.com/IOSorokin/example-teamcity/
