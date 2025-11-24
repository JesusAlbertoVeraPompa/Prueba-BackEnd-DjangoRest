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

Agregamos el CORD en settings.py
# Apps del proyecto
INSTALLED_APPS = [
# CORS primero en apps
'corsheaders',

Agregamos tambien  en settings.py
# DRF
'rest_framework',
# App de dominio
'empleados',

Agregamos Tambien  en settings.py
MIDDLEWARE = [
# CORS debe ir lo más arriba posible y ANTES de SecurityMiddleware
'corsheaders.middleware.CorsMiddleware',

Agregamos al final en settings.py
# --- Django REST Framework ---
# Sin autenticación y sin permisos restrictivos (API abierta en dev)
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [],
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.AllowAny',
    ],
    # Render/parse JSON por defecto
    'DEFAULT_RENDERER_CLASSES': [
        'rest_framework.renderers.JSONRenderer',
    ],
    'DEFAULT_PARSER_CLASSES': [
        'rest_framework.parsers.JSONParser',
    ],
}
# --- CORS ---
CORS_ALLOWED_ORIGINS = [
    "http://localhost:5173",  # React (Vite)
]
# (Opcional) Métodos permitidos explícitos (por claridad)
CORS_ALLOW_METHODS = [
    "GET",
    "POST",
    "PUT",
    "PATCH",
    "DELETE",
    "OPTIONS",
]


