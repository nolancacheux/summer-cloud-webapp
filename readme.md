# Summer Cloud

Summer Cloud is a self-hosted cloud storage solution built with Django, providing users with a personal file management system similar to Google Drive or OneDrive. The application offers a clean, responsive web interface for managing files and folders with secure user authentication and storage limitations.

## Features

### Core Functionality
- **User Authentication**: Secure registration and login system with personalized user spaces
- **File Management**: Upload, download, move, and copy files with ease
- **Folder Organization**: Create nested folder structures to organize content
- **Storage Limits**: 
  - Maximum storage per user: 100 MB
  - Maximum file upload size: 40 MB
- **File Type Detection**: Automatic categorization of files (images, documents, videos, audio, others)
- **Responsive Design**: Built with Tailwind CSS for optimal viewing on desktop and mobile devices
- **User Statistics**: Visual dashboard showing storage usage and file distribution by type

### Technical Features
- **Django 5.1.2**: Modern Python web framework
- **SQLite Database**: Lightweight database with demo data included
- **Docker Support**: Easy deployment with Docker Compose
- **Tailwind CSS**: Utility-first CSS framework for responsive design
- **File System Storage**: Direct server file system storage for simplicity

## Technology Stack

- **Backend**: Django 5.1.2, Python
- **Frontend**: HTML, Tailwind CSS, JavaScript
- **Database**: SQLite3
- **Containerization**: Docker, Docker Compose
- **CSS Processing**: PostCSS, Autoprefixer
- **Forms**: Django Crispy Forms

## Project Structure

```
SummerCloud-production/
├── SummerCloud/          # Main Django project settings
├── drive/                # Core application module
│   ├── models.py        # File and Folder data models
│   ├── views.py         # Application logic and controllers
│   ├── forms.py         # Upload and folder creation forms
│   ├── templates/       # HTML templates
│   └── migrations/      # Database migrations
├── static/              # Static files (CSS, JS)
├── requirements.txt     # Python dependencies
├── package.json         # Node.js dependencies
├── docker-compose.yml   # Docker configuration
└── manage.py           # Django management script
```

## Team
- Nathan Eudeline
- Cyprien Kelma
- Paul Pousset
- Nolan Cacheux

## Installation

### Standard Installation

```bash
# Create and activate virtual environment
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install Python dependencies
pip install -r requirements.txt

# Install Node.js dependencies for Tailwind CSS
npm install

# Build CSS
npm run build

# Run database migrations
python3 manage.py migrate

# Start the development server
python3 manage.py runserver
```

### Docker Installation

```bash
docker-compose up
```

The application will be available at `http://localhost:8000`

## Usage

### Demo Account

A demo user account is pre-configured in the provided SQLite database:

```
Username: bafbi
Password: TyTbfc%G#lCZL4
```

Sample files are included in the media folder for testing purposes.

### Development Mode

For active development with automatic CSS rebuilding:

```bash
# Terminal 1: Run Django server
source venv/bin/activate
python3 manage.py runserver

# Terminal 2: Watch for CSS changes
npm run watch
```

## Configuration

### Environment Variables
Create a `.env` file in the project root (copy from `.env.example` if available) to configure:
- Secret key
- Debug mode
- Database settings
- Media file paths

### Storage Limits
Storage limits are configured in `drive/views.py`:
- `MAX_FILE_SIZE`: 40 MB per file
- `MAX_STORAGE_SIZE`: 100 MB per user

## Project

**Ouvert le :** jeudi 17 octobre 2024, 12:00

**À rendre :** vendredi 8 novembre 2024, 23:59

### Description

Develop a Cloud Drive application (similar to Google Drive and OneDrive) using Django. To make the project simpler, the files will be stored on the server. The base folder of each user will be his login.

The tool can also work on local storage in replacement of File Explorer.

For example, if there are two users "foo" and "bar" that have uploaded some files, the file structure on the server will be simialr to this one:


- ***base\_server\_folder/*** (root)
  - *foo/* (user1)
    - **file1.txt**
    - *images/*
      - **eiffel tower.png**
  - *bar/* (user2)
    - **bread recipe.pdf**
    - *2024/*
    - **python lecture.pfg**

### Features

The web application will provide the maximum of the following features:

[x] Authentication and account creation with login and password

[x] Browse files and folders on a web UI

[X] Display file properties and file metadata

[x] Upload files

[x] Create folders

[X] Move and copy files and folders

[X] Each account has a drive limit of 100 MB (his folder on the server cannot exceed 100 MB)

[x] The max upload size is 40 MB (a file greater than 40MB cannot be uploaded)

[X] The web app provides an account info screen that shows statics using graphics
    Example of graphic : space distribution per format (images, documents, videos, ...)

[ ] Preview the maximum of known formats (images, videos, pdf, source code, documents, ...)

[x] Setup script to install requirements and demo data in sqlite.

[x] (3+ person group) Nice, beautiful, responsive UX (demo on laptop and smartphone)

[ ] (4 person group) Open text, view images, play videos



### Some example screens

![](https://junia-learning.com/pluginfile.php/114707/mod_assign/intro/image%20%282%29.png)

![](https://junia-learning.com/pluginfile.php/114707/mod_assign/intro/image%20%281%29.png)

![](https://junia-learning.com/pluginfile.php/114707/mod_assign/intro/image.png)
