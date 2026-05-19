# Задача 1: Запуск экземпляров приложения
- Запустил `docker run` и создал первый контейнер на примере `nginx:alpine`
- Создал `volume nginx-data`

<img width="1156" height="231" alt="image" src="https://github.com/user-attachments/assets/7d3731be-a733-400e-9a55-fad46aa641bd" />

- Запустил контейнер `nginx-volume` через флаг `-v` подключил том к контейнеру
- Вошел внутрь контейнера c помощью `docker exec -it` ввиду отсутствия `bash` использовал `ash`
- Проверил файл `index.html`

<img width="936" height="383" alt="image" src="https://github.com/user-attachments/assets/c77e48c0-e116-424a-ad14-ec6f4294497d" />

- Создал кастомную сеть типа сетевой мост `network create --driver bridge`

<img width="936" height="300" alt="image" src="https://github.com/user-attachments/assets/aabd8365-d6ba-49f5-b6c1-b8f76ddfb341" />

# Задача 2: Подключение томов и сети
-  Пересоздал оба контейнера с флагом `-v` для присоединения тома `(nginx-cont и nginx-cont2)` и указал обоим директорию монтирования `/logs`

<img width="1204" height="276" alt="image" src="https://github.com/user-attachments/assets/88e7b1b5-b8f5-4b93-a7bb-a24b0829f04c" />

- Подключился в оба контейнера и сделал `echo` с `nginx-cont` в `/logs/log.txt`
- Через `cat` в контейнере `nginx-cont2` увидел `echo` с первого контейнера

<img width="1204" height="488" alt="image" src="https://github.com/user-attachments/assets/26a722d9-f444-474a-8ceb-fa8832317252" />

- Остановил контейнеры и удалил их `docker stop и docker rm`
- Удалил образ `nginx:alpine`
- Немного запутался с удалением и остановкой `volume`, но все таки удалил нужно было через флаг `-v` - `(Немного каша в конце получилась на скриншоте последнем)`
- Удалил сеть `docker network rm`
- Очистил все `volume` которые не используются через `prune`

<img width="1204" height="713" alt="image" src="https://github.com/user-attachments/assets/0d167a9f-1859-4528-b262-b681df0dda57" />

  
