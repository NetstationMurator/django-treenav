Dokumentacja techniczna 
======================

Informacje o aplikacji
----------------------
Treenav jest aplikacją ułatwiającą tworzenie rozwijalnych menu.

Wdrozone w projektach
---------------------

+-----------------+----------------+
| Nazwa projektu  | ticket Redmine |
+-----------------+----------------+
| TestV2          |                |
+-----------------+----------------+

Konfiguracja
------------

*perf/requirements.txt:*

.. code:: python

    -e git+https://github.com/NetstationMurator/django-treenav.git#egg=django_treenav
    FeinCMS==1.10.1

*settings.py:*

.. code:: python

    INSTALLED_APPS = [
    (...)
    'treenav',
    'mptt',
    ]

Django 1.7:

.. code:: python

    TEMPLATE_CONTEXT_PROCESSORS = (
        "django.core.context_processors.request",
        "treenav.context_processors.treenav_active",
    )

Django >=1.8:

.. code:: python

    TEMPLATES = [
    {
        'OPTIONS': {
            'context_processors': [
                "django.template.context_processors.request",
                "treenav.context_processors.treenav_active",
                ],
        },
    },
    ]

*urls.py:*

.. code:: python

    urlpatterns = [
        url(r'^treenav/', include('treenav.urls')),
    ]
