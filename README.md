# Домашнее задание к занятию "10.04. ELK"

## Дополнительные ссылки
<details>
При выполнении задания пользуйтесь вспомогательными ресурсами:

- [поднимаем elk в докер](https://www.elastic.co/guide/en/elastic-stack-get-started/current/get-started-docker.html)
- [поднимаем elk в докер с filebeat и докер логами](https://www.sarulabs.com/post/5/2019-08-12/sending-docker-logs-to-elasticsearch-and-kibana-with-filebeat.html)
- [конфигурируем logstash](https://www.elastic.co/guide/en/logstash/current/configuration.html)
- [плагины filter для logstash](https://www.elastic.co/guide/en/logstash/current/filter-plugins.html)
- [конфигурируем filebeat](https://www.elastic.co/guide/en/beats/libbeat/5.3/config-file-format.html)
- [привязываем индексы из elastic в kibana](https://www.elastic.co/guide/en/kibana/current/index-patterns.html)
- [как просматривать логи в kibana](https://www.elastic.co/guide/en/kibana/current/discover.html)
- [решение ошибки increase vm.max_map_count elasticsearch](https://stackoverflow.com/questions/42889241/how-to-increase-vm-max-map-count)

В процессе выполнения задания могут возникнуть также не указанные тут проблемы в зависимости от системы.

Используйте output stdout filebeat/kibana и api elasticsearch для изучения корня проблемы и ее устранения.
</details>

---
## Задание повышенной сложности

Не используйте директорию [help](./help) при выполнении домашнего задания.  

---
## Задание 1

Вам необходимо поднять в докере:
- elasticsearch(hot и warm ноды)
- logstash
- kibana
- filebeat

и связать их между собой.

Logstash следует сконфигурировать для приёма по tcp json сообщений.

Filebeat следует сконфигурировать для отправки логов docker вашей системы в logstash.

В директории [help](./help) находится манифест docker-compose и конфигурации filebeat/logstash для быстрого 
выполнения данного задания.

Результатом выполнения данного задания должны быть:  
- скриншот `docker ps` через 5 минут после старта всех контейнеров (их должно быть 5)
- скриншот интерфейса kibana
- docker-compose манифест (если вы не использовали директорию help)
- ваши yml конфигурации для стека (если вы не использовали директорию help)  
  
### Ответ:
<details>
    <summary style="font-size:14px">Развернуть</summary>

![изображение](https://user-images.githubusercontent.com/93001155/181102539-4014a933-a9e5-4363-930d-97818af55465.png)


![изображение](https://user-images.githubusercontent.com/93001155/181102606-74070add-b226-48c5-aa4a-0205fe75c6ee.png)


  Конфигурация доступна в папке [src](./src/). Были внесены незначительные изменения в предложенный вариант.


</details>


---
## Задание 2

Перейдите в меню [создания index-patterns  в kibana](http://localhost:5601/app/management/kibana/indexPatterns/create)
и создайте несколько index-patterns из имеющихся.

Перейдите в меню просмотра логов в kibana (Discover) и самостоятельно изучите как отображаются логи и как производить 
поиск по логам.

В манифесте директории help также приведенно dummy приложение, которое генерирует рандомные события в stdout контейнера.
Данные логи должны порождать индекс logstash-* в elasticsearch. Если данного индекса нет - воспользуйтесь советами 
и источниками из раздела "Дополнительные ссылки" данного ДЗ.

### Ответ:
<details>
    <summary style="font-size:14px">Развернуть</summary>

![изображение](https://user-images.githubusercontent.com/93001155/181102893-139c0977-aa9b-4015-b1c7-2d9b67b85b07.png)
![изображение](https://user-images.githubusercontent.com/93001155/181102982-d37bf73a-9f00-4085-b942-114eb089419f.png)
![изображение](https://user-images.githubusercontent.com/93001155/181103194-38db3f13-30dc-4929-b567-11ae170802e5.png)
</details>
 
---



 
