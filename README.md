# Тестовое задание Software Engineer(Ruby On Rails)

## Цель
Мы хотим получить бекенд для построения различных приложений: веб или мобильных.

Разработать API для учебного портала, используя возможности Ruby On Rails.
## Описание приложения

В приложении есть пользователи и факультативы.

В приложении можно создавать новых пользователей.

Пользователи могу записываться на факультативные занятия.

Один пользователь может быть подписан на много факультативов.

У факультатива есть связь с учителем, который ведет этот факультатив.

В приложении должна быть реализована ролевая модель:

* Пользователь может иметь одну из трех ролей: Ученик, Учитель, Родитель.
* Создавать новых пользовательей может только пользователь с ролью учитель. 
* При создании ученика необходимо указать родителя.
* Записываться на факультативы могут только пользователи с ролью Ученик.
* Родители имеют доступ к информации, которая относится только к их детям.
* Ученики имеют доступ к информации, которая относится только к пользователем с ролью ученик и учитель.
* Учителя имеют доступ к информации о всех пользователях независимо от роли.

Пользователь должен пройти процесс авторизации используя email и пароль. Неавторизованный пользователь не имеет доступа к методам API и должен получать ошибку при попытке это сделать.

Схема исходных данных

```
Пользователь(
  id
  email
  name
  role
  password
)

Факультатив(
  id
  title
  description
  teacher
)
```

Нужно реализовать API методы, которые позволят

- авторизовываться пользователям используя email и пароль
- создавать новых пользователей
- получить информацию по одному пользователю с проверкой прав доступа к этому пользователю в зависимости от роли текущего пользователя. В ответе должны быть name, email, role и список факультативов на которые он записался.
- показать список факультативов, на которые записался ученик, с проверкой прав доступа к информации об этом ученике в зависимости от роли текущего пользователя.
- показать список всех имеющихся факультативов
- метод, который создает подписку пользователя на факультатив
- метод поиска популярных факультативов по частичному совпадению поля title. На вход метода приходит строка term. Метод возвращает факультативы, в которых term является подстрокой title факультатива. Метод возвращает список факультативов, отсортированных по популярности: от большей к меньшей. Популярность определяется так: чем больше учеников подписано на факультатив, тем он популярней

## Технические требования

- Ruby On Rails > 5.0
- PostgreSQL
- ActiveRecord
- Docker

На выходе должен получиться проект на [Github.com](http://github.com/) с инструкцией по запуску в README.md. Приложение должно запускаться в Docker

## Будет большим плюсом

- Покрыть функциональность API сервера тестами.(rspec или mini test)

## После выполнения

- Ты использовал какие-то дополнительные библиотеки? Если да, то зачем?
- Сколько времени заняло выполнение тестового задания?
- Если бы нужно было вывести этот проект в продакшен, что бы ты улучшил?
- Как тебе наше тестовое задание? Мы будем рады любому фидбеку
