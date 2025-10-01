# Project Setup Instructions

Follow these steps to get the app running on your computer.

### Prerequisites

Before you start, make sure you have installed:

1.  **Node.js**: [Download from nodejs.org](https://nodejs.org/en/download/)
2.  **MySQL Community Server & Workbench**: [Download from mysql.com](https://dev.mysql.com/downloads/installer/). (During installation, remember the password you set for the 'root' user).

### Step 1: Set Up the Database (First Time Launch)

1.  Open MySQL Workbench. On the first launch, it will ask you to set a password for the `root` user. **Choose a password and save it somewhere secure. You will need it later.**
2.  On the main screen, you will see a "Local instance" connection. Double-click it to connect to your database server. It will ask for the password you just created.
3.  Once connected, you will see a window with a "Schemas" panel on the left. To create a new database, click the **"create a new schema" icon** (a cylinder with a '+') in the toolbar at the top.
4.  A new tab will open. For the "Name", type `my_app_db`.
5.  Click the **"Apply"** button on the bottom right. A window will pop up showing the SQL command. Click "Apply" again to confirm. You should now see `my_app_db` in the Schemas list on the left.
6.  Go back to the project folder and open the `database_setup.sql` file in any text editor.
7.  Copy the entire content of the file.
8.  Go back to MySQL Workbench, click `File > New Query Tab`.
9.  Paste the entire copied script into this new query tab.
10. Click the **first lightning bolt icon** (the one without the cursor) in the toolbar to execute the entire script. This will create all the tables and add all the sample data.

### Step 2: Set Up the Backend Server

1.  Open your computer's terminal (Command Prompt or PowerShell on Windows, Terminal on Mac).
2.  Navigate to the project folder using the `cd` command. Example: `cd C:\Users\YourName\Desktop\aol se`
3.  Run the following command to install all the required packages:
    ```bash
    npm install
    ```
4.  **IMPORTANT:** Open the `server.js` file in a text editor (like VS Code or Notepad). Find this section and replace `'YOUR_MYSQL_PASSWORD'` with the actual MySQL root password you created in Step 1.
    ```javascript
    const dbPool = mysql.createPool({
        host: 'localhost',
        user: 'root',
        password: 'YOUR_MYSQL_PASSWORD', // <-- REPLACE THIS
        database: 'my_app_db',
        //...
    });
    ```
5.  Save the `server.js` file.

### Step 3: Run the Application

1.  In your terminal (while still in the project folder), run this command to start the server:
    ```bash
    node server.js
    ```
2.  You should see the message: `Server is running on http://localhost:3000`.
3.  Open your web browser and go to this address to start:
    **http://localhost:3000/login.html**

That's it! The application should now be fully functional.
