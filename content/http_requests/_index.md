

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
[![GET через netcat](/Lab1.github.io/images/http_requests/get.png)](/Lab1.github.io/images/http_requests/get.png)

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
[![POST через netcat](/Lab1.github.io/images/http_requests/post.png)](/Lab1.github.io/images/http_requests/post.png)

## 2. Те же запросы через cURL

**cURL** — это утилита командной строки, которая умеет отправлять HTTP-запросы (GET, POST и др.) прямо из терминала.  

## 2.1 GET-запрос (cURL)

Команда:
```bash
curl -i "https://postman-echo.com/get?from=curl"
```
[![GET через curl](/Lab1.github.io/images/http_requests/get2.png)](/Lab1.github.io/images/http_requests/get2.png)

---

## 2.2 POST-запрос (cURL)

Команда:
```bash
curl -i -X POST "https://postman-echo.com/post" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  --data "name=test&value=123"
```
[![POST через curl](/Lab1.github.io/images/http_requests/post2.png)](/Lab1.github.io/images/http_requests/post2.png)

