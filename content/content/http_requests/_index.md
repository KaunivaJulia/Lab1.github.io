---
title: "HTTP Requests"
description: "Отчёт по HTTP-запросам (пункт 1)"
---

# HTTP Requests

## 1. GET и POST через netcat (CLI)
Использован postman-echo.com — публичный echo API, который возвращает параметры запроса и тело POST-запроса в ответе.

## 1.1 GET-запрос
Подключение:
```bash
/usr/bin/nc -v postman-echo.com 80
```
Введённый HTTP-запрос:
```http
GET /get?from=netcat HTTP/1.1
Host: postman-echo.com
User-Agent: netcat
Accept: */*
Connection: close

```
![GET через netcat](/images/http_requests/get.png)

## 1.2 POST-запрос
Подключение:
```bash
/usr/bin/nc -v postman-echo.com 80
```
Введённый HTTP-запрос:
```http
POST /post HTTP/1.1
Host: postman-echo.com
User-Agent: netcat
Accept: */*
Content-Type: application/x-www-form-urlencoded
Content-Length: 19
Connection: close

name=test&value=123
```
![POST через netcat](/images/http_requests/post.png)
