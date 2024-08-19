# Django API Project

## Overview

This project is a Django-based API with JWT authentication. It includes endpoints for user registration, authentication, token management, and testing.

## Features

- **User Registration**: Create a new user with email and password.
- **Authentication**: Obtain a JWT token for authenticated requests.
- **Token Refresh**: Refresh JWT tokens before they expire.
- **Token Revocation**: Revoke JWT tokens (if implemented).
- **Protected Endpoints**: Access protected endpoints using JWT tokens.

## Prerequisites

- Python 3.x
- Django
- Django REST Framework
- Django REST Framework Simple JWT

## Installation

1. **Clone the repository:**
```bash
git clone https://github.com/yourusername/your-repository.git
cd your-repository
```
2. Create and activate a virtual environment:

```bash
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```
3. **Install dependencies:**

```bash
pip install -r requirements.txt
```
4. Apply migrations:
 ```bash
python manage.py migrate
```
5. Create a superuser (optional, for admin access):
 ```bash
python manage.py createsuperuser
```
6. Start the development server:
```bash
python manage.py runserver
The server will be available at http://localhost:8000.
```
## API Endpoints
1. **Sign Up (User Registration)**
- Endpoint: POST /api/register/
- Data: email=user@example.com&password=yourpassword
- Description: Creates a new user.
2. **Sign In (Obtain Token)**
- Endpoint: POST /api/token/
- Data: email=user@example.com&password=yourpassword
- Description: Authenticates the user and returns a JWT token.
3. **Test Endpoint with Token Authorization**
- Endpoint: GET /api/test/
- Headers: Authorization: Bearer YOUR_JWT_TOKEN
- Description: Access protected endpoint using JWT token.
4. **Refresh Token**
- Endpoint: POST /api/token/refresh/
- Data: refresh=YOUR_REFRESH_TOKEN
- Description: Refreshes the JWT token.
5. **Revoke Token (If implemented)**
- Endpoint: POST /api/token/revoke/
- Headers: Authorization: Bearer YOUR_JWT_TOKEN
- Description: Revokes the JWT token.

## Example curl Commands
Sign Up:
```bash
curl -X POST http://localhost:8000/api/register/ -d "email=user@example.com&password=yourpassword"
```
Sign In:
```bash
curl -X POST http://localhost:8000/api/token/ -d "email=user@example.com&password=yourpassword"
```
Test Endpoint:
```bash
curl -H "Authorization: Bearer YOUR_JWT_TOKEN" http://localhost:8000/api/test/
```
Refresh Token:
```bash
curl -X POST http://localhost:8000/api/token/refresh/ -d "refresh=YOUR_REFRESH_TOKEN"
```
Revoke Token:
```bash
curl -X POST http://localhost:8000/api/token/revoke/ -H "Authorization: Bearer YOUR_JWT_TOKEN"
```
Contributing
Feel free to fork the repository and submit pull requests. If you encounter any issues or have feature requests, please open an issue on GitHub.

License
This project is licensed under the MIT License. See the LICENSE file for details.

