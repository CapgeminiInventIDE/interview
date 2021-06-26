<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/7/7e/Invent_Logo_2COL_RGB.png" style="width:80%;"><br>
</div>

-----------

# Interview - Data Everywhere

## Instructions

- You have **5 days** to complete this assignment, which should be submitted to us as a **private** repo (make sure to allow access to the given hiring manager's github account).
- We have layed out a sample structure for you in the [submission folder](/submission), you should add your submission material into this folder.
- You should answer **2** out of 3 questions from section A and all of section B.

While doing this take home assignment you will have access to the "client" through the teams link that has been sent to you by the recruitment team, simply join the meeting at anytime to start sending messages to the "client". They can clarify any questions for you in the technical section, and they will be responsive to questions you have for your case study, to emulate real client interactions.

## Section A

> Only answer 2 out of 3 questions in this section.

### Question 1 - Data Wrangling

> The purpose of this question is to demonstrate your data gathering and manipulation skills.

Use the [Pokemon API](https://pokeapi.co/) to create a tabular data structure which has the following format (for all pokemon):

| id | order | name | weight | speed | special-defense | special-attack | defense | attack | hp | dominant_color | image_link |
| -- | ----- | ---- | ------ | ---------- | ----- | --------------- | -------------- | ------- | ------ | -- | ------- |
| 132| 203 | Ditto | 40 | 48 | 48 | 48 | 48 |  48 | 48 | #9C5CB4 | https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/132.png |

You can use any techniques, packages or services for finding the dominant color, however you should be able to explain how it works in the interview.

---

### Question 2 - Exposing Data

> The purpose of this question is to show how to clearly expose data in your applications to external users with zero prior knowledge of your systems.

Create a well documented API (hint: swagger) that users can get information about a person (**information should be faked**), for example:

| Endpoint                | Explaination                             | Example Output                                                                                                                        |
|-------------------------|------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| `/me/age`                 | Returns age in years                     | `{'age': 31, 'unit': 'years'}`                                                                                                          |
| `/me/age?unit=days`       | Returns age in days                      | `{'age': 11323, 'unit': 'days'}`                                                                                                        |
| `/me/height`              | Returns height in cm                     | `{'height': 180, 'unit': 'cm'}`                                                                                                       |
| `/me/height?unit=feet`    | Returns height in feet                   | `{'height': 5.9, 'unit': 'foot'}`                                                                                                     |
| `/me/name`                | Returns first and last name              | `{'first': 'Jane', 'last': 'Doe'}`                                                                                                    |
| `/me/gender`              | Returns Gender                           | `{'gender': 'F'}`                                                                                                                     |
| `/me/favorite/food`       | Returns the full list of favorite foods  | `[{'name': 'Pizza'}, {'name': 'Pie'}, {'name': 'Poultry'}, {'name': 'Peas'}, {'name': 'Peanuts'}]`                                    |
| `/me/favorite/food?max=3` | Returns at most 3 favorite foods         | `[{'name': 'Pizza'}, {'name': 'Pie'}, {'name': 'Poultry'}]`                                                                           |
| `/me/favorite/drinks`     | Returns the full list of favorite drinks | `[{'name': 'Water'}, {'name': 'Watermelon Juice'}, {'name': 'Soda Water'}, {'name': 'Sparkling Water'}, {'name': 'Flavoured Water'}]` |
| `/me/favorite/food?max=2` | Returns at most 3 favorite drinks        | `[{'name': 'Water'}, {'name': 'Watermelon Juice'}]`                                                                                   |

---

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

## Section B

### Question 1 - Code Review

> The purpose of this question is to evaluate your capacity to perform a constructive code review for your peers.

You should review the below piece of code, make notes on how your reviewee could adapt or change the code (ask questions to your "client" - see top of page). You will ultimately give verbal feedback to the interviewer in a role playing exercise.

```python
def get_line_coef(p1, p2):
    points = [p1, p2]
    x_coords, y_coords = zip(*points)
    A = np.vstack([x_coords, np.ones(len(x_coords))]).T
    m, c = np.linalg.lstsq(A, y_coords, rcond=None)[0]
    return m, c
```

---

### Question 2 - Technology Assessment

> The purpose of this question is to gain an understanding on your ability to perform a literature search and present arguments for/against a given technology and supply an ultimate decision.

TODO: Add in a technology (eg webserver, language, ML choices for client, ...) for applicant to pose a few solutions to and present back in the interview.

---

### Question 3 - Project/Case Study

> The purpose of the case study is to evaluate your Data Science skills applied to consulting, which should show a combination of domain knowledge, technology (ML, statistics, programming), and business acumen.

You should pick **one** of the below projects to complete, you will present this project to the interviewers and add your source code into your repository.

#### Project 1

Tabular data...

#### Project 2

Image data...

#### Project 3

Time-series data...
