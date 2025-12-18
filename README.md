# Student Assignment Tracker

A full-stack web application for managing student assignments with comprehensive CRUD operations, data validation, and reporting capabilities.

## Features

### Student Management
- Create, read, update, and delete student records
- Email validation and uniqueness constraints
- View all assignments for individual students

### Assignment Management
- Track assignment titles, due dates, and status
- Date validation (prevents past due dates)
- Update and delete assignments
- View all assignments sorted by due date

### Reporting & Analytics
- Assignments per student report
- Days until due date calculations
- Assignment status tracking
- Student workload overview

## Technical Implementation

### Backend
- **Flask**: Web framework for routing and request handling
- **SQLAlchemy**: ORM for database interactions
- **Marshmallow**: Schema validation and serialization
- **SQLite**: Lightweight database for data persistence

### Database Schema
- **Student Table**: id, name (indexed), email (unique, indexed)
- **Assignment Table**: id, title (indexed), due_date (indexed), status, student_id (foreign key, indexed)
- Optimized with indexes for fast querying and joins

### API Endpoints

#### Students
- `POST /students` - Create new student
- `GET /students` - List all students
- `PUT /students/<id>` - Update student
- `DELETE /students/<id>` - Delete student
- `GET /students/<id>/assignments` - Get student's assignments

#### Assignments
- `POST /assignments` - Create new assignment
- `GET /assignments` - List all assignments
- `PUT /assignments/<id>` - Update assignment
- `DELETE /assignments/<id>` - Delete assignment
- `GET /assignments/all` - View assignments page

#### Reports
- `GET /report/assignments_per_student` - Generate student workload report

### Key Features
- **Data Validation**: Marshmallow schemas ensure data integrity
- **Error Handling**: Comprehensive error responses with rollback
- **Database Indexing**: Optimized queries for performance
- **Prepared Statements**: SQL injection prevention
- **RESTful Design**: Clean, intuitive API structure

## Installation

1. Clone the repository:
```bash
git clone https://github.com/samanthakatovich/student-assignment-tracker.git
cd student-assignment-tracker
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install flask flask-sqlalchemy marshmallow
```

4. Run the application:
```bash
python app.py
```

5. Open your browser to `http://localhost:5000`

## Project Structure
```
student-assignment-tracker/
├── app.py              # Main application file
├── models.py           # Database models
├── templates/          # HTML templates
│   ├── index.html
│   ├── view_assignments.html
│   └── report_assignments_per_student.html
└── students.db         # SQLite database (created on first run)
```

## Technologies Used
- Python 3.x
- Flask
- SQLAlchemy
- Marshmallow
- SQLite
- HTML/CSS
- RESTful API Design

## Future Enhancements
- Add user authentication
- Implement assignment categories/subjects
- Add email notifications for upcoming due dates
- Create student dashboard with analytics
- Export reports to PDF/CSV
```

## Steps to Upload:

1. **Create the repository:**
   - Name: `student-assignment-tracker`
   - Public
   - Add README

2. **Create proper file structure:**
```
   student-assignment-tracker/
   ├── app.py
   ├── models.py
   ├── requirements.txt
   ├── README.md
   └── templates/
       └── (your HTML files here)
```

3. **Create requirements.txt** with:
```
   Flask==3.0.0
   Flask-SQLAlchemy==3.1.1
   marshmallow==3.20.1
```

4. **Upload all files** to the repository

5. **Important:** Add a `.gitignore` file with:
```
   students.db
   __pycache__/
   *.pyc
   venv/
   .env
