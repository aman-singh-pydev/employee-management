# Employee Management API (Django REST Framework)

A simple and clean Employee Management REST API built using Django and Django REST Framework (DRF).  
Supports full CRUD operations with validation and a modular, extensible project architecture.

---

## Features

- CRUD operations for employee records  
- DRF ModelSerializer with validation  
- REST API using DRF ViewSets and Routers  
- SQLite database (development)  
- Clean project structure  
- Easily extendable for authentication, RBAC, pagination, etc.

---

## Tech Stack

- Python 3.x  
- Django 5.x  
- Django REST Framework  
- SQLite  
- Virtual Environment (venv)

-----------------------------------

## Project Structure
```
employee-management/
│
├── employee_mgmt/
│ ├── init.py
│ ├── settings.py
│ ├── urls.py
│ ├── wsgi.py
│ └── asgi.py
│
├── employees/
│ ├── init.py
│ ├── admin.py
│ ├── apps.py
│ ├── models.py
│ ├── serializers.py
│ ├── views.py
│ ├── urls.py
│ └── migrations/
│
├── db.sqlite3
├── manage.py
└── README.md
```
-----------------------------------

## API Endpoints

| Method | Endpoint               | Description              |
|--------|-------------------------|---------------------------|
| GET    | `/api/employees/`      | List all employees        |
| POST   | `/api/employees/`      | Create a new employee     |
| GET    | `/api/employees/{id}/` | Retrieve employee by ID   |
| PUT    | `/api/employees/{id}/` | Update employee details   |
| PATCH  | `/api/employees/{id}/` | Partial update            |
| DELETE | `/api/employees/{id}/` | Delete employee           |

-----------------------------------

## Installation & Setup

1. **Clone the repository**

   ```
   git clone https://github.com/aman-singh-pydev/employee-management.git
   cd employee-management
   
2. **Create & activate a virtual environment**
   ```
   python -m venv venv
   venv\Scripts\activate
3. **Install dependencies**
   ```
   pip install -r requirements.txt
4. **Apply migrations**
   ```
   python manage.py migrate
5. **Run the development server**
   ```
   python manage.py runserver
-----------------------------------

**API Base URL**
```
http://127.0.0.1:8000/api/employees/
```
-----------------------------------

**Model Structure**
```
class Employee(models.Model):
    name = models.CharField(max_length=100)
    email = models.EmailField(unique=True)
    designation = models.CharField(max_length=100)
    salary = models.DecimalField(max_digits=10, decimal_places=2)
    date_joined = models.DateField(auto_now_add=True)
```
-----------------------------------

**Serializer**
```
class EmployeeSerializer(serializers.ModelSerializer):
    class Meta:
        model = Employee
        fields = '__all__'
```
-----------------------------------

**ViewSet**
```
class EmployeeViewSet(viewsets.ModelViewSet):
    queryset = Employee.objects.all()
    serializer_class = EmployeeSerializer
```
-----------------------------------

**Router Configuration**
```
router = DefaultRouter()
router.register(r'employees', EmployeeViewSet)

urlpatterns = router.urls
```
-----------------------------------

## Future Enhancements

- Authentication (JWT / session-based)

- Role-based access control (RBAC)

- Pagination and filtering

- Logging and monitoring

- Frontend integration (React/Angular/Vue)

- Switch to PostgreSQL for production

-----------------------------------

**Author**

Aman Singh

Python Developer

GitHub: https://github.com/aman-singh-pydev


   
