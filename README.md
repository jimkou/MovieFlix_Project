# MovieFlix_Project
Flask application with mongoDB

#### HOW TO RUN:
>Make sure you have docker and docker-compose installed correctly on your computer.
>git clone the repository , cd into it and then type docker-compose up
```sh
$ git clone https://github.com/jimkou/MovieFlix_Project.git
$ cd https://github.com/jimkou/MovieFlix_Project
$ sudo docker-compose up
```
#### IMPORTANT NOTES:
> The application works only with 1 login session. So it handles only one user at the time with the variables login_name and login_email.

#### OPERATIONS
> Important Note: Database is initialzed with an admin account by default. Email: admin , Name : admin , Password : admin
- User Registration 
  - Navigate to http://localhost:5000/user_register 
  - Type your email , username and password and press the register button
- User Login 
  - Navigate to http://localhost:5000/user_login
  - Type your email and password and press the login button
- Search Movie
    >  Note that you can search for multiple titles or actors simultaneously with just a space between them.
    > Search is not case sensitive , so it doesn't matter if you type caps or not.
  - Navigate to http://localhost:5000/search_movie
  - Fill at least one of the following fields to search a movie
      * [Title] to search by  Movies Title
      * [Year] to search by Movies year
      * [Actors] to search by Movies Actors
- Movie information
  - Navigate to http://localhost:5000/movie_info
  - Type the movie title you want to search for(Same as movie_search but comments and ratings wont return)
- Comments of a movie
  - Navigate to http://localhost:5000/comments
  - Type the movie title and movie year you want and the page will appear all the comments of the movie
     
- Rate a movie
  - Navigate to http://localhost:5000/rate_movie
  - Fill the following fields
    *  Title of the Movie
    *  Year of the Movie
    *  Rating
    > You can only rate a movie once. If you want to change your rating you must delete the current rating and then make a new.
 - Delete a movie rating
    - Navigate to http://localhost:5000/delete_rating
    - If you are logged in as a simple User:
        * Type the title and the year of the Movie that you want your ratings to be deleted from
    - If you are logged in as Administrator:
        * Type the user email and the movie title and year that you want to delete user ratings at the particular movie.
        > As a admin if you want to delete your rating in a movie you just type your email instead of a user's email.
- Make a comment
    - Navigate to http://localhost:5000/make_comment
        * Type movie title you want to comment to
        * Type the movie year 
        * Type the comment
        > If you type the same comment at the same movie more than once , then comment is not gone to be made again.
- See all your comments 
    - Navigate to http://localhost:5000/all_comments
    - If you are logged in as a simple User:
        * Page will all your comments will appear
    - If you are logged in as Administrator:
        * Type user email to see all the comments he made(Or type your email to see yours) 
- See all your ratings
    - Navigate to http://localhost:5000/ratings
    - If you are logged in as a simple User:
         * Page will all your ratings will appear
    - If you are logged in as Administrator:
         * Type user email to see all the ratings he made(Or type your email to see yours) 
- Delete a comment
    - Navigate to http://localhost:5000/delete_comment
    - if you are a simple User:
        * Type movie title and year you want to delete your comment from
        * Type the comment for deletion
    - If you are Administrator:
        * Type email of user or your email
        * Type movie title and year you want to delete your comment from
        *  Type the comment for deletion
- Delete an account
    - Navigate to http://localhost:5000/delete_user
    - if you are a simple User:
        * Type Yes if you really want to delete your account
    - If you are Administrator:
        * Type email of the user that you want to delete
#### ADMINISTRATOR OPERATIONS
- Insert a Movie
    - Navigate to http://localhost:5000/insert_movie
    - From the following fields admin must fill at least Title of Movie and one actor
        * Title
        * Year
        * Desciption
        * Actors
        * Rating
        * Comments
    > Administrator can insert multiple actors with a comma between them
    > He also can insert a rating or a comment in the movie he inserts.
- Delete a movie
    - Navigate to http://localhost:5000/delete_movie
    - User must type the Movie Title for deletion
    >  In case of two movies exist with this title then the older movies will be removed.
- Update a movie
    - Navigate to http://localhost:5000/update_movie
    - From the following fields admin must fill  Title of Movie for update  and at least one of the rest fields.
        * Title of movie for update
        * Title
        * Year
        * Desciption
        * Actors insert
        * Actors delete
        > You can insert one actor here and delete 1 actor at the same time.
- Delete a comment 
    - Navigate to http://localhost:5000/delete_comment
    - Fill the following fields:
        * Email of user
        * Title of Movie
        * Year of the Movie
        * The comment for deletion
- Upgrade a User 
    - Navigate to http://localhost:5000/upgrade_user
    - Fill the following fields:
        * Email of user for upgrade 
- Delete a User 
    - Navigate to http://localhost:5000/delete_user
    - Fill the following fields:
        * Email of user for deletion      
        > Can delete only himself or simple users
