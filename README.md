# email_service

<h1 align="center">Email Service</h1>
<p align="center"><img src="https://img.shields.io/badge/made_by-KD3821-maroon"></p>

<p align="center"><b>Emailing customers used to be hard - IT'S NOT ANYMORE!</b></p><br>
<ul>
<li>
Set ENV with PG_PASSWORD: export POSTGRES_PASSWORD=EmailApp123</li>
<li>
Run command: docker-compose -f docker-compose.yml up --build</li>
<li>
Create superuser inside backend container: docker exec -it email_backend /bin/bash (& then: python manage.py createsuperuser)</li>
<li>
Enter Django Admin ( http://127.0.0.1/admin ) and set 'IntervalSchedule' intervals for Celery Beat: 5, 10, 30 SECONDS (three intervals)</li>
<li>
Sing-up >> Login >> Add Customers >> Create Campaign >> Confirm Sending >> Check Campaign Details</li>
<li>
If message is not sent successfully then service will queue message for sending and will retry sending every 5 seconds</li>
<li>
If campaign is outdated or canceled by Admin then service will stop sending campaign's messages</li>
<li>
Swagger-UI page (DRF-Spectacular): http://127.0.0.1/api/schema/swagger-ui/</li>
<li>
If integration with Authorization Service (OAuth) is needed then check the 'accounts' app of Django for token models, middleware & permissions</li>
<li></ul>


<p align="center"><img src="https://github.com/kd3821/email_service/blob/main/img/edit_customer.png?raw=true"></p>

<p align="center"><img src="https://github.com/kd3821/email_service/blob/main/img/customer_list.png?raw=true"></p>

<p align="center"><img src="https://github.com/kd3821/email_service/blob/main/img/add_campaign.png?raw=true"></p>

<p align="center"><img src="https://github.com/kd3821/email_service/blob/main/img/campaign_list.png?raw=true"></p>

<p align="center"><img src="https://github.com/kd3821/email_service/blob/main/img/email_service.png?raw=true"></p>

<p align="center"><img src="https://github.com/kd3821/email_service/blob/main/img/schema_swagger_ui.png?raw=true"></p>

<p align="center"><img src="https://github.com/kd3821/email_service/blob/main/img/celery_beat_intervals.png?raw=true"></p>