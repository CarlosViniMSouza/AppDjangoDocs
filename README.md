# Documentacao do Projeto:

## 1 - Iniciar Servidor: `python manage.py runserver`

## 2 - Migrar dados para o SQLite: `python manage.py migrate`

## 3 - Criar um SuperUser(ADM): `python manage.py createsuperuser`

```
Enter your desired username and press enter.

  >>> Username: admin

You will then be prompted for your desired email address:

  >>> Email address: admin@example.com

The final step is to enter your password. You will be asked to enter your password twice, the second time as a confirmation of the first.

  >>> Password: carlosvinimsouza
  >>> Password (again): carlosvinimsouza
  >>> Superuser created successfully.
```

## 4 - Rodar testes: `python manage.py test polls`