

# Установка докера в Debian 11

## Step 1

```
sudo apt update
```

```
sudo apt -y install ca-certificates curl gnupg lsb-release # Дополнительные пакеты, которые необходимы для работы с удалёнными репозиториями
```

```
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg # скачивание и добавление PGP ключа от репозитория Docker
```

```
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null # добавления репозитория Docker
```


- [ ] 
## Step 2

### УСТАНОВКА ПАКЕТОВ DOCKER

```
sudo apt update
```

```
sudo apt -y install docker-ce docker-ce-cli containerd.io
```
- [x] 
## Step 3

### ЗАПУСК И АВТОЗАГРУЗКА docker 

```
sudo systemctl start docker
```

```
sudo systemctl enable docker
```

### Добавление пользователя в группу DOCKER

```
sudo groupadd docker # Если группа не была создана автоматически
```

```
sudo usermod -aG docker $USER
```

### Install latest Compose on Debian 11

```
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

```
sudo chmod +x /usr/local/bin/docker-compose
```

```
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose # ПРИМЕЧАНИЕ . Этот шаг необходим только в том случае, если по какой-либо причине путь /usr/local/bin/docker-composeвызывает какие-либо проблемы, на которые вы всегда можете создать символическую ссылку /usr/bin
```


- [ ] 
Step 3 взят отсюда 
https://devcoops.com/install-docker-compose-on-debian-11/


