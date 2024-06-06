# SysAdm

### Zabbix БД PostgreSQL. Выбор технологии решения обоснуйте.**  


**Обоснование выбора**: В контексте системы мониторинга Zabbix, PostgreSQL может быть использована как дополнительное хранилище для сохранения метрик на более длительный срок. Это позволяет хранить большое количество данных и обеспечивает возможность анализа и отчетности по метрикам за длительный период времени. Система мониторинга Zabbix является более традиционным инструментом, который лучше подходит для мониторинга инфраструктуры и серверов, являясь всеобще принятым стандартом в организациях.
## **CLI**
Меняем значение в файле
```
nano /etc/php/7.4/apache2-mod_php/php.ini
```
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/42eda88f-3429-4b5c-bab3-6a919cc03d73)  
```
systemctl start --now httpd2.service
systemctl enable httpd2.service
```

В окне браузера переходим по адресу: **http://localhost/zabbix/setup.php**
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/d945e049-9a08-4d14-8b3d-58606eb9e9e3)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/e932df06-db77-4978-9f4a-5210f09e256c)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/5901e712-a4f5-4a60-86cd-fc7a60cf9c1b)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/2b8dff21-9dc5-42da-991e-4fa09e552a36)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/ddb21b6e-1a8f-435f-a6a5-d1223762b0aa)  
Далее появится окно, в котором потребуется сохранить файл конфигурации и в ручную перенести его в необходимую папку:
```
cp /home/user/Загрузки/zabbix.conf.php /var/www/webapps/zabbix/ui/conf/
```
После необходимо "Finish".
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/6460b520-3ef1-488f-b83d-91f6a263be11)  
Установка завершена.

б. Произведите разграничение доступа к панели управления системы мониторинга путём создания отдельной учётной записи в соответствии с таблицей 1.
**Таблица №1**
| Учётная запись | Пароль | 
| :---         |     ---:      | 
| AdminMonitoring   | P@ssw0rd!     |  

После авторизации в панели администрирования - создадим пользователя:
## **CLI**

![image](https://github.com/NyashMan/DEMO2024/assets/1348639/6b51d7c8-c45d-464c-986f-8b26a2c4547b)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/a98a2ea0-35c5-4a54-8b1d-94570f347362)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/a5d04fd4-e45a-4368-afdf-556baf8d94b6)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/5fbafe46-5708-4d8b-bbc9-efaa45d8caad)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/2d1677ac-7a10-4810-9748-021b5b74fa9a)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/de5ea380-f6ba-4ae5-ac78-e80b00ec29ac)  

в. Произвести настройку агента мониторинга центрального узла сети – ISP.

## **ISP**
```
nano /etc/zabbix/zabbix_agentd.conf
```
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/e66dd889-773a-48cf-a975-4b3897656d3b)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/95ad12bd-d3e3-467e-9187-467f91cdacee)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/345597c6-7918-4500-9a61-3d27ca490c6f)  

```
systemctl start --now zabbix_agentd.service
systemctl enable zabbix_agentd.service
```

г. Произведите настройку правил проверки узла мониторинга на доступность с использованием протокола ICMP.

## **CLI**  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/2801bb0b-c28f-4616-b452-807eba15a720)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/2f0285e8-c2ed-4964-b92d-14375eaddd20)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/7cee221c-a4ec-49f8-b623-1ac9298c5241)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/a41b1dd5-6e8f-40f1-8cb6-96a199aac736)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/63501779-5b99-481c-aaa6-121a2247130d)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/720ee50a-7544-476d-9a83-cae4fa74b110)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/66497307-9fba-4e1a-b496-24c5bc4a1d33)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/1e732a5a-c628-46ed-a702-ed0e040800f8)  
**P.S. обращаю внимание, что агент поднимается не моментально, а в течении нескольких минут!**

д. Осуществите проверку доступности узлов мониторинга на сервере, оформите отчёт с результатами проверки.

## **CLI**
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/53656215-c2d8-4994-be33-7e72f57996f0)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/a2ea25fc-2afc-43d1-b660-4cefbeec01e4)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/38dea2e6-1127-49be-9875-25bac8dae780)  
![image](https://github.com/NyashMan/DEMO2024/assets/1348639/426de2d1-00bb-48d2-91eb-0f2fefa2024d)  

**Отчёт:** 
Проверка доступности нового узла мониторинга ISP показала следующие результаты: узел доступен, связь стабильна. Всего было отправлено три пакета, при этом их потеря составила 0%. 
К отчёту прилагается скриншот, подтверждающий успешную отправку ICMP-запросов.
