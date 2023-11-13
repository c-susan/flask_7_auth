# flask_7_auth
HHA504 / Cloud Computing / Assignment 7 / Session Management and User Authentication

This repo aims to dive into the core of application security: user sessions and authentication. Flask and an external identity provider like Google Cloud is utilized, ensuring the Flask application is both user-friendly and secure.

# Documentation 

### 1. Session Management with Flask-Session
I took the following steps to setup Flask-Session in the application: 
1. Pip install Flask-Session in the terminal: ```pip install Flask-Session```
2. In the `app.py` file, imported the module: ```from flask_session import Session```
3. Configured Flask-Session by adding the code:
    ```
    app.config["SESSION_PERMANENT"] = False
    app.config["SESSION_TYPE"] = "filesystem"
    Session(app)
    ```
Flask-Session helps in managing user sessions by storing user-specific information between requests. When a user starts a new session, Flask-Session will create a unique session ID for that user, which will allow it to associate requests from the same user with their specific session. The `session` object in Flask will act as a dictionary to store user-specific information.

### 2. User Authentication with Flask:
To authenticate user registration, login, and logout, the user authentication system uses OAuth 2.0 and Google as the identity provider. 
+ In the `app.py` file, ```update_or_create_user(user)``` is used to register users into the system when a user successfully authenticates with Google. 
+ ```session['user'] = user``` is used create a user session and store their information to keep track of the authenticated user across the different routes of the application. 
+ ```session.pop('user', None)``` is used to destroy the user sessions when they logout. 

### 3. Cloud-based Authentication System
Cloud-based authentication systems helps to securely authenticate, authorize, and manage users across applications. They allow scalability to accommadate for a growing ammount of users can can include multi-factor authentication and enhanced security. In addition, cloud-based authentication services can integrate with other services and applications to manage user access. 

