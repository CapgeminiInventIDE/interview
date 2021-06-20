# Capgemini Invent Data Based Interview

## Overview

You have **5 days** to complete this assignment, which should be submitted to us as a **private** repo (make sure to allow access to the given hiring manager's github account). We have layed out a sample structure for you in the [submission folder](/submission).

While doing this take home assignment you will have access to the "client" through the email/discord link that has been sent to you by the recruitment team. They can clarify any questions for you in the technical section, and they will be responsive to questions you have for your case study, to emulate real client interactions.

## Technical Questions

### Question 1 - Data Wrangling

> The purpose of this question is to demonstrate your data gathering and manipulation skills.

Use the [Pokemon API](https://pokeapi.co/) to create a tabular data structure which has the following format (for all pokemon):

| id | order | name | weight | speed | special-defense | special-attack | defense | attack | hp | dominant_color | image_link |
| -- | ----- | ---- | ------ | ---------- | ----- | --------------- | -------------- | ------- | ------ | -- | ------- |
| 132| 203 | Ditto | 40 | 48 | 48 | 48 | 48 |  48 | 48 | #9C5CB4 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/132.png |

You can use any techniques, packages or services for finding the dominant color, however you should be able to explain how it works in the interview.

### Question 2 - Exposing Data

> The purpose of this question is to show how to clearly expose data in your applications to external users with zero prior knowledge of your systems.

Create a well documented API (hint: swagger) that users can get information about yourself (information can be faked), for example:

- `curl -X GET http://localhost:8000/me/age` should return your age, eg `{'age': 31, 'unit': 'years'}`
- `curl -X GET http://localhost:8000/me/age?unit=days` should return your age, eg `{'age': 11323, 'unit': 'days'}`
- `curl -X GET http://localhost:8000/me/height` should return your height eg `{'height': 180, 'unit': 'cm'}`
- `curl -X GET http://localhost:8000/me/height?unit=feet` should return your height eg `{'height': 5.9, 'unit': 'foot'}`
- `curl -X GET http://localhost:8000/me/name` should return your name eg `{'first': 'Jane', 'last': 'Doe'}`
- `curl -X GET http://localhost:8000/me/gender` should return your gender eg `{'gender': 'F'}`
- `curl -X GET http://localhost:8000/me/favorite/food` should return your top 5 favorite foods eg `[{'name': 'Pizza'}, {'name': 'Pie'}, {'name': 'Poultry'}, {'name': 'Peas'}, {'name': 'Peanuts'}]`
- `curl -X GET http://localhost:8000/me/favorite/food?max=3` should return your top 3 favorite foods eg `[{'name': 'Pizza'}, {'name': 'Pie'}, {'name': 'Poultry'}]`
- `curl -X GET http://localhost:8000/me/favorite/drinks` should return your top 5 favorite drinks eg `[{'name': 'Water'}, {'name': 'Watermelon Juice'}, {'name': 'Soda Water'}, {'name': 'Sparkling Water'}, {'name': 'Flavoured Water'}]`
- `curl -X GET http://localhost:8000/me/favorite/food?max=2` should return your top 2 favorite drinks eg `[{'name': 'Water'}, {'name': 'Watermelon Juice'}]`

### Question 3 - Complex Problem

> The purpose of this question is to see how you tackle complex problems, which have simple solutions.

A safe keypad has the following layout:

```txt
┌───┬───┬───┐
│ a │ b │ c │
├───┼───┼───┤
│ d │ e │ f │
├───┼───┼───┤
│ g │ h │ i │
└───┼───┼───┘
    │ j │
    └───┘
```

You are able to observe the targeted person entering the code, which you think is "afdj" it is possible that each of the characters could actually be another that is adjacent (horizontally or vertically, but not diagonally). Eg `"a"` could have been `"b"` or `"d"` and the result would therefore be `["a", "b", "d"]`, another example, `"jj"` could have been `["jj", "jh", "hj", "hh"]`.

These kind of locks can have unlimited attempts and do not sound any alarm, therefore your task as the **hacker** is to make a function `crack(code: str) -> List[str]: ...` that can find all variations for a given code that could be 1-8 characters in length.

### Question 4 - Code Review

> The purpose of this question is to evaluate your capacity to perform a constructive code review for your peers.

TODO: Add in piece of code ~ 10-15 lines long for review, the applicant will make notes, but ultimately give verbal feedback to the interviewer in a role playing exercise.

### Question 5 - Technology Assessment

> The purpose of this question is to gain an understanding on your ability to perform a literature search and present arguments for/against a given technology and supply an ultimate decision.

TODO: Add in a technology (eg webserver, language, ML choices for client, ...) for applicant to pose a few solutions to and present back in the interview.

## Project - Case Study

> The purpose of the case study is to evaluate your Data Science skills applied to consulting, which should show a combination of domain knowledge, technology (ML, statistics, programming), and business acumen.

You should pick **one** of the below projects to complete, you will present this project to the interviewers and add your source code into your repository.

### Project 1

Tabular data...

### Project 2

Image data...

### Project 3

Time-series data...

### Project 4

Audio data...
