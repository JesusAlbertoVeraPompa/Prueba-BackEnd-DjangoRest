Pasos para Empezar un proyecto BackEnd Django

Crea el entorno virtual:
python -m venv venv

Activamos el venv
venv\Scripts\activate

Actualizar pip:
python -m pip install --upgrade pip

Instalar la dependencia de Django:
pip install django djangorestframework pymysql django-cors-headers

Creamos el Proyecto
django-admin startproject rh_django .

Creamos la Aplicacion
python manage.py startapp empleados