# Team 1 - Best Bytes 
<p align = "center">
<img width="300" alt="Screenshot 2022-12-15 at 11 13 42" src="https://user-images.githubusercontent.com/60015635/207845276-0b5715fa-7549-4253-8e6e-7c64dc28177f.png">
</p>

Best Bytes alllows users to submit a food review, further interaction is also available through deleting and updating reviews and so much more.
<p align = "center">
Taking life one bite at a time
</p>

## Project Description
We wanted to create a space where food lovers, just like us, can share their food related experiences all in one place. 

This application gives the users the space to add, update and delete reviews to the database - we have created specific classes for this with properties that we deemed to be the most important for creating these reviews.

## Key Features 
Beyond our basic CRUD functionalilty, we decided to implement a few key features to increase the user's ability to interact with the API. These features include a randomisation function to allow to user to find a foodplace at random if they cannot decide where to eat. We also use derived queries to create filters (eg: filter foodplaces based on foodtype among others).

**We have created:** Classes for user, review, foodplace along with their respected services, repositories and controllers.


## MVP ##  

- Create user, review and foodplace.
- Read users, reviews and foodplaces.
- Update users, reviews and foodplaces.
- Delete users, reviews and foodplaces.
- Add review method in User to attach a review.

### UML MVP ###
<img width="986" alt="UML MVP" src="https://user-images.githubusercontent.com/60015635/207842537-5b50a8c3-2595-44bf-b323-1c7b9f1f3b09.png">

### ERD  ###

We used two one-to-many relationships, so one user to many reviews and one food place to many reviews.
<img width="986" alt="ERD MVP" src="https://user-images.githubusercontent.com/60015635/207842999-a269756e-bfb7-488a-a82e-25219a526afb.png">

### MVC ###
<img width="1408" alt="Screenshot 2022-12-15 at 11 48 20" src="https://user-images.githubusercontent.com/60015635/207851793-3c86a793-c404-40dd-8f59-5b2cb67d0172.png">

## Completed Extensions ##

- Delete review method in User and Review (to allow moderators to also delete inappropriate reviews).
- Average rating method in FoodPlace class.
- Derived queries for filtering User's name, FoodPlace's name, food type and average ratings.
- Changed openingHours: String to openingHour:LocalTime and closingHour: LocalTime.


## Tech Stack ##
- Java
- Spring Framework (dependencies: Spring Web, Spring Boot DevTools, PostgreSQL Driver, Spring Data JPA
- Postman
- Postico
- Terminal
- Git and GitHub

## Installation Instructions ##
TO copy our git repo, please follow the instructions below:
- Git clone SSH Key git clone git@github.com:e-b-m/team_1_food_review.git 
- Create a database called food_review in the terminal (createdb food_review)
- Also make sure to install postgres, paste this command into the terminal ---> brew install postgresql 

## Routes ##
localhost:8080...
|Request Type                  |HTTP Request Path                        | Description                                  |
|:----------------------------:|:----------------------------------------|:---------------------------------------------|
|GET                           |.../user                                 |Display all users                             |
|POST                          |.../user                                 |Add a new user                                |
|GET                           |.../user/1                               |Find user by id                               |
|PUT                           |.../user/1                               |Update user                                   |
|DELETE                        |.../user/1                               | Delete user                                  |         
|GET                           |.../user/1/reviews                       |Get all reviews from the user by their id     |
|GET                           |.../user/1/foodplace                     |Get food places from user                     |
|GET                           |.../user/username?name=Zsolt             |Find user by name                             |
|GET                           |.../foodplace                            |Display all food places                       |
|POST                          |.../foodplace                            |Add a new food place                          |
|GET                           |.../foodplace/1                          |Find food place by id                         |
|PUT                           |.../foodplace/1                          |Update food place                             |
|DELETE                        |.../foodplace/1                          |Remove a food place                           |
|GET                           |.../foodplace/1/reviews                  |Get all reviews from a food place             |
|GET                           |.../foodplace/1/average_rating           |Get average rating of a food place            |
|GET                           |.../foodplace/name?name=Amigos           |Find food place by name                       |
|GET.                          |.../foodplace/foodtype?foodType=Japanese |Filter food places by food type               |
|GET                           |.../foodplace/random                     |Find a random food place                      |
|GET                           |.../review                               |Display all reviews                           |
|POST                          |.../review                               |Add a new review                              |
|GET                           |.../review/1                             |Find review by id                             |
|PUT                           |.../review/1                             |Update a review                               |
|DELETE                        |.../review/1                             |Remove a review                               |



## Example Objects ##
Below are examples of the objects in Json form.
```js 
FoodPlace: {
    "name" : "TacoBell",
    "foodType" : "Mexican",
    "openingHour": "09:00:00",
    "closingHour": "16:00:00",
    "website": "TacoBell.com"
}
```
```js 
User: {
    "name": "oogway"
}
```

```js 
Review: {
    "rating": 5.0,
    "reviewText": "The food was very amazing.",
    "date": "2022-10-06",
    "userId": 1,
    "foodPlaceId": 1
}
```
## Testing ##
We decided to test all our routes in Postman and Postico.

Here is a sample of our testing in Postman - it shows our GET request to display all the reviews.

<img width="716" alt="Screenshot 2022-12-15 at 14 20 53" src="https://user-images.githubusercontent.com/110283546/207885190-c20d8dcf-af11-40e4-aee5-eb2859957dfc.png">


This is what our Review table looks like in Postico.

<img width="851" alt="Screenshot 2022-12-15 at 11 31 03" src="https://user-images.githubusercontent.com/110283546/207850516-1520efb1-cf4b-474d-9cc0-45af4c0a55cb.png">


Here is the code from the Review Controller.

`    @GetMapping
    public ResponseEntity<List<Review>> getAllReviews() {
        List<Review> reviews = reviewService.displayAllReviews();
        return new ResponseEntity<>(reviews, HttpStatus.OK);
    }`
    
   ## Further Incomplete Extensions ##
- Making the food types a list in case a food place had more than one food type e.g. a buffet restaurant could have Mexican, Chinese and Thai food. 
- Adding a list of food items to each food place. 
- Google maps - making our API compatible with Google maps to help with the front-end. 
- Applying contact information to the API so people can access details from the foodplace. 




## Thank you ##
Thank you to all the trainers for helping and inspiring us, and thank you to everyone on our cohort for supporting us. 

See you next year 😘

