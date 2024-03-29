## Задача

* Создать VPS с помощью Terraform
* Написать playbook для установки nginx, чтобы в нем использовалось несколько переменых в файле nginx.conf, т.е. вам надо параметризировать данный конфигурационный файл, что бы в зависимости от знавения переменных, генерировался разный результат и параметризировать конфигурационные файлы для двух виртуал-хостов

## Предпосылки

* Установить terraform
* Установить Go 1.13 (to build the provider plugin)
* Собрать плагин terraform для vscale
* Установить ansible https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

## Развертывание

* Конфигурируем main.tf (создаем ресурс в Vscale и запускаем средствами terraform  ansible-playbook)
* Выносим описание variables  в отдельный файл variables.tf
* Описываем в фале outputs.tf выводимые значения
* Переменные объявляем в файле terraform.tfvars (В файле объявляем токен, имя образа, Id дата-центра,secret_key, access_key для AWS, регион для AWS)
* В файле terraform.tfvars.sample описано назначение переменных
* Конфигурируем playbook для  установки кастомного  nginx на 80 порте
* Выносим значения переменных в group_vars
* Используемые переменные должны иметь несколько значений и перебираться в конструкции {% for item in items %} или подобной

## Подключаемся по ssh.

* ssh root@31.184.252.46

## Проверяем подключение по 80 порту к виртуальным хостам 

*  curl site1.example.com
*  curl site2.example.com


## Авторы

  - Sergey Babanin https://gitlab.rebrainme.com/babaninsergey

