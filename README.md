# Capital City Quiz

This is a simple web application built with Node.js, Express.js, and PostgreSQL that quizzes users on capital cities.

## Features

-   Displays a random country and prompts the user to enter its capital.
-   Tracks the user's score.
-   Provides visual feedback on correct/incorrect answers.
-   Restarts the quiz after an incorrect answer.
-   Data is stored and retrieved from a PostgreSQL database.

## Technologies Used

-   Node.js
-   Express.js
-   PostgreSQL
-   EJS (Embedded JavaScript templates)
-   CSS

## Prerequisites

-   Node.js and npm installed
-   PostgreSQL installed and running
-   A PostgreSQL database named `world` with a table named `capitals` (see database setup below).

## Database Setup

1.  Create a database named `world`.
2.  Create a table named `capitals` with the following schema:

    ```sql
    CREATE TABLE capitals (
        country VARCHAR(255) NOT NULL,
        capital VARCHAR(255) NOT NULL
    );
    ```

3.  Populate the `capitals` table with country and capital data. For example:

    ```sql
    INSERT INTO capitals (country, capital) VALUES
    ('France', 'Paris'),
    ('United Kingdom', 'London'),
    ('United States of America', 'New York');
    -- Add more countries and capitals as needed
    ```

## Installation

1.  Clone the repository:

    ```bash
    git clone https://github.com/Hamish404/World-Capital-Quiz/
    cd Hamish404/World-Capital-Quiz/
    ```

2.  Install dependencies:

    ```bash
    npm install
    ```

3.  Configure your PostgreSQL database connection in the `index.js` file:

    ```javascript
    const db = new pg.Client({
      user: "postgres",
      host: "localhost",
      database: "world",
      password: "123456", // Replace with your password
      port: 5432
    });
    ```

4.  Run the application:

    ```bash
    node index.js
    ```

5.  Open your browser and navigate to `http://localhost:3000`.

## Usage

1.  Enter the capital city in the input field.
2.  Click "SUBMIT" to check your answer.
3.  The score will be updated, and a new question will be displayed.
4.  If you answer incorrectly, the game will restart.
