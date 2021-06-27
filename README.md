<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/7/7e/Invent_Logo_2COL_RGB.png" style="width:80%;"><br>
</div>

-----------

# Interview - Data Everywhere

This interview structure has been selected to slowly increase ambiguity, with the ability to talk to "clients". The aim of which is to emulate the tasks you would be expected to do while working on projects with clients.

*You should take the opportunity to showcase your skills to show what sets you apart.*

## Our Interview process

- [x] Apply
- [x] Phone screening and resume assessment
- [ ] Take Home Assignment
- [ ] Panel Interview with a Manager & Senior Manager
- [ ] Offer

## Instructions

- You have **5 days** to complete this assignment, which should be submitted to us as a **private** repo (make sure to allow access to the given hiring manager's github account).
- We have layed out a sample structure for you in the [submission folder](/submission), you should add your submission material into this folder.
- You should answer **2** out of 3 questions from section A and all of section B.
- This technical assessment should take around 2-3 hours

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

-----------

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

-----------

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

-----------

### Question 2 - Technology Assessment

> The purpose of this question is to gain an understanding on your ability to perform a literature search and present arguments for/against a given technology and supply an ultimate decision.

You will be supplied a technology (eg webserver, language, ML choices for client, ...) to conduct a literature search on. You should present arguments for/against a given technology and supply an ultimate decision. You will be expected to present your findings in the interview and defend your stance.

-----------

### Question 3 - Project/Case Study

> The purpose of the case study is to evaluate your Data Science skills applied to consulting, which should show a combination of domain knowledge, technology (ML, statistics, programming), and business acumen.

- Pick **one** of the below projects to complete, you will present this project to the "clients" (interviewers)
- Add any of your source code into your repository for submission
- Create a presentation that covers:
  - Initial data analysis and exploration
  - Modelling proposals and assumptions
  - Proposed architecture  
  - Path to production
  - Business value proposition

#### Project 1 - Classic

You are working with a utilities company that wants to understand why customers are paying late, they keep all of their customer and payment data in a relational database and want to use data science to understand what their customers are experiencing, how would you design an analytics platform and pipeline to facilitate this.

**Sample data:**

| Billing_Issues_1month | Billing_Issues_2month | Invoice_Count | Qtr | Year | Billing_Method | Payment_Method   | Account_Owner_Role | Risk_Factor | Hardship_Notice | Payment_Agreement | Concession_Agreement | High_Usage_Indicator | Invoice_Notice_Sent | Final_Notice_Sent | Payment_Issue_Notice | Requested_Additional_Payment_Time | Gov_Grant_Enrolled | Prior_Hardship_Notice | Complaint_Count | Customer_Contact_Count | Property_Type | Property_Suburb   | Property_County   | Gov_Housing | Qtr_Rain_MM |
|-----------------------|-----------------------|---------------|-----|------|----------------|------------------|--------------------|-------------|-----------------|-------------------|----------------------|----------------------|---------------------|-------------------|----------------------|-----------------------------------|--------------------|-----------------------|-----------------|------------------------|---------------|-------------------|-------------------|-------------|-------------|
| No                    | No                    | 50            | 1   | 2017 | Mail           | Payment_Method 1 | Tenant             | Low Risk    | No              | Yes               | No                   | No                   | Yes                 | Yes               | Yes                  | Yes                               | No                 | No                    |                 | 8                      | Dwelling      | Property_Suburb 1 | Property_County 1 | No          | 152.2       |
| No                    | No                    | 51            | 2   | 2017 | Mail           | Payment_Method 1 | Tenant             | Low Risk    | No              | Yes               | No                   | No                   | Yes                 | Yes               | Yes                  | Yes                               | No                 | No                    |                 | 8                      | Dwelling      | Property_Suburb 1 | Property_County 1 | No          | 172.1       |
| No                    | No                    | 35            | 4   | 2016 | Mail           | Payment_Method 2 | Owner Occupier     | Low Risk    | No              | No                | No                   | No                   | Yes                 | Yes               | No                   | No                                | No                 | No                    |                 | 1                      | Dwelling      | Property_Suburb 2 | Property_County 2 | No          | 0           |
| No                    | No                    | 38            | 1   | 2017 | Mail           | Payment_Method 2 | Landlord           | Low Risk    | No              | No                | No                   | No                   | Yes                 | Yes               | No                   | No                                | No                 | No                    |                 | 1                      | Dwelling      | Property_Suburb 3 | Property_County 3 | No          | 132.8       |
| Yes                   | Yes                   | 31            | 2   | 2016 | Mail           | Payment_Method 2 | Owner Occupier     | Low Risk    | No              | No                | Yes                  | No                   | Yes                 | No                | No                   | Yes                               | No                 | No                    |                 | 2                      | Unit          | Property_Suburb 4 | Property_County 1 | No          | 7           |
| No                    | No                    | 34            | 1   | 2017 | Mail           | Payment_Method 2 | Owner Occupier     | Low Risk    | No              | No                | Yes                  | No                   | Yes                 | No                | No                   | Yes                               | No                 | No                    |                 | 3                      | Unit          | Property_Suburb 4 | Property_County 1 | No          | 152.2       |
| No                    | No                    | 33            | 4   | 2016 | Mail           | Payment_Method 2 | Owner Occupier     | Low Risk    | No              | No                | No                   | No                   | Yes                 | Yes               | No                   | Yes                               | No                 | No                    |                 | 3                      | Dwelling      | Property_Suburb 4 | Property_County 1 | No          | 214.2       |
| Yes                   | Yes                   | 30            | 2   | 2016 | Email          | Payment_Method 3 | Owner Occupier     | Low Risk    | No              | No                | No                   | No                   | Yes                 | Yes               | No                   | Yes                               | No                 | No                    |                 | 4                      | Unit          | Property_Suburb 5 | Property_County 4 | No          | 7.6         |
| Yes                   | Yes                   | 33            | 1   | 2017 | Email          | Payment_Method 4 | Owner Occupier     | Low Risk    | No              | No                | No                   | No                   | Yes                 | Yes               | No                   | Yes                               | No                 | No                    |                 | 4                      | Unit          | Property_Suburb 5 | Property_County 4 | No          | 98.2        |
| No                    | No                    | 46            | 3   | 2016 | Mail           | Payment_Method 2 | Owner Occupier     | High Risk   | No              | No                | No                   | No                   | Yes                 | Yes               | Yes                  | Yes                               | No                 | Yes                   |                 | 3                      | Dwelling      | Property_Suburb 1 | Property_County 1 | No          | 231.4       |

#### Project 2 - Image

You are working on a proposal for uplifting the governments identification process, which includes supplying a passport quality image of the applicants face. You should supply a proposal with a plan on how to build and deploy a solution that can verify an applicants photograph from a government issued mobile application.

Helpful links:

- [Passport photo guidelines](https://www.passports.gov.au/getting-passport-how-it-works/photo-guidelines)
- [Open source human face dataset](https://www.kaggle.com/ashwingupta3012/human-faces)

#### Project 3 - NLP

You are working with an intelligence organization who want to build a service that can pull information from a device in order to establish the targets network. You have been asked to supply a proposal with a plan on how to build and deploy a solution. The solution should find and match entities with enriched information from unstructured texts and contacts.

**Example data:**

```json
{
  "message": "Is John with you?",
  "to": "+61484932566",
  "gps": [
    -37.840935, 144.946457
  ],
  "epoch": 1561623216
}
```

# References

- This take-home was built with the applicant in mind and took learnings from [CodeSubmit](https://codesubmit.io/blog/take-home-coding-challenge/)
