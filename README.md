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


Устанавливаем утилиту curl с помощью команды

`sudo yum install curl`

![image](https://github.com/user-attachments/assets/a1782e15-d15b-4f52-9e52-c970162e792c)


При помощи команды `sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo`
выкачиваем репозиторий для linux centos

![image](https://github.com/user-attachments/assets/7adce59d-f163-41a8-8d8f-b9bbca5cc023)

Устанавливаем докер

`sudo yum install docker-ce docker-ce-cli containerd.io`

![image](https://github.com/user-attachments/assets/8796262b-0a04-4310-8fe5-311d14d044e3)
![image](https://github.com/user-attachments/assets/3fddff65-124b-4501-a1c9-e7f1a3534480)

Запускаем его и разрешаем автозапуск

`sudo systemctl enable docker --now`

![image](https://github.com/user-attachments/assets/0c14a4e8-fd80-4d3f-9d59-84cac7f5bb0f)


