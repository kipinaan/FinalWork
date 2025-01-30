## Упаковать сервисы short_url и to_do в Docker-контейнеры, используя именованные Docker-тома для сохранения данных

1. Создаем тома:
   - `docker volume create todo_data`
   - `docker volume create shorturl_data`
  
2. Создаем докер-образ с именем и тэгом, контекст сборки - текущая директория:
   - `docker build -t to_do:latest .`
   -  `docker build -t short_url:latest .`

3. Привязываем ранее созданные тома к контейнерам:
   - `docker run -d -p 8000:80 -v todo_data:/app/data to_do:latest`
   - `docker run -d -p 8001:80 -v shorturl_data:/app/data short_url:latest`
  
4. **Результат:** контейнеры на Docker активны

![image](https://github.com/user-attachments/assets/23aba30d-8bec-4c1a-9135-78b272164eb1)

## TO-DO

1. Переходим в развернутый FastApi для сервиса to-do

![image](https://github.com/user-attachments/assets/b9dbe75f-2974-42b0-a806-dd9a43a1b347)

2. Раздел **default:**
   - GET /items
  ![image](https://github.com/user-attachments/assets/ca9b741f-adac-4f6c-9ae0-e7b070841c45)
   - POST /items
     ![image](https://github.com/user-attachments/assets/4ec176bd-a58b-42ad-aae9-b27c0786eba5)
   - GET /items/{item_id}
     ![image](https://github.com/user-attachments/assets/320e5700-631e-4595-9238-62f0370003b9)
   - PUT /items/{item_id}
     ![image](https://github.com/user-attachments/assets/485c3eda-a203-45a2-abe7-b7512fa8686d)
   - DELETE /items/{item_id}
     ![image](https://github.com/user-attachments/assets/5bfc98e7-702e-4364-bcef-aa0bdf984530)
3. Раздел **Schemas:**
   ![image](https://github.com/user-attachments/assets/b1bfdfd0-bbe1-49ba-b0ab-b0cec5aad091)

## SHORT_URL

1. Переходим в развернутый FastApi для сервиса short_url

![image](https://github.com/user-attachments/assets/2e0c2cb9-19ee-487d-ad0d-93674c31b900)

2. Раздел **default:**
   - POST /shorten
   ![image](https://github.com/user-attachments/assets/80756331-ac4a-4333-93b3-eb3f8402ed41)
   - GET /{short_id}
   ![image](https://github.com/user-attachments/assets/9d1a2fdc-4274-4f17-bd86-23626298a924)
   - GET /stats/{short_id}
   ![image](https://github.com/user-attachments/assets/85e39215-f1f8-4655-8cdc-7bdd170c6ab3)
3. Раздел **Schemas:**

![image](https://github.com/user-attachments/assets/80b16445-7f48-4ecb-9baf-7cde120a8335)
