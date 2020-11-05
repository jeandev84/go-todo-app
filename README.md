# REST API
``Это не более чем архитектурный подход к построению Веб приложений, которые общаются по протоколу HTTP``

# CRUD (CREAD, READ, UPDATE, DELETE)
Для каждого этого метода используем HTTP Методы
GET        - получение
POST       - Добавление 
PUT/PATCH  - Модификация
DELETE     - Удаление

1. Получение данных

2. Добавление данных

3. Модификация данных

4. Удаление данных

# GIT
``…or create a new repository on the command line``
``echo "# go-todo-app" >> README.md``
``git init``
``git add README.md``
``git commit -m "first commit"``
``git branch -M main``
``git remote add origin https://github.com/jeandev84/go-todo-app.git``
``git push -u origin main``
                
``…or push an existing repository from the command line``
``git remote add origin https://github.com/jeandev84/go-todo-app.git``
``git branch -M main``
``git push -u origin main``
``…or import code from another repository``
``You can initialize this repository with code from a Subversion, Mercurial, or TFS project.``


# СТРУКТУРА API

POST /AUTH/SIGN-UP
POST /AUTH/SIGN-IN


GET /LISTS
GET /LISTS/{ID}
POST /LISTS
PUT /LISTS/{ID}
DELETE /LISTS/{ID}
GET /LISTS/{ID}/ITEMS
POST /LISTS/{ID}/ITEMS


# СТРУКТУРА БД
(Realtion ManyToMany)
# TABLES
``users_lists``
id integer       (not null)
user_id interger (not null)
list_id integer  (not null)


``list_items: ``
id integer        (not null)
list_id integer   (not null)
item_id integer   (not null)


``users : Пользователи``
id integer (not null)
name varchar(255)   (not null)
username varchar(255)   (not null)
password_hash varchar(255)   (not null)

``todo_list : TODO списки``
id integer (not null)
title varchar(255) (not null)
description varchar(255) (not null)


``todo_item : Элементы список (задачи)`` 
id integer (not null)
title varchar(255) (not null)
description varchar(255) (not null)
done boolean (not null)


# CREATE PROJECT
$ mkdir todo-app
$ cd todo-app
todo-app$ go mod init github.com/zhashkevych/todo-app

$ git init
$ git add .
$ git commit -m "initial projet"
$ git push origin master

# PACKAGES
``Framework for working with HTTP``
todo-app$ go get -u github.com/gin-gonic/gin

# RESOURCE UNCLE BOB
``https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html``


# ГИБКИЕ И МАСШТАБИРУЕМЫЕ СИСТЕМЫ:
``Позволяют безболезненно менять фреймворки и инфраструктурные элементы``

``Имеют возможность изолированно тестировать каждый слой системы без зависимостей``

``Не зависят от реализации пользовательского интерфейса``

``Бизнес логика не зависит от конкретного выбора базы данных или других технических решений системы``

# Правило DEPENDENCY INJECTION (Внедрение зависимостей)

struct BlogPostSaver {
    storage Storage
}


func NewBlogPostSaver() *BlogPostSaver {
    return &BlogPostSaver{
        storage: NewStorage(),
    }
}


func (s *BlogPostSaver) Save(post *Post) {
   s.Storage.Save(post)
}


# Клиент - Сервер

HTTP Запросы
  |
HANDLER
  |
SERVICE (Бизнес логика)
  |
REPOSITORY (Работа с БД)


# LUNCH PROJECT
``go run ./cmd/main.go or go run cmd/main.go``

