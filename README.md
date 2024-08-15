### Description

This project uses 
* [celery](https://pypi.org/project/celery/)
* [celery beat](https://pypi.org/project/django-celery-beat/)
* [celery results](https://pypi.org/project/django-celery-results/)

#### Start
* `docker compose up`                           # start redis
* `celery -A d_celery_beat worker -l INFO`      # start the worker
* `celery -A d_celery_beat beat -l INFO --scheduler django_celery_beat.schedulers.DatabaseScheduler`  # start beat
* start the app

#### URLs
* go to http://localhost:8000/ to run the task once
* go to http://localhost:8000/schedule to create and schedule the scheduled task
* go to http://localhost:8000/admin/django_celery_beat/periodictask/ to view the scheduled periodic tasks
* go to http://localhost:8000/admin/django_celery_results/taskresult/ to view the results of the task runs