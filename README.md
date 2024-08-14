# JWT Authentication

## Overview

This project demonstrates the implementation of JSON Web Token (JWT) based authentication in a Django application. It provides secure login, registration, password reset via email, and token-based authentication mechanisms, ensuring that only authorized users can access protected resources.


## Features

- **User Registration:** Allows users to create an account.
- **User Login:** Generates a JWT token upon successful login.
- **Password Reset via Email:** Allows users to reset their password using an email link.
  ![password reset mail](https://github.com/Sudham4444/jwt_authentication/blob/main/password_reset_mail.png)
- **Token Authentication:** Protects API endpoints using JWT tokens.
- **Token Refresh:** Provides a mechanism to refresh JWT tokens.
- **Protected Routes:** Access control for specific API endpoints using token authentication.

## Installation

### Prerequisites

- Python 3.12.4 (recommended)
- Django 4.2.2 or higher (5.1 recommended)
- Django Rest Framework
- SimpleJWT
- Virtual Environment (recommended)

### Steps to Set Up

1. **Clone the Repository**

   ```bash
   git clone https://github.com/Sudham4444/jwt_authentication.git

2. **Navigate to the Project Directory**

   ```bash
   cd jwt_authentication

3. **Create and Activate a Virtual Environment**

    ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`

4. **Install Dependencies**

   ```bash
   pip install -r requirements.txt

5. **Apply Database Migrations**

    ```bash
    python manage.py migrate

6. **Create a Superuser (Optional, for admin access)**

    ```bash
    python manage.py createsuperuser

7. **Run the Development Server**

    ```bash
    python manage.py runserver

8. **Access the Application**

    Open your web browser and go to http://127.0.0.1:8000/admin/ for the admin interface.

## Configuration
  `JWT Settings:` The JWT settings can be configured in settings.py to customize the token lifetime, refresh behavior, and other options.

  `Database:` This project uses SQLite by default. You can configure a different database in settings.py if needed.

  `Email Settings:` Configure the email backend in settings.py to enable password reset via email. For example, you can use SMTP with Gmail or any other email service provider.

## API Testing with Postman
### Importing the Postman Collection
1. Download the Postman Collection File

    Ensure that the Postman collection file is available in your project repository. You can add it to the root directory of your project or a dedicated postman/ folder.

2. Import the Collection into Postman

    Open Postman.
   
    Click on the "Import" button in the top left corner.
   
    Choose the file option and select the Postman collection file (e.g., djangojwtauthapi.postman_collection.json).
   
    Click "Import."
   
3. Use the Collection

    Once imported, you'll see the collection in your Postman app.
   
    You can now test the API endpoints as defined in the collection.
   
## Manual API Testing
If you prefer to manually test the API endpoints, follow these steps:

1. User Registration

    - **Method:** POST
   
    - **URL:** http://127.0.0.1:8000/api/user/resgister/
   
    - **Body:** Send JSON data with username, password, email and all necessary fields.
  
2. User Login

    - **Method:** POST

    - **URL:** http://127.0.0.1:8000/api/user/login/
   
    - **Body:** Send JSON data with username and password fields.
   
    - **Response:** You will receive an access token and a refresh token.
  
3. Access Protected Endpoints

    - **Method:** GET (or other HTTP methods depending on the endpoint)
   
    - **URL:** http://127.0.0.1:8000/api/user/profile/
   
    - **Header:** Include the JWT token in the Authorization header as Bearer <access_token>.

4. Token Refresh

    - **Method:** POST
   
    - **URL:** http://127.0.0.1:8000/api/token/refresh/
   
    - **Body:** Send JSON data with the refresh token to obtain a new access token.

## Deployment
   To deploy this application, follow the platform-specific deployment instructions. Ensure that you have configured the environment variables and database settings as needed.

## Contributing
   Contributions are welcome! Please fork the repository and create a pull request with your proposed changes.

## License
   This project is licensed under the MIT License. See the LICENSE file for details.

## Contact
   For any questions or issues, please contact at sudhamsingh2412@gmail.com
