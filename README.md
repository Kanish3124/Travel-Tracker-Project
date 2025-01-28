# ✨ Visited Countries Tracker ✨

This is a web application that allows users to track countries they have visited. Users can add countries by name, and the app updates a list showing all visited countries along with the total count.

## 📚 Features

- 🌎 Track countries you've visited.
- ➕ Add new countries by entering their name.
- 📊 Displays the total number of visited countries.
- ⚠️ Error handling for duplicate entries or invalid country names.

## ⚡ Technologies Used

- **Backend:** Node.js, Express
- **Database:** PostgreSQL
- **Templating Engine:** EJS
- **Middleware:** body-parser

---

## ⚙️ Setup Instructions

### Prerequisites

Ensure you have the following installed:

1. [Node.js](https://nodejs.org/)
2. [PostgreSQL](https://www.postgresql.org/)
3. A `.env` file for environment variables.

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/visited-countries-tracker.git
cd visited-countries-tracker
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Set Up PostgreSQL Database

1. Log in to PostgreSQL:
   ```bash
   psql -U postgres
   ```

2. Create the database:
   ```sql
   CREATE DATABASE visited_countries_db;
   ```

3. Connect to the database:
   ```sql
   \c visited_countries_db;
   ```

4. Create the required tables:
   ```sql
   CREATE TABLE countries (
       country_code VARCHAR(3) PRIMARY KEY,
       country_name VARCHAR(100) NOT NULL
   );

   CREATE TABLE visited_countries (
       id SERIAL PRIMARY KEY,
       country_code VARCHAR(3) REFERENCES countries(country_code)
   );
   ```

5. Populate the `countries` table with data:
   ```sql
   INSERT INTO countries (country_code, country_name) VALUES
   ('USA', 'United States'),
   ('CAN', 'Canada'),
   ('IND', 'India');
   ```

### 4. Configure Environment Variables

Create a `.env` file in the root directory with the following contents:

```env
PG_USER=your_pg_user
PG_HOST=localhost
PG_DATABASE=visited_countries_db
PG_PASSWORD=your_pg_password
PG_PORT=5432
SESSION_SECRET=your_secret_key
```

Replace `your_pg_user`, `your_pg_password`, and `your_secret_key` with your actual PostgreSQL username, password, and a secret key for sessions.

### 5. Start the Application

Run the following command to start the server:

```bash
node app.js
```

The server will be running at [http://localhost:3000](http://localhost:3000).

---

## 🔧 How to Use

1. Open the application in your browser: [http://localhost:3000](http://localhost:3000).
2. Enter the name of a country you have visited and click **Add**.
3. The app will display the country in the list and update the total count.
4. Handle errors such as duplicate entries or invalid country names with the displayed messages.

---

## 🚀 Future Improvements

- Add user authentication to track countries per user.
- Implement search functionality for easier country addition.
- Enhance the UI for a more engaging experience.

---

## ✨ Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

---

## 🛠️ Troubleshooting

If you encounter issues connecting to the database, ensure that:

1. PostgreSQL is running on your machine.
2. The credentials in the `.env` file are correct.
3. The `countries` table is properly populated.

---

## Author 💌

- Created by **Kanish**. :)

---

Enjoy tracking your travels! 🌍✈️
