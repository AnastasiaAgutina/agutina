# Агутина Анастасия К-ИСП-39-1

Вводим команду для установки wget.

`sudo yum install wget`

![image](https://github.com/user-attachments/assets/f9d01689-0387-4c2e-b300-f493344b2427)

Выдает ошибку is not in the sudoers file.
Переключаемся на учетную запись root с помощью команды 

`su root`

Открываем файл sudoers с помощью команды 

`vi /etc/sudoers`

![image](https://github.com/user-attachments/assets/87d3788b-2824-48c8-ba3c-fd7dcc2b1b0d)

Редактируем файл sudoers, добавляем пользователя agutina в список пользователей с правами sudo.
Устанавливаем wget

![image](https://github.com/user-attachments/assets/01295080-6039-4eaa-b717-2eb899863efc)


Устанавливаем утилиту curl с помощью команды

`sudo yum install curl`

![image](https://github.com/user-attachments/assets/a1782e15-d15b-4f52-9e52-c970162e792c)


При помощи команды 

`sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo`

выкачиваем репозиторий для linux centos

![image](https://github.com/user-attachments/assets/7adce59d-f163-41a8-8d8f-b9bbca5cc023)

Устанавливаем докер

`sudo yum install docker-ce docker-ce-cli containerd.io`

![image](https://github.com/user-attachments/assets/8796262b-0a04-4310-8fe5-311d14d044e3)
![image](https://github.com/user-attachments/assets/3fddff65-124b-4501-a1c9-e7f1a3534480)

Запускаем его и разрешаем автозапуск

`sudo systemctl enable docker --now`

![image](https://github.com/user-attachments/assets/0c14a4e8-fd80-4d3f-9d59-84cac7f5bb0f)

Объявление переменной COMVER, полученной в результате curl запроса, хранящей в себе номер последней версии Docker Compose

`COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)`

![image](https://github.com/user-attachments/assets/ba3f98e9-693f-4653-9f17-0b34006c930a)

Теперь скачиваем скрипт docker-compose последней версии, используя объявленную ранее переменную и помещаем его в каталог /usr/bin

`sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose`

![image](https://github.com/user-attachments/assets/d54c3842-ce76-4a15-ae45-9e98c445d747)


Команда chmod +x используется для предоставления прав на выполнение скачанному скрипту docker-compose.

`sudo chmod +x /usr/bin/docker-compose`

![image](https://github.com/user-attachments/assets/ff4cad3f-56ae-4667-9bfe-6c57beb7b162)

Выполняется команда для проверки установленной версии Docker Compose.

`docker-compose --version`

![image](https://github.com/user-attachments/assets/8c2d72bc-4998-41e2-b3a7-23536a0e811f)

Клонирование репозитория с GitHub:
 - Пытается выполнить команду git clone для клонирования репозитория grafana_stack_for_docker с GitHub.
 - Обнаружено, что команда git не установлена в системе. Предлагается установить пакет git-core, который предоставляет команду git.

`git clone https://github.com/skl256/grafana_stack_for_docker.git`

![image](https://github.com/user-attachments/assets/53a99315-4e5d-4805-b416-9cd7f50648f9)

`sudo yum install git`

![image](https://github.com/user-attachments/assets/840f97a4-ba71-426e-94d9-4298c9fa6f0e)
![image](https://github.com/user-attachments/assets/c0f7ba3c-611b-41cb-8b9c-f6d56d20db3f)

`git clone https://github.com/skl256/grafana_stack_for_docker.git`

![image](https://github.com/user-attachments/assets/dd405b1e-75b0-425b-93a9-0b5abbd882dc)

`cd grafana_stack_for_docker`

`sudo mkdir -p /mnt/common_volume/swarm/grafana/config`

`sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data}`

`sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana}`

`touch /mnt/common_volume/grafana/grafana-config/grafana.ini`

`cp config/* /mnt/common_volume/swarm/grafana/config/`

`mv grafana.yaml docker-compose.yaml`

![image](https://github.com/user-attachments/assets/20eb4690-b564-40f7-8acc-63e257f5d1b8)

`sudo docker compose up -d`

![image](https://github.com/user-attachments/assets/583dcef3-151b-4da3-a877-b83747261e17)

