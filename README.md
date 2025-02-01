# Агутина Анастасия К-ИСП-39-1

Вводим команду для установки wget.

`sudo yum install wget`

![image](https://github.com/user-attachments/assets/f9d01689-0387-4c2e-b300-f493344b2427)

Выдает ошибку is not in the sudoers file.
Переключаемся на учетную запись root с помощью команды 

`su root`

Открываем файл sudoers с помощью команды 

`vi /etc/sudoers/`

![image](https://github.com/user-attachments/assets/87d3788b-2824-48c8-ba3c-fd7dcc2b1b0d)

Редактируем файл sudoers, добавляем пользователя agutina в список пользователей с правами sudo.
Устанавливаем wget

![image](https://github.com/user-attachments/assets/01295080-6039-4eaa-b717-2eb899863efc)
