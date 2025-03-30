# Smart Travel Planner

The **Smart Travel Planner** is a web-based application built using **Streamlit** and **MongoDB**. It simplifies and enhances the process of planning and managing trips by providing an intuitive interface for creating, customizing, and managing travel itineraries. The application also includes a backup database for high availability and data redundancy.

---

## Features

### 1. **User Authentication**
- Secure user registration, login, and logout functionality.
- Passwords are hashed using SHA-256 for enhanced security.

### 2. **Trip Management (CRUD Operations)**
- Create, view, update, and delete trips.
- Each trip includes:
  - Trip Name
  - Destination
  - Start Date and End Date
  - Itinerary (list of activities with time and location)
  - A flag to mark the trip as a "solo trip."

### 3. **Itinerary Management**
- Add, update, and delete itinerary items dynamically for each trip.
- Itinerary items include activity details, time, and location.

### 4. **Dashboard**
- Displays all trips for the logged-in user in an organized format.
- Shows trip details, including the itinerary and whether it is a solo trip.
- Aggregated data, such as the number of trips grouped by destination, is also displayed.

### 5. **Aggregation**
- MongoDB aggregation pipelines are used to compute and display:
  - The number of trips grouped by destination.
  - Other potential metrics, such as trips grouped by year or average trip duration.

### 6. **Backup Database**
- A secondary MongoDB instance is configured as a backup.
- If the primary database connection fails, the application automatically switches to the backup database to ensure high availability.

### 7. **Indexing**
- MongoDB indexes are created on key fields for optimized query performance:
  - `username` in the `users` collection (unique index).
  - `destination` and `start_date` in the `trips` collection.

---

## Project Structure
smart-travel-planner/
│
├── app.py               # Main Streamlit application
├── auth.py              # User authentication logic
├── crud.py              # CRUD operations for trips and itineraries
├── db.py                # MongoDB connection and backup handling
├── utils.py             # Helper functions for displaying data
├── requirements.txt     # Python dependencies
└── README.md            # Project documentation
