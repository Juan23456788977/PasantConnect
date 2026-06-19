<div align="center">

# 🎓 PasantConnect

### Sistema Integral de Gestión de Pasantías
*Full-Stack Internship Management System*

**🌐 English** | [🇪🇸 Español](#-español)

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=18&pause=1000&color=3ECF8E&center=true&vCenter=true&width=650&lines=Multi-role+Authentication+(RBAC);Intern+%2B+Company+%2B+Moderator+Management;Hour+Tracking+%26+Grade+Management;Testimonial+System+%2B+Email+Recovery" alt="Typing SVG" />
</p>

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](#)
[![PHP](https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white)](#)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](#)
[![MySQL](https://img.shields.io/badge/MySQL-316192?style=for-the-badge&logo=mysql&logoColor=white)](#)
[![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white)](#)

</div>

---

## 📋 Description

**PasantConnect** is a complete web-based internship management system built as a graduation thesis project. It centralizes and automates the full lifecycle of student internships: from company assignment to hour tracking, grade management, and supervisor communication.

Originally developed for **I.T.A.T. (Instituto Técnico de Telemática)** as the final year thesis project for the *Técnico Medio en Telemática* degree.

---

## ✨ Core Features

- 🔐 **Multi-role RBAC** — `pasante` / `moderador` / `admin` with bcrypt password hashing
- 🏢 **Company Management** — Register and categorize companies by importance level
- 👤 **Intern Management** — Full profile, company assignment, hour tracking
- ⏱️ **Hour Tracking** — Log completed vs. required internship hours
- 📝 **Grade System** — Assign and track internship grades per student
- 💬 **Testimonial System** — Interns submit feedback, moderators review it
- 📧 **Email Recovery** — Password reset via PHP Mailer API
- 🔒 **Secure Auth** — bcrypt hashing (`$2y$10$...`), session management

---

## 🗄️ Database Schema

```sql
-- Users table (multi-role)
CREATE TABLE users (
  id              INT PRIMARY KEY AUTO_INCREMENT,
  nombre          VARCHAR(100) NOT NULL,
  email           VARCHAR(100) UNIQUE NOT NULL,
  password        VARCHAR(255) NOT NULL,        -- bcrypt hashed
  role            ENUM("pasante","moderador","admin") NOT NULL,
  nota            INT DEFAULT NULL,             -- internship grade
  horas_totales   INT DEFAULT NULL,             -- required hours
  horas_cumplidas INT DEFAULT 0,               -- completed hours
  asignado_empresa VARCHAR(100) DEFAULT NULL,   -- assigned company
  ubicacion_empresa VARCHAR(100) DEFAULT NULL,
  comentarios     TEXT
);

-- Companies table
CREATE TABLE empresas (
  id          INT PRIMARY KEY AUTO_INCREMENT,
  nombre      VARCHAR(100) UNIQUE NOT NULL,
  importancia ENUM("Importante","Medio importante","No tan importante") NOT NULL,
  ubicacion   VARCHAR(100) NOT NULL
);
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | HTML5, CSS3, Vanilla JavaScript (ES6+) |
| Backend | PHP 7.3+ |
| Database | MySQL / MariaDB 10.x |
| Auth | PHP Sessions + bcrypt (`password_hash`) |
| Email | PHP Mailer API (password recovery) |
| Server | Apache / XAMPP (local) |

---

## 🚀 Installation

```bash
# 1. Clone repository
git clone https://github.com/Juan23456788977/PasantConnect.git

# 2. Import database
# Open phpMyAdmin and import: gestion_pasantias.sql

# 3. Configure database connection
# Edit db.php with your MySQL credentials:
# $host = "localhost"; $user = "root"; $pass = ""; $db = "gestion_pasantias";

# 4. Run with XAMPP / WAMP
# Place folder in htdocs/ and access: http://localhost/PasantConnect/

# 5. Default admin credentials
# Email: admin@empresa.com  |  Password: (set during install)
```

---

## 📁 Project Structure

```
PasantConnect/
├── index.html              # Landing page + login redirect
├── login.php               # Authentication handler
├── db.php                  # Database connection
├── registerPasante.php     # Intern registration
├── registerEmpresa.php     # Company registration
├── registerModerador.php   # Moderator registration
├── gestion_pasantias.sql   # Full database schema
├── css/
│   └── main.css            # Global styles
└── js/
    ├── auth.js             # Auth logic
    ├── main.js             # Core app logic
    └── ui.js               # UI components
```

---

<details>
<summary>🇪🇸 Español</summary>

<br>

## 📋 Descripción

**PasantConnect** es un sistema web completo para la gestión de pasantías estudiantiles, desarrollado como proyecto de tesis de grado. Centraliza y automatiza todo el ciclo de vida de las pasantías: desde la asignación a empresas hasta el control de horas, gestión de notas y comunicación entre supervisores y pasantes.

Desarrollado originalmente para el **I.T.A.T. (Instituto Técnico de Telemática)** como proyecto de grado para la carrera *Técnico Medio en Telemática*.

## ✨ Características Principales

- 🔐 **RBAC Multi-rol** — `pasante` / `moderador` / `admin` con contraseñas hasheadas con bcrypt
- 🏢 **Gestión de Empresas** — Registro y categorización por nivel de importancia
- 👤 **Gestión de Pasantes** — Perfil completo, asignación a empresa, seguimiento de horas
- ⏱️ **Control de Horas** — Registro de horas cumplidas vs. requeridas
- 📝 **Sistema de Notas** — Asignación y seguimiento de calificaciones por pasante
- 💬 **Sistema de Testimonios** — Los pasantes envían feedback, los moderadores lo revisan
- 📧 **Recuperación por Email** — Restablecimiento de contraseña vía PHP Mailer API
- 🔒 **Autenticación Segura** — bcrypt, gestión de sesiones PHP

## 🚀 Instalación

```bash
# 1. Clonar repositorio
git clone https://github.com/Juan23456788977/PasantConnect.git

# 2. Importar base de datos
# Abre phpMyAdmin e importa: gestion_pasantias.sql

# 3. Configurar conexión a BD
# Edita db.php con tus credenciales MySQL

# 4. Ejecutar con XAMPP/WAMP
# Coloca la carpeta en htdocs/ y accede: http://localhost/PasantConnect/
```

</details>

---

<div align="center">
  <b>Juan Alberto Cortez Urrea</b> — 18 años, Caracas, Venezuela 🇻🇪<br/>
  <a href="https://github.com/Juan23456788977">GitHub</a> · 
  <a href="mailto:cortezurreajuanalberto@gmail.com">Email</a><br/><br/>
  <i>"My graduation thesis. Built to solve a real problem."</i>
</div>
