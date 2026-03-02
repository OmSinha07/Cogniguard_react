# 🚀 CogniGuard

<div align="center">

<!-- TODO: Add project logo -->

[![GitHub stars](https://img.shields.io/github/stars/OmSinha07/CogniGuard?style=for-the-badge)](https://github.com/OmSinha07/CogniGuard/stargazers)

[![GitHub forks](https://img.shields.io/github/forks/OmSinha07/CogniGuard?style=for-the-badge)](https://github.com/OmSinha07/CogniGuard/network)

[![GitHub issues](https://img.shields.io/github/issues/OmSinha07/CogniGuard?style=for-the-badge)](https://github.com/OmSinha07/CogniGuard/issues)

[![GitHub license](https://img.shields.io/github/license/OmSinha07/CogniGuard?style=for-the-badge)](LICENSE) <!-- TODO: Add actual license file and link -->

**Your Fortress for Secure and Private File Management**

<!-- TODO: Add live demo link if available -->
<!-- TODO: Add documentation link if available -->

</div>

## 📖 Overview

CogniGuard is a robust web application designed for highly secure and private file storage. It empowers users to securely upload and download files, protected by advanced cryptographic techniques, comprehensive key management, and multi-factor authentication. Beyond basic encryption, CogniGuard integrates machine learning models to detect potential threats within uploaded content, providing an intelligent layer of security. The application focuses on data privacy, offering a user-friendly interface powered by Flask, ensuring that your sensitive files remain confidential and protected against unauthorized access.

## ✨ Features

-   **Secure File Upload & Download:** Encrypt and decrypt files during upload and download processes, ensuring data confidentiality.
-   **Robust User Authentication:** Secure registration and login system with multi-factor authentication (MFA) support using Argon2 password hashing.
-   **Advanced Key Management:** Generates and securely manages user-specific cryptographic keys, including adaptive key derivation.
-   **Machine Learning Threat Detection:** Utilizes a pre-trained ML model to classify and detect potential threats or anomalies in uploaded files.
-   **File Metadata Management:** Stores and retrieves essential metadata for each uploaded file, enhancing organization and retrieval.
-   **Performance Monitoring:** Logs and analyzes performance metrics for file upload and download operations.
-   **Role-Based Access Control:** Differentiates between regular users and administrative roles for enhanced security management.
-   **Client-Side Cryptography (Adaptive):** Employs adaptive cryptographic utilities for enhanced security and flexibility in encryption.
-   **Intuitive Web Interface:** A clean and responsive web interface built with Flask and Jinja2 templates for seamless user interaction.

## 🖥️ Screenshots

<!-- TODO: Add actual screenshots of the application -->
<!-- ![Screenshot 1](path-to-screenshot-1.png) -->
<!-- ![Screenshot 2](path-to-screenshot-2.png) -->

## 🛠️ Tech Stack

**Backend:**

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)

[![Flask](https://img.shields.io/badge/Flask-2.2.2-000000?style=for-the-badge&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)

[![Flask-Login](https://img.shields.io/badge/Flask--Login-0.6.2-blue?style=for-the-badge)](https://flask-login.readthedocs.io/en/latest/)

[![Cryptography](https://img.shields.io/badge/Cryptography-39.0.0-6D84C7?style=for-the-badge)](https://cryptography.io/en/latest/)

[![Argon2](https://img.shields.io/badge/Argon2-21.3.0-darkgreen?style=for-the-badge)](https://pypi.org/project/argon2-cffi/)

**Frontend:**

[![HTML](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)

[![CSS](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)

[![Jinja2](https://img.shields.io/badge/Jinja2-3.1.2-white?style=for-the-badge&logo=jinja)](https://jinja.palletsprojects.com/)

**Machine Learning:**

[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.2.0-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)

[![Pandas](https://img.shields.io/badge/Pandas-1.5.2-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)

[![NumPy](https://img.shields.io/badge/NumPy-1.23.5-013243?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org/)

**Database:**

[![SQLite](https://img.shields.io/badge/SQLite-07405E?style=for-the-badge&logo=sqlite&logoColor=white)](https://www.sqlite.org/index.html)

[![Flask-SQLAlchemy](https://img.shields.io/badge/Flask--SQLAlchemy-3.0.3-orange?style=for-the-badge)](https://flask-sqlalchemy.palletsprojects.com/)

[![JSON](https://img.shields.io/badge/JSON-000000?style=for-the-badge&logo=json&logoColor=white)](https://www.json.org/json-en.html)

## 🚀 Quick Start

Follow these steps to get CogniGuard up and running on your local machine.

### Prerequisites

-   **Python 3.x** (preferably 3.8 or higher)
-   **pip** (Python package installer, usually comes with Python)

### Installation

1.  **Clone the repository**
    ```bash
    git clone https://github.com/OmSinha07/CogniGuard.git
    cd CogniGuard
    ```

2.  **Install dependencies**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Environment setup**
    Create a `.env` file in the root directory and add your `SECRET_KEY`. This is crucial for Flask session management.
    ```bash
    cp .env.example .env # If .env.example existed, otherwise create manually
    ```
    Edit `.env` and add:
    ```ini
    SECRET_KEY='your_super_secret_key_here'
    FLASK_APP=app_with_auth.py
    FLASK_ENV=development # For development, use 'production' for deployment
    ```
    Replace `'your_super_secret_key_here'` with a long, random string.

4.  **Database setup**
    Initialize the SQLite database and create necessary tables.
    ```bash
    flask shell
    ```
    Inside the Flask shell, run:
    ```python
    from app_with_auth import db, app
    with app.app_context():
        db.create_all()
    exit()
    ```
    This will create `site.db` inside the `instance/` folder and other JSON files like `file_metadata.json`, `user_keys.json` in the root.

5.  **Start development server**
    ```bash
    flask run
    ```

6.  **Open your browser**
    Visit `http://localhost:5000` (or the port indicated by Flask).

## 📁 Project Structure

```
CogniGuard/
├── .gitignore
├── .env                  # Environment variables for Flask (SECRET_KEY, FLASK_APP)
├── app_with_auth.py      # Main Flask application, routes, and core logic
├── auth.py               # Authentication module (login, register, MFA, password hashing)
├── crypto_utils.py       # Basic cryptographic utility functions
├── crypto_utils_adaptive.py # Adaptive cryptographic utility functions
├── download_performance_metrics.csv # CSV log for download performance
├── encrypted_uploads/    # Directory to store encrypted user files
├── file_metadata.json    # JSON file acting as a database for file metadata
├── file_storage.py       # Handles file upload and download operations
├── instance/             # Flask instance folder (contains SQLite database: site.db)
│   └── site.db
├── key_storage.py        # Manages user-specific encryption keys
├── ml_classifier.py      # Machine learning model integration and classification logic
├── ml_model.pkl          # Pre-trained ML model (e.g., for threat detection)
├── models.py             # SQLAlchemy models for User and File entities
├── requirements.txt      # Python package dependencies
├── templates/            # HTML templates rendered by Flask
│   ├── base.html         # Base template for common layout
│   ├── dashboard.html    # User dashboard
│   ├── download.html     # File download page
│   ├── index.html        # Home page
│   ├── login.html        # User login page
│   ├── register.html     # User registration page
│   └── upload.html       # File upload page
├── upload_performance_metrics.csv # CSV log for upload performance
└── user_keys.json        # JSON file acting as a database for user cryptographic keys
```

## ⚙️ Configuration

### Environment Variables

The application relies on environment variables for sensitive information and configuration.
Create a `.env` file in the project root based on the example below.

| Variable    | Description                                              | Default       | Required |

| :---------- | :------------------------------------------------------- | :------------ | :------- |

| `SECRET_KEY` | A strong, random string used for session management.     | None          | Yes      |

| `FLASK_APP` | Specifies the main Flask application file.               | `app_with_auth.py` | Yes      |

| `FLASK_ENV` | Sets the Flask environment (`development` or `production`). | `development` | Yes      |

### Configuration Files

-   **`instance/site.db`**: The SQLite database for user accounts and file records (managed by Flask-SQLAlchemy).
-   **`file_metadata.json`**: Stores metadata for each encrypted file.
-   **`user_keys.json`**: Stores encrypted user keys.

## 🔧 Development

### Available Scripts

| Command        | Description                                     |

| :------------- | :---------------------------------------------- |

| `flask run`    | Starts the Flask development server.            |

| `flask shell`  | Opens an interactive Python shell with Flask app context. |

### Development Workflow

1.  Ensure all prerequisites are met and dependencies are installed.
2.  Set up environment variables in `.env`.
3.  Initialize the database if it's a fresh setup.
4.  Run `flask run` to start the application.
5.  Access the application via your web browser.

## 🧪 Testing

No specific testing framework or test files were detected in the repository. It is recommended to implement unit and integration tests for the various components (authentication, cryptography, file storage, ML classification) to ensure robustness and security.

<!-- ## 🚀 Deployment

For production deployment of this Flask application, it's recommended to use a production-ready WSGI server such as Gunicorn or uWSGI, typically behind a reverse proxy like Nginx or Apache.

**Example with Gunicorn:**

1.  Install Gunicorn:
    ```bash
    pip install gunicorn
    ```
2.  Run the application using Gunicorn:
    ```bash
    gunicorn -w 4 'app_with_auth:app'
    ```
    (Replace `4` with the number of worker processes appropriate for your server.)

Consider containerization with Docker for easier deployment and environment consistency. -->

## 📚 API Reference

CogniGuard provides web-based endpoints through Flask. Key routes include:

### Authentication & User Management
-   `GET /`: Home page.
-   `GET /login`: Displays the login form.
-   `POST /login`: Handles user login.
-   `GET /register`: Displays the registration form.
-   `POST /register`: Handles user registration and key generation.
-   `GET /logout`: Logs out the current user.
-   `GET /mfa_setup`: Displays MFA setup page (if implemented).
-   `POST /mfa_setup`: Handles MFA setup (if implemented).
-   `GET /admin_dashboard`: Administrator dashboard (requires admin role).

### File Management
-   `GET /dashboard`: Displays user's file dashboard.
-   `GET /upload`: Displays the file upload form.
-   `POST /upload`: Handles secure file uploads, encryption, and ML classification.
-   `GET /download/<filename>`: Initiates secure file download and decryption.
-   `POST /delete_file/<filename>`: Deletes a user's file (requires authentication).

## 🤝 Contributing

We welcome contributions to CogniGuard! If you have suggestions for improvements, new features, or bug fixes, please consider the following:

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/YourFeatureName`).
3.  Make your changes.
4.  Commit your changes (`git commit -m 'Add new feature'`).
5.  Push to the branch (`git push origin feature/YourFeatureName`).
6.  Open a Pull Request.

Please ensure your code adheres to a consistent style and includes comments where necessary.

### Development Setup for Contributors

The development setup is the same as described in the [Quick Start](#🚀-quick-start) section.

## 📄 License

This project is currently without an explicit license. Please contact the repository owner for licensing details. <!-- TODO: Add actual license if available, e.g., MIT License -->

## 🙏 Acknowledgments

-   **Flask Ecosystem:** For providing a flexible and powerful web framework.
-   **Cryptography Library:** For secure cryptographic primitives.
-   **Scikit-learn, Pandas, NumPy:** For robust machine learning and data handling capabilities.
-   **OmSinha07:** The project author.

## 📞 Support & Contact

-   📧 Email: [Contact OmSinha07 via GitHub profile](https://github.com/OmSinha07) <!-- TODO: Add a specific contact email if desired -->
-   🐛 Issues: [Report bugs or suggest features on GitHub Issues](https://github.com/OmSinha07/CogniGuard/issues)

---

<div align="center">

**⭐ Star this repo if you find it helpful!**

Made with ❤️ by [OmSinha07](https://github.com/OmSinha07)

</div>

