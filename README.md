# 📚 Library Management System API using SLIM Framework
----------------------------------------------------------------------------------------------------------
## Overview 
The Library Management System API is built using the SLIM Framework to create lightweight, RESTful endpoints. It’s a simple yet powerful example of how SLIM makes API development easy and efficient, providing a seamless way to manage resources like books, members, and transactions.

## Table of Contents
- [Key Features](#key-features)
- [Installation Required](#installation-required)
- [Endpoints](#endpoints)
--------------------------------------------------------------------------------------------------------
## Key Features 
### 🔒 JWT Authentication 
- Token-based user verification for secure API access. One-time token validity to enhance session security.
### 🔍 Advanced Search and Filters 
- Search for books by genre, author, availability, or publication date.
### 📖 Comprehensive CRUD Operations
- Add, update, delete, and view book records with search by title, author, or unique ID.
--------------------------------------------------------------------------------------------------------
## Installation Required
```
composer require slim/slim:3.*
composer require firebase/php-jwt
```
## Endpoints🚀
----------------------------------------------------------------------------------------------------------
## User Endpoints 👤
----------------------------------------------------------------------------------------------------------
### Register a new user
- **Method:** `POST ` 
- **Endpoint:** `/users/register`  

- _**Payload:**_
```json
{
    "email": "gean@gmail.com",
    "username": "Geannele",
    "password": "gean1234"
}
```
- _**Response:**_
```json
{
    "status": "success",
    "data": null
}
```
----------------------------------------------------------------------------------------------------------
### Login and obtain JWT token
- **Method:** `POST`
- **Endpoint:** `/users/login`

- _**Payload:**_
```json
{
    "email": "gean@gmail.com",
    "password": "gean1234"
}
```
- _**Response:**_
```json
{
    "status": "success",
    "token": "your_jwt_token"
}
```
----------------------------------------------------------------------------------------------------------
### View all users in the system
- **Method:** `GET`
- **Endpoint:** `/users/displayAll`

- _**Payload:**_
```json
{
    "token": "your_jwt_token"
}
```
- _**Response:**_
```json
{
    "status": "success",
    "new_token": "new_jwt_token",
    "data": [
        {
           "userid": "1",
           "email": "gean@gmail.com",
           "username": "Geannele"
        }
    ]
}
```
----------------------------------------------------------------------------------------------------------
## Book Endpoints 📚
----------------------------------------------------------------------------------------------------------

### Add a new book
- **Method:** `POST`
- **Endpoint:** `/books/add`

- **Payload:**
```json
{
      "author": "author_name",
    "title": "book_title",
    "genre": "book_genre",
    "token": "your_jwt_token"
}
```
- **Response:**
```json
{
    "status": "success",
    "new_token": "new_jwt_token"
}
```
----------------------------------------------------------------------------------------------------------
### Update an existing book
- **Method:** `PUT`
- **Endpoint:** `/books/update`

- **Payload:**
```json
{
    "author": "author_name",
    "title": "book_title",
    "genre": "book_genre",
    "bookCode": "book_code",
    "token": "your_jwt_token"
}
```
- **Response:**
``` json
{
    "status": "success",
    "new_token": "new_jwt_token"
}
```
----------------------------------------------------------------------------------------------------------
### Delete a book by bookCode
- **Method:** `DELETE`
- **Endpoint:** `/books/delete`
- **Payload:**
``` json
{
    "bookCode": "bookCode",
    "token": "your_jwt_token"
}
```
- **Response:** 
``` json
{
    "status": "success",
    "new_token": "new_jwt_token"
}
```
----------------------------------------------------------------------------------------------------------
### Display all books by a specific author
- **Method:** `GET`
- **Endpoint:** `/books/displayAll`

- **Payload:**
``` json
{
    "token": "yout_jwt_token"
}
```
- **Response:**
``` json
{
    "status": "success",
    "new_token": "new_jwt_token",
    "data": [
        {
           "bookid": "1",
           "title": "book_title",
           "genre": "book_genre",
           "bookCode": "book_code",
           "authorid": "1",
           "authorname": "author_name"
        }
    ]
}
```
----------------------------------------------------------------------------------------------------------
### Display all books by a specific author
- **Method:** `GET`
- **Endpoint:** `/books/displayauthorsbooks`

- **Payload:**
``` json
{
    "token": "your_jwt_token",
    "authorname": "author_name"
}
```
- **Response:**
``` json
{
    "status": "success",
    "new_token": "new_jwt_token",
    "data": [
      {
        "bookid": "book_id",
        "title": "book_title",
        "genre": "book_genre",
        "bookCode": "book_code",
        "authorid": "author_id",
        "authorname": "author_name"
      }
   ]
}
```
----------------------------------------------------------------------------------------------------------
### Search books by title
- **Method:** `GET`
- **Endpoint:** `/books/displaytitlebooks`

- **Payload:**
``` json
{
    "token": "your_jwt_token",
    "booktitle": "book_title"
}
```
- **Response:**
``` json
{
    "status": "success",
    "new_token": "new_jwt_token",
    "data": [
        {
            "bookid": "1",
            "title": "book_title",
            "genre": "book_genre",
            "bookCode": "book_code",
            "authorid": "1",
            "authorname": "author_name"
        }
    ]
}
```
----------------------------------------------------------------------------------------------------------
### Search books by genre
- **Method:** `GET`
- **Endpoint:** `/books/displaygenrebooks`

- **Payload:**
``` json
{
    "token": "your_jwt_token",
    "bookgenre": "book_genre"
}
```
- **Response:**
``` json
{
    "status": "success",
    "new_token": "new_jwt_token",
    "data": [
        {
            "bookid": "1",
            "title": "book_title",
            "genre": "book_genre",
            "bookCode": "book_code",
            "authorid": "1",
            "authorname": "author_name"
        }
    ]
}
```
----------------------------------------------------------------------------------------------------------
## Author Endpoints ✍️
----------------------------------------------------------------------------------------------------------
### Add a new author
- **Method:** `POST`
- **Endpoint:** `/authors/add`

- **Payload:**
``` json
{
    "authorname": "author_name",
    "token": "your_jwt_token"
}
```
- **Response:**
``` json
{
    "status": "success",
    "new_token": "new_jwt_token"
}
```
----------------------------------------------------------------------------------------------------------
### Update author information.
- **Method:** PUT
- **Endpoint:** /authors/update

- **Payload:**
``` json
{
    "authorid": "author_id",
    "authorname": "author_name",
    "token": "your_jwt_token"
}
```
- **Response:**
``` json
{
    "status": "success",
    "new_token": "new_jwt_token"
}
```
----------------------------------------------------------------------------------------------------------
### Delete an author by ID.
- **Method:** `DELETE`
- **Endpoint:** `/authors/delete`

- **Payload:**
``` json
{
    "authorid": "author_name",
    "token": "new_jwt_token"
}
```
- **Response:**
``` json
{
    "status": "success",
    "new_token": "new_jwt_token"
}
```
----------------------------------------------------------------------------------------------------------
### View all authors.
- **Method:** `GET`
- **Endpoint:** `/authors/display`

- **Payload:**
``` json
{
    "token": "your_jwt_token"
}
```
- **Response:**
``` json
{
    "status": "success",
    "new_token": "new_jwt_token",
    "data": [
        {
            "authorid": "1",
            "authorname": "author_name"
        }
    ]
}
```




 
