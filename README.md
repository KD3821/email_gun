# email_service

<h1 align="center">Email Service</h1>
<p align="center"><img src="https://img.shields.io/badge/made_by-KD3821-lightblue"></p>

<b>Emailing customers used to be hard - NOT ANYMORE!</b><br>
<ul>
<li>
Set ENV with PG_PASSWORD:   export POSTGRES_PASSWORD=EmailApp123</li>
<li>
Run command: docker-compose -f docker-compose.yml up --build</li>
<li>
Create superuser inside backend container: docker exec -it email_backend /bin/bash (& then: python manage.py createsuperuser)</li>
<li>
Enter Django Admin and set 'IntervalSchedule' intervals for Celery Beat: 5, 10, 30 SECONDS (three intervals)</li>
<li>
Sing-up >> Login >> Add Customers >> Create Campaign >> Confirm Sending >> Check Campaign Details</li>
<li>
Enjoy using Service!</li></ul>


<p align="center"><img src="https://github.com/kd3821/email_service/blob/main/img/email_service.png?raw=true"></p>

<p align="center"><img src="https://github.com/kd3821/email_service/blob/main/img/celery_beat_intervals.png?raw=true"></p>