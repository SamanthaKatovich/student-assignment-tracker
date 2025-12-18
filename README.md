# Student Assignment Tracker

A full-stack web application for managing student assignments with comprehensive CRUD operations, data validation, and reporting capabilities.

![Student Tracker](https://img.shields.io/badge/Python-3.9+-blue.svg)
![Flask](https://img.shields.io/badge/Flask-3.0.0-green.svg)

## Features

### 📚 Student Management
- Create, read, update, and delete student records
- Email validation with uniqueness constraints
- Real-time form validation and error handling
- View all assignments for individual students

### 📝 Assignment Management
- Track assignment titles, due dates, and status
- Date validation (prevents creating assignments with past due dates)
- Student dropdown selection for easy assignment creation
- Update and delete assignments with confirmation dialogs
- View all assignments sorted by due date

### 📊 Reporting & Analytics
- **Assignments per Student Report**: Comprehensive overview of each student's workload
- **Days Until Due Calculation**: Automatic calculation of time remaining
- **Overdue Tracking**: Visual highlighting of overdue assignments
- **Assignment Status Monitoring**: Track completion status across students

## Screenshots

### Main Dashboard
The main interface allows you to create students and assignments, with real-time validation and Bootstrap styling.

### Assignment Report
View a detailed breakdown of assignments per student with due date calculations and overdue indicators.

## Technical Implementation

### Backend Architecture
- **Flask**: Lightweight web framework for routing and request handling
- **SQLAlchemy ORM**: Database abstraction and relationship management
- **Marshmallow**: Advanced schema validation and serialization
- **SQLite**: Embedded database for data persistence

### Database Schema

**Student Table**
```
- id (Primary Key, Integer)
- name (String, Indexed)
- email (String, Unique, Indexed)
```

**Assignment Table**
```
- id (Primary Key, Integer)
- title (String, Indexed)
- due_date (Date, Indexed)
- status (String)
- student_id (Foreign Key → Student, Indexed)
```

**Performance Optimizations**
- Strategic indexes on frequently queried columns (name, email, due_date)
- Foreign key indexing for efficient joins
- Prepared SQL statements for complex queries

### API Endpoints

#### Students
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/students` | Create new student |
| GET | `/students` | List all students |
| PUT | `/students/<id>` | Update student |
| DELETE | `/students/<id>` | Delete student |
| GET | `/students/<id>/assignments` | Get student's assignments |

#### Assignments
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/assignments` | Create new assignment |
| GET | `/assignments` | List all assignments |
| PUT | `/assignments/<id>` | Update assignment |
| DELETE | `/assignments/<id>` | Delete assignment |
| GET | `/assignments/all` | View assignments page |

#### Reports & Utilities
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/report/assignments_per_student` | Generate workload report |
| GET | `/dropdown/students` | Get students for dropdown |

### Key Features

✅ **Data Validation**
- Marshmallow schemas ensure data integrity
- Email uniqueness validation
- Future date validation for assignments
- Required field validation

✅ **Error Handling**
- Comprehensive error responses with details
- Database rollback on validation errors
- User-friendly error messages
- Graceful handling of not-found resources

✅ **Security**
- Prepared statements prevent SQL injection
- Input sanitization through Marshmallow
- Foreign key constraints maintain referential integrity

✅ **User Experience**
- Bootstrap-styled responsive interface
- Real-time form validation feedback
- Confirmation dialogs for destructive actions
- Success/error message display
- Automatic list refresh after operations

## Installation & Setup

### Prerequisites
- Python 3.9 or higher
- pip package manager

### Step 1: Clone the Repository
```bash
git clone https://github.com/samanthakatovich/student-assignment-tracker.git
cd student-assignment-tracker
```

### Step 2: Create Virtual Environment
```bash
# On macOS/Linux
python3 -m venv venv
source venv/bin/activate

# On Windows
python -m venv venv
venv\Scripts\activate
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Run the Application
```bash
python app.py
```

### Step 5: Access the Application
Open your browser and navigate to:
```
http://localhost:5000
```

## Usage Guide

### Creating a Student
1. Enter student name and email in the form
2. Click "Add Student"
3. Student appears in the list below

### Creating an Assignment
1. Enter assignment title
2. Select due date (must be in the future)
3. Enter status (e.g., "Pending", "Completed")
4. Select student from dropdown
5. Click "Add Assignment"

### Viewing Reports
1. Click "View Assignments per Student Report"
2. See workload breakdown by student
3. View days until due for each assignment
4. Overdue assignments are highlighted in red

### Editing Records
- Click "Edit" button next to any student or assignment
- Enter new information in the prompt
- Changes are saved automatically

### Deleting Records
- Click "Delete" button next to any student or assignment
- Confirm deletion in the dialog
- Record is removed from database

## Project Structure
```
student-assignment-tracker/
├── app.py                  # Main Flask application
├── models.py               # SQLAlchemy database models
├── requirements.txt        # Python dependencies
├── README.md              # Project documentation
├── .gitignore             # Git ignore rules
└── templates/             # HTML templates
    ├── index.html                          # Main dashboard
    ├── assignments.html                    # Assignment management
    ├── students.html                       # Student list view
    ├── view_assignments.html               # All assignments view
    └── report_assignments_per_student.html # Report page
```

## Technologies Used

**Backend**
- Python 3.9+
- Flask 3.0.0
- SQLAlchemy (ORM)
- Marshmallow (Validation)
- SQLite (Database)

**Frontend**
- HTML5
- CSS3
- JavaScript (ES6+)
- Bootstrap 4.5.2
- Fetch API for AJAX

**Architecture Patterns**
- RESTful API design
- MVC pattern
- ORM for database abstraction
- Schema-based validation

## Future Enhancements

- [ ] User authentication and authorization
- [ ] Assignment categories/subjects
- [ ] Email notifications for upcoming due dates
- [ ] Student dashboard with personal analytics
- [ ] Export reports to PDF/CSV
- [ ] Assignment priority levels
- [ ] Search and filter functionality
- [ ] Bulk operations (import/export students)
- [ ] Assignment templates
- [ ] Calendar view for due dates

## Learning Outcomes

This project demonstrates proficiency in:
- Full-stack web development
- RESTful API design and implementation
- Database design and optimization
- Data validation and error handling
- Frontend-backend integration
- CRUD operations
- SQL query optimization
- User interface design

## Contributing

This is a personal portfolio project, but feedback and suggestions are welcome!

## License

This project is open source and available for educational purposes.

## Contact

**Samantha Katovich**
- Email: samanthakatovich@gmail.com
- GitHub: [@samanthakatovich](https://github.com/samanthakatovich)
- Portfolio: [samanthakatovich.github.io](https://samanthakatovich.github.io)

---
