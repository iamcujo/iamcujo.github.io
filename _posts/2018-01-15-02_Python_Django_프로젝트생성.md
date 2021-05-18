---
layout: post
title: Python + Django 프로젝트 생성
description: >
tags: [django]
---



### Python + Django 프로젝트 생성



**1. Django 프로젝트 생성**

- CMD창에서 프로젝트를 생성하려는 폴더로 이동한다.

- 프로젝트 생성 명령어를 입력한다.

  ```
  > django-admin startproject djangoFirst
  ```

  ```
  명령어 : django-admin (django-admin.py 파일 실행)
  옵션 : startproject
  프로젝트명 : djangoFirst
  ```



**2. Django 프로젝트 실행**

- CMD창에서 프로젝트 생성 시 manage.py 파일이 생성된 경로로 이동한다.

```
> python manage.py runserver
```

- 브라우저에서 http://127.0.0.1:8000 입력하면, django 실행 성공 화면을 볼 수 있다.