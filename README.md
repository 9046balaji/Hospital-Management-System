# 🏥 Hospital Appointment System

A simple and easy-to-use web application for managing hospital appointments, patients, doctors, and departments.

---

## 📋 What This App Does

This system helps hospitals manage:

- **📅 Appointments** - Schedule, view, update, and cancel patient appointments
- **👥 Patients** - Add and manage patient information
- **👨‍⚕️ Doctors** - Manage doctor profiles and their departments
- **🏢 Departments** - Organize doctors by medical departments
- **🔐 User Authentication** - Secure login and registration system

---

## 🛠️ Technologies Used

| Category | Technology |
|----------|------------|
| Backend | Node.js, Express.js |
| Database | PostgreSQL |
| Frontend | HTML, CSS, JavaScript, Bootstrap 5 |
| Security | JWT Authentication, Helmet, Rate Limiting |

---

## 📁 Project Structure

```
hospital-appointment/
├── server.js           # Main server file
├── package.json        # Dependencies and scripts
├── .env                # Environment variables (you create this)
├── database/           # SQL files for database setup
├── middleware/         # Authentication middleware
├── models/             # Database models
├── public/             # Frontend files (HTML, CSS, JS)
├── routes/             # API routes
├── scripts/            # Utility scripts
└── tests/              # Test files
```

---

## 🚀 How to Run This Project

### Step 1: Install Node.js

Download and install Node.js from [nodejs.org](https://nodejs.org/)

### Step 2: Install PostgreSQL

Download and install PostgreSQL from [postgresql.org](https://www.postgresql.org/download/)

### Step 3: Clone the Project

```bash
git clone <your-repo-url>
cd hospital-appointment
```

### Step 4: Install Dependencies

```bash
npm install
```

### Step 5: Set Up the Database

1. Open pgAdmin or psql terminal
2. Create a new database:
   ```sql
   CREATE DATABASE hospital_appointment;
   ```
3. Run the SQL file to create tables:
   ```bash
   psql -U your_username -d hospital_appointment -f database/hospital_appointment_pg.sql
   ```
4. (Optional) Create user authentication table:
   ```bash
   psql -U your_username -d hospital_appointment -f database/create_users_table.sql
   ```

### Step 6: Create Environment File

Create a file named `.env` in the root folder with:

```env
# Database Settings
DB_HOST=localhost
DB_PORT=5432
DB_USER=your_postgres_username
DB_PASSWORD=your_postgres_password
DB_NAME=hospital_appointment

# Server Settings
PORT=3000

# Security (generate a random string for JWT_SECRET)
JWT_SECRET=your_secret_key_here
JWT_EXPIRES_IN=24h
```

### Step 7: Start the Application

**For Development (auto-restart on changes):**
```bash
npm run dev
```

**For Production:**
```bash
npm start
```

### Step 8: Open in Browser

Go to: [http://localhost:3000](http://localhost:3000)

---

## 📖 How to Use

### Dashboard
- View summary of appointments, patients, and doctors
- Quick overview of today's schedule

### Patients Page
- Add new patients with name, phone, and email
- View all registered patients
- Edit or delete patient records

### Doctors Page
- Add doctors and assign them to departments
- View all doctors and their specialties
- Manage doctor information

### Appointments Page
- Schedule new appointments
- Select patient, doctor, date, and time
- View, update, or cancel appointments
- Check appointment conflicts automatically

### Admin Section
- Manage departments
- User settings and preferences

---

## 🔌 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| **Departments** | | |
| GET | `/api/departments` | Get all departments |
| POST | `/api/departments` | Create new department |
| PUT | `/api/departments/:id` | Update department |
| DELETE | `/api/departments/:id` | Delete department |
| **Patients** | | |
| GET | `/api/patients` | Get all patients |
| POST | `/api/patients` | Add new patient |
| PUT | `/api/patients/:id` | Update patient |
| DELETE | `/api/patients/:id` | Delete patient |
| **Doctors** | | |
| GET | `/api/doctors` | Get all doctors |
| POST | `/api/doctors` | Add new doctor |
| PUT | `/api/doctors/:id` | Update doctor |
| DELETE | `/api/doctors/:id` | Delete doctor |
| **Appointments** | | |
| GET | `/api/appointments` | Get all appointments |
| POST | `/api/appointments` | Create appointment |
| PUT | `/api/appointments/:id` | Update appointment |
| DELETE | `/api/appointments/:id` | Cancel appointment |
| **Authentication** | | |
| POST | `/api/auth/register` | Register new user |
| POST | `/api/auth/login` | Login user |

---

## 🧪 Running Tests

```bash
npm test
```

---

## 📝 Available Scripts

| Command | What it does |
|---------|--------------|
| `npm start` | Start the server |
| `npm run dev` | Start with auto-reload (development) |
| `npm test` | Run tests |
| `npm run lint` | Check code quality |
| `npm run format` | Format code automatically |

---

## 🔒 Security Features

- **Password Hashing** - Passwords are encrypted using bcrypt
- **JWT Tokens** - Secure authentication tokens
- **Rate Limiting** - Prevents too many requests (100 per 15 minutes)
- **Helmet** - Adds security headers
- **CORS** - Controls which websites can access the API

---

## 🗄️ Database Tables

| Table | Purpose |
|-------|---------|
| `departments` | Hospital departments (Cardiology, Pediatrics, etc.) |
| `patients` | Patient information (name, phone, email) |
| `doctors` | Doctor profiles linked to departments |
| `appointments` | Scheduled appointments with status |
| `users` | User accounts for login |

---

## ❓ Common Issues

### "Cannot connect to database"
- Make sure PostgreSQL is running
- Check your `.env` file has correct database credentials

### "Port 3000 already in use"
- Change `PORT` in `.env` file to another number (e.g., 3001)

### "Missing environment variables"
- Make sure you created the `.env` file
- Copy from `.env.example` if available

---

## 👨‍💻 Contributing

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Make your changes
4. Commit (`git commit -m 'Add some feature'`)
5. Push (`git push origin feature/your-feature`)
6. Open a Pull Request

---

## 📄 License

ISC License

---

## 🙋 Need Help?

If you have questions or run into issues:
1. Check the "Common Issues" section above
2. Look at existing issues in the repository
3. Create a new issue with details about your problem

---

**Made with ❤️ for better healthcare management**
