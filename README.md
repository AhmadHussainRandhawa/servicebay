# Services - Django Web Application

## Introduction
Welcome to **Services**, a Django-based web application that allows users to browse and manage services, reviews, and certificates with ease. This project was built as part of my Django learning journey, combining models, views, templates, and Tailwind CSS for a functional and polished application.

[Check out the live demo here!](https://ahmadhussain.pythonanywhere.com)

---

## Features
- **Browse Services**: Explore a list of services with detailed descriptions.
- **Filter by Stores**: Easily filter services by store locations.
- **Manage Reviews**: Add and view reviews for services.
- **Certificates**: Access certificates associated with services.
- **Admin Panel**: Manage the database efficiently through a customized Django admin panel.

---

## Tech Stack
- **Backend**: Django
- **Frontend**: HTML, Tailwind CSS
- **Database**: SQLite (default for development)
- **Deployment**: Hosted on [PythonAnywhere](https://www.pythonanywhere.com)

---

## Installation and Setup

### Prerequisites
Ensure you have the following installed on your system:
- Python (3.8+)
- Git
- A code editor (e.g., VS Code)

### Steps
1. Clone the Repository:
   ```bash
   git clone git@github.com:AhmadHussainRandhawa/Coding-Services.git
   cd services
   ```

2. Create a Virtual Environment:
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # Linux/MacOS
   .venv\Scripts\activate    # Windows
   ```

3. Install Dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Apply Migrations:
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

5. Run the Server:
   ```bash
   python manage.py runserver
   ```

6. Access the App:
   Open your browser and go to `http://127.0.0.1:8000/`.

---

## Deployment on PythonAnywhere

### Steps to Deploy:
1. Push your code to GitHub.
2. Log in to [PythonAnywhere](https://www.pythonanywhere.com/).
3. Open a **Bash Console** and clone your repository:
   ```bash
   git clone <repository_url>
   cd services
   ```
4. Set up your virtual environment:
   ```bash
   python -m venv .venv
   source .venv/bin/activate
   pip install -r requirements.txt
   ```
5. Configure WSGI:
   - Go to **Web** section in PythonAnywhere.
   - Set your **Working Directory** to `/home/yourusername/services/`.
   - Set your **WSGI file** to point to `services/wsgi.py`.
   
6. Restart the web app to apply changes.

---

## Project Structure

```
my_project
├── db.sqlite3
├── manage.py
├── media
│   └── services
├── my_project
│   ├── asgi.py
│   ├── __init__.py
│   ├── __pycache__
│   ├── settings.py
│   ├── urls.py
│   ├── views.py
│   └── wsgi.py
├── requirements.txt
├── services
│   ├── admin.py
│   ├── apps.py
│   ├── forms.py
│   ├── __init__.py
│   ├── migrations
│   ├── models.py
│   ├── __pycache__
│   ├── templates
│   ├── tests.py
│   ├── urls.py
│   └── views.py
├── static
│   └── style.css
├── templates
│   ├── layout.html
│   └── website
└── theme
    ├── apps.py
    ├── __init__.py
    ├── __pycache__
    ├── static
    ├── static_src
    └── templates
```

---

## Future Enhancements

- **Real Services**: Transition from showcasing service descriptions to offering real, functional services directly on the platform.  
- **User Authentication**: Add authentication for personalized features and user accounts.  
- **Improved Reviews**: Enhance the review system with star ratings and additional feedback options.  
- **Advanced Search**: Implement advanced search and filtering for easier navigation.  
- **Home Page Redesign**: Plan to make the home page more visually engaging and user-friendly.  

---

## Contributing
Contributions are welcome! If you'd like to make improvements, follow these steps:
1. Fork the repository.
2. Create a new branch for your feature:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. Commit your changes and push them:
   ```bash
   git commit -m "Add your feature description"
   git push origin feature/your-feature-name
   ```
4. Open a pull request.

---

## Contact
If you have any questions or feedback, feel free to reach out:   

[<img src="https://img.icons8.com/3d-fluency/30/secured-letter.png" alt="Email" style="vertical-align: middle;"/> official.ahmadrandhawa@gmail.com](mailto:official.ahmadrandhawa@gmail.com)   
[<img src="https://icon.icepanel.io/Technology/svg/GitHub.svg" width="26" alt="GitHub"/> My GitHub Profile](https://github.com/AhmadHussainRandhawa)   
[<img src="https://icon.icepanel.io/Technology/svg/LinkedIn.svg" width="26" alt="LinkedIn"/>  Ahmad Hussain](https://www.linkedin.com/in/ahmad-hussain-randhawa/)

---

> "Start falling in love with errors instead of girls." 😎
