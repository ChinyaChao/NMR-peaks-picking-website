# NMR-peaks-picking-website
=============
Peaks-Picking
=============

Peaks-picking is a Django webpage to conduct Web-based peaks picking.

Quick start
-----------
1. Check pip is installed::

    pip --version

2. If pip isn’t already installed, then first try to bootstrap it from the standard library::

    python3 -m ensurepip --default-pip

3. Ensure vitualenv, pip, setuptools, and wheel are up to date::

    pip install virtualenv
    python3 -m pip install --upgrade pip setuptools wheel

4. Optionally, create a virtual environment::

    python3 -m venv peaks-picking
    source peaks-picking/bin/activate

5. Change into the outer directory and install Django::

    cd peaks-picking
    pip install django

6. If this is your first time using Django, you’ll have to take care of some initial setup::

    django-admin startproject trydjango

7. Install the package::

    cd tridjango
    python3 -m pip install --extra-index-url https://test.pypi.org/simple/ peaks-picking -t .

8. Add "NMR" to your INSTALLED_APPS in trydjango/setting like this::

    path = os.path.join(BASE_DIR, 'NMR')
    MEDIA_ROOT = os.path.join(path, 'media')
    MEDIA_URL = "/media/"
    INSTALLED_APPS = [
        ...
        'NMR',
        'django_cleanup'
    ]

9. Include the polls URLconf in your trydjango/urls.py like this, be careful with the QUOTATION marks::

    from django.urls import include
    urlpatterns = [
        ...
        path('NMR/', include('NMR.urls')), 
    ]

10. Run the following to create the NMR models and admin user:

    python3 manage.py migrate
    python3 manage.py createsuperuser

11. Run the following commands to connect to the server:

    python3 manage.py runserver

12. Start the development server and visit http://127.0.0.1:8000/admin/ to create a spectrum (you'll need the Admin app enabled).

13. Visit http://127.0.0.1:8000/NMR/ to start the peaks picking.
