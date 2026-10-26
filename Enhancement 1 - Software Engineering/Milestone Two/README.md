# Grazioso Salvare Animal Shelter Dashboard

CS 499 Milestone Two: Software Design and Engineering

## Project Overview

This project enhances the original CS 340 animal shelter dashboard by converting it into a standalone Dash application. Improvements include reorganized application components, staff authentication, input validation, and a more accessible interface for managing and analyzing animal shelter records.

## Live Dashboard

The enhanced dashboard is deployed on Render and can be accessed without installing any software.

GitHub Repository:
https://github.com/JenniferJSNHU/Grazioso-Salvare-Dashboard-Milestone-Two

Dashboard URL:
https://grazioso-salvare-dashboard-milestone-two.onrender.com/

**Staff Login**
- Username: staff
- Password: Butters

The hosted dashboard connects to MongoDB Atlas and includes the animal shelter records needed to evaluate the application.

Note: The dashboard may take 1–2 minutes to load if the Render service has been inactive.

## Requirements

- Python 3
- MongoDB Community Server
- MongoDB Compass

## Local Setup

### 1. Install Dependencies

Open a terminal in the project folder and run:

    py -m pip install -r requirements.txt

### 2. Import the Database

The `data/animals.json` file contains 10,000 animal shelter records.

1. Start MongoDB Community Server.
2. Open MongoDB Compass.
3. Connect to `mongodb://localhost:27017/`.
4. Create a database named `aac`.
5. Create a collection named `animals`.
6. Open the collection and select Add Data > Import JSON or CSV file.
7. Select `data/animals.json` and import it as JSON.
8. Confirm that 10,000 records were imported.

### 3. Configure Staff Authentication

The submission ZIP includes a `.env` file with the local staff authentication configuration.

Generate a new password hash using:

    py -c "from getpass import getpass; from werkzeug.security import generate_password_hash; print(generate_password_hash(getpass('Staff password: ')))"

Update `.env` with the following values:

    GRAZIOSO_STAFF_USER=staff
    GRAZIOSO_STAFF_PASSWORD_HASH=YOUR_GENERATED_HASH
    MONGODB_URI=mongodb://localhost:27017/

Replace `YOUR_GENERATED_HASH` with the newly generated hash.

### 4. Run the Dashboard

Start the application:

    py app.py

Open http://127.0.0.1:8052 in a browser.

Sign in using the configured staff credentials.

## Software Design and Engineering Enhancements

- Converted the original Jupyter Notebook dashboard into a standalone Python application.
- Separated database operations, application logic, and interface components.
- Added server-side staff authentication using password hashing.
- Improved input validation and handling of animal records.
- Reorganized the dashboard interface for easier navigation.
- Added automated tests to verify application functionality.