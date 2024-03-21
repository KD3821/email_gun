# message_service

<h1 align="center">Message Service</h1>
<p align="center"><img src="https://img.shields.io/badge/made_by-KD3821-maroon"></p>

<p align="center"><b>Управляйте рассылками с MESSAGE SERVICE!</b></p><br>
<ul>
<li>
Создайте .env файл в папке 'email_app' на одном уровне вложенности с файлом manage.py (используйте пример из файла env.example)</li>
<li>
Перед запуском docker-compose из консоли установите пароль для БД в переменную среды командой: export POSTGRES_PASSWORD=EmailApp123 (пароль должен совпадать с паролем в .env файле)</li>
<li>
Также измените дефолтное значение таймаута для HTTP-соединения у контейнеров в момент сборки - из консоли запустите команду: export COMPOSE_HTTP_TIMEOUT=300 (300 сек. вместо 60 сек.)</li>
<li>
Запустите команду в консоли: docker-compose -f docker-compose.yml up --build (дождитесь завершения сборки сети контейнеров)</li>
<li>
Если по какой-то причине процесс остановился с ошибкой - вызовите команду из консоли: docker-compose down и дождитесь остановки. Затем повторите предыдущий шаг</li>
<li>
После завершения сборки сети нужно создать superuser для Django Admin в контейнере с приложением Django: docker exec -it email_backend /bin/bash (и далее: python manage.py createsuperuser)</li>
<li>
Авторизуйтесь в Django Admin ( http://127.0.0.1/admin ) и установите 'IntervalSchedule' для Celery Beat: 5, 10, 30 секунд (три интервала)</li>
<li>
Регистрируйтесь >> Входите в ЛК >> Добавляйте клиентов >> Создавайте рассылки >> Редактируйте и подтверждайте >> Проверяйте статус рассылки</li>
<li>
Если сообщение не будет отправлено с первого раза - повторная попытка произойдет через минимум 5 секунд. И так будет происходить пока не наступит таймаут - после первой попытки 60 секунд</li>
<li>
Если время окончания рассылки наступит раньше чем таймаут - попытки отправки сообщения будут остановлены</li>
<li>
Страница со Swagger-UI доступна по адресу: http://127.0.0.1/api/schema/swagger-ui/</li>
<li>
Страница с Redoc доступна по адресу: http://127.0.0.1/api/schema/redoc/</li>
<li>
Есть заготовка приложения с интеграцией со Stripe (реализована) и авторизацией по OAuth (частично реализована - сервис авторизации реализован на FastAPI & Vue.js)</li>
<li>
Вариант со Stripe + OAuth - https://github.com/KD3821/email_app/tree/oauth</li>
<li>
Сервис авторизации (DOLLAR SERVICE) на FastAPI - https://github.com/KD3821/dollar_app & минимальным фронтендом на Vue.js + Vuetify- https://github.com/KD3821/dollar_vue</li></ul>


<p align="center"><img src="https://github.com/kd3821/email_service/blob/main/img/edit_customer.png?raw=true"></p>

<p align="center"><img src="https://github.com/kd3821/email_service/blob/main/img/customer_list.png?raw=true"></p>

<p align="center"><img src="https://github.com/kd3821/email_service/blob/main/img/add_campaign.png?raw=true"></p>

<p align="center"><img src="https://github.com/kd3821/email_service/blob/main/img/campaign_list.png?raw=true"></p>

<p align="center"><img src="https://github.com/kd3821/email_service/blob/main/img/email_service.png?raw=true"></p>

<p align="center"><img src="https://github.com/kd3821/email_service/blob/main/img/email_service_done.png?raw=true"></p>

<p align="center"><img src="https://github.com/kd3821/email_service/blob/main/img/schema_swagger_ui.png?raw=true"></p>

<p align="center"><img src="https://github.com/kd3821/email_service/blob/main/img/celery_beat_intervals.png?raw=true"></p>

<p align="center"><img src="https://github.com/kd3821/email_service/blob/main/img/oauth_service.png?raw=true"></p>