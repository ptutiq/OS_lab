# Лабораторная работа №5

## Задание

 #### На серверах web1, web2 установить Nginx.
 #### На серверах haproxy1, haproxy2 установить и настроить отказоустойчивую связку HAProxy+Keepalived. Настроить VIP с помощью Keepalived в соответствии со схемой
 #### На серверах web1, web2 Nginx должен работать по порту 8080 и отдавать кастомную страницу, зайдя на которую можно понять на каком сервере вы находитесь.
 #### На серверах с HAProxy ПО должно обеспечить балансировку нагрузки серверов web1 и web2 в режиме round-robin. Сделать таймауты ожидания ответа web1 и web2 как можно меньше. Скажем, 1-2 секунды
 #### Установка и настройка всего ПО должна быть обеспечена Ansible-сценарием.
 #### Все файлы по этому заданию выложить в Github и написать ReadMe со скринами работоспособности и инструкцию по запуску вашего Ansible-сценария.

## Как запустить playbook

Сначала уничтожить все то, что было сделано:

 > vagrant destroy --force

Далее поднять vagrant:

> vagrant up

Запустить playbook:

> ansible-playbook nginx.yml 

## Проверка балансировщика
### Всё работает
<a href="https://ibb.co/xFGSNk7"><img src="https://i.ibb.co/Y087xCL/2022-04-06-20-48-56.png" alt="2022-04-06-20-48-56" border="0"></a>

<a href="https://imgbb.com/"><img src="https://i.ibb.co/WsJmFJ5/2022-04-06-20-24-15.png" alt="2022-04-06-20-24-15" border="0"></a>


## Проверка отказоустойчивости
### Отключен haproxy1
<a href="https://imgbb.com/"><img src="https://i.ibb.co/6NQGLcB/2022-04-06-20-24-15.png" alt="2022-04-06-20-24-15" border="0"></a>

<a href="https://ibb.co/xFGSNk7"><img src="https://i.ibb.co/Y087xCL/2022-04-06-20-48-56.png" alt="2022-04-06-20-48-56" border="0"></a>

### Отключен haproxy2
<a href="https://ibb.co/pxq7nPT"><img src="https://i.ibb.co/ZV9jNJr/2022-04-06-20-26-06.png" alt="2022-04-06-20-26-06" border="0"></a>


<a href="https://ibb.co/xFGSNk7"><img src="https://i.ibb.co/Y087xCL/2022-04-06-20-48-56.png" alt="2022-04-06-20-48-56" border="0"></a>
