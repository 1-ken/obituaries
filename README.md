# Obituary Platform

## Introduction
The Obituary Platform is a web application that allows users to submit and view obituaries. The application is built using Node.js, Express, and MySQL, with HTML and CSS for the front-end.

## Prerequisites
Before setting up the project, ensure you have the following installed:
- [Node.js](https://nodejs.org/) (version 14 or later)
- [MySQL](https://www.mysql.com/)
- A code editor, such as [Visual Studio Code](https://code.visualstudio.com/)

## Setup

### Clone the Repository
```bash
git clone https://github.com/yourusername/obituary-platform.git
cd obituary-platform
```

### Install Dependencies
```bash
npm install
```

### Configure MySQL
1. Create a new MySQL database named `obituary_platform`.
2. Run the following SQL command to create the `obituaries` table:
   ```sql
   CREATE TABLE obituaries (
       id INT AUTO_INCREMENT PRIMARY KEY,
       name VARCHAR(255) NOT NULL,
       date_of_birth DATE NOT NULL,
       date_of_death DATE NOT NULL,
       content TEXT NOT NULL,
       author VARCHAR(255) NOT NULL,
       slug VARCHAR(255) NOT NULL,
       submission_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP
   );
   ```

### Configure Environment Variables
Create a `.env` file in the root directory of the project and add the following environment variables:
```
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=
DB_NAME=obituary_platform
PORT=3000
```

### Start the Application
```bash
npm start
```
The server will run on `http://localhost:3000`.

## Development Process

### Project Structure
The project is structured as follows:
```
/obituary-platform
|-- /public
|   |-- /styles.css
|   |-- /obituary_form.html
|-- app.js
|-- package.json
|-- .env
```

### Key Files
- `app.js`: The main application file that sets up the Express server, connects to MySQL, and defines routes.
- `public/styles.css`: The CSS file for styling the HTML pages.
- `public/obituary_form.html`: The HTML file for the obituary submission form.

### Adding Routes
- **Submit Obituary Form (GET)**: Serves the obituary form to the user.
- **Submit Obituary (POST)**: Handles form submission and stores the data in MySQL.
- **View Obituaries (GET)**: Retrieves and displays all obituaries.

### Middleware
- `body-parser`: Parses incoming request bodies.
- `express.static`: Serves static files from the `public` directory.

### HTML Templates
The HTML templates are defined within the routes for simplicity. This can be refactored to use a templating engine like EJS or Pug for a more scalable solution.

## Usage

### Submitting an Obituary
1. Navigate to `http://localhost:3000/submit_obituary_form`.
2. Fill out the form with the required information.
3. Click the "Submit" button.

### Viewing Obituaries
1. Navigate to `http://localhost:3000/view_obituaries`.
2. View the list of submitted obituaries, displayed as cards with shadows.

### Social Media Sharing
Each obituary card includes links to share the obituary on Facebook and Twitter.

## Folder Structure
```
/obituary-platform
|-- /public
|   |-- /styles.css
|   |-- /obituary_form.html
|-- app.js
|-- package.json
|-- .env
```
