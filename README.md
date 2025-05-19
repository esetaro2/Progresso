#  Progresso

The system is a **web-based collaborative environment** intended for **team project management**. Facilitate creation and structuring of projects, task creation, tracking progress, and communication via comments. The system should be designed in a way that it supports **secure permission management** where different categories of users (e.g., *administrators*, *project managers*, and *team members*) can access different functionalities.

Developed with **Angular**, the user interface is simple and facilitates easy and efficient visualization and interaction with the data related to the projects. The backend, developed using **Java** and **Spring Boot**, manages business logic and data access via a **repository** and **service structure**.

This project was developed as part of a **Bachelor’s thesis in Computer Science** at the **University of Salerno (UNISA)**. The system was designed to maximize collaboration and support project management, making it suitable for a variety of organizational contexts and team structures, with a focus on **effectiveness** and **scalability**.

## Table of Contents

- [💻 Technologies](#technologies)  
- [✨ Main Features](#features)  
- [📦 Installation](#installation)
- [📄 Documentation](#documentation)
- [⚖️ Licensing](#licensing)
<h2 id="technologies">💻 Technologies</h2>

- **Frontend:**
  - **Angular**: A framework and platform for developing single-page client applications using HTML and TypeScript.
  - **HTML5**: Markup language for structuring the content on the web.
  - **CSS3**: Style sheet language used for defining the presentation of the web page.
  - **TypeScript**: JavaScript superset that supports optional static typing and is used with Angular.

- **Backend:**

  - **Java**: Programming language to develop the backend.
  - **Spring Boot**: A mechanism for developing stand-alone, production-ready Spring-based applications. It has an abundance of features to expedite the development of backend applications.
  - **Spring Security**: A module of the Spring framework, used for authentication, authorization, and other security operations in a Spring Boot app.
  - **Spring Data JPA**: One of the pieces of the Spring Data project, it simplifies data access using JPA (Java Persistence API) to talk to databases. Hibernate is the built-in JPA provider for ORM capabilities.
  - **MySQL**: Relational database used to store the application's data.

- **Build & Dependency Management:**
  - **Maven**: A build automation tool used for managing dependencies and packaging.
  - **Node.js**: JavaScript runtime used for the frontend build and running development tools.

- **Version Control:**
  - **Git**: Version control system to manage the source code.
  - **GitHub**: Git repository hosting platform used to store the project.

- **Testing:**
  - **JUnit**: A framework for writing and running tests in Java.
  - **Mockito**: A Java-based mocking framework used in unit tests.
  - **Selenium IDE**: A browser automation tool that helps in automating web application testing by recording and playing back user interactions with the browser. It's used for automating frontend tests in the web-based project.

- **Other Tools:**
  - **Postman**: API testing tool used to test the backend APIs.

<h2 id="features">✨ Main Features</h2>

- 🔐 **Role-based access control**: Different permissions for Admins, Project Managers, and Team Members.
- 📁 **Project and task management**: Create, update, assign, and track tasks within projects.
- 💬 **Comment system**: Users can communicate directly within each project via comments.
- 📊 **Progress tracking**: Visual indicators of task and project status.
- 🔎 **Secure authentication**: Login system protected via Spring Security.

<h2 id="installation">📦 Installation</h2>

### ‼️ Before you start

Make sure **Git** is installed (required for cloning the repo and submodules):

```bash
git --version
# e.g. git version 2.41.0
```
If you don’t have it, install from: https://git-scm.com/
### 🔧 Backend Setup

#### Prerequisites

Make sure the following tools are installed on your system:

- [Java 21](https://adoptium.net/)
- [MySQL](https://www.mysql.com/)
- [Maven](https://maven.apache.org/)

#### 1. Clone the repository with submodules

This project uses Git submodules for frontend and backend. Clone it using:

```bash
git clone --recurse-submodules https://github.com/esetaro2/progresso.git
cd progresso
```
<strong>If you forgot <code>--recurse-submodules</code></strong>, run this:

```bash
git submodule update --init --recursive
```

#### 2. Configure environment variables

Before proceeding, set the following environment variables so that Spring Boot picks up your credentials and secret.

- ##### Linux / macOS (bash, zsh, etc.)
  ```bash
  export DB_USER="your_mysql_username"
  export DB_PASS="your_mysql_password"
  export JWT_SECRET="your_jwt_secret_key"
  ```
  To verify:
  ```bash
  echo $DB_USER
  echo $DB_PASS
  echo $JWT_SECRET
  ```
  
- ##### Windows PowerShell
  ```bash
  $env:DB_USER = "your_mysql_username"
  $env:DB_PASS = "your_mysql_password"
  $env:JWT_SECRET = "your_jwt_secret_key"
  ```
  To verify:
  ```bash
  echo $env:DB_USER
  echo $env:DB_PASS
  echo $env:JWT_SECRET
  ```

- ##### Windows (cmd.exe)
  ```bash
  set DB_USER=your_mysql_username
  set DB_PASS=your_mysql_password
  set JWT_SECRET=your_jwt_secret_key
  ```
  To verify:
   ```bash
  echo %DB_USER%
   echo %DB_PASS%
   echo %JWT_SECRET%
   ```

#### 3. Set up the MySQL database

##### 1. Start your MySQL server.
##### 2. Create a new database:

```bash
CREATE SCHEMA progresso CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

#### 4. Build and run the backend

From the backend directory, run the following commands:

```bash
mvn clean install
mvn spring-boot:run
```

### 🔧 Frontend Setup
#### Prerequisites

Make sure the following tools are installed on your system:

- [Node.js (v22.12.0 or higher)](https://nodejs.org/en/download/)
- [Angular CLI (v19.1.0 or higher)](https://angular.dev/tools/cli/setup-local)

#### 1. Verify Node.js version
```bash
node --version
# should output: v22.12.0 (or newer)
```
#### 2. Verify Angular CLI version
```bash
ng version
# should show Angular CLI: 19.1.0 (or newer)
```
If you need to update:
```bash
npm install -g @angular/cli@latest
```

#### 3. Navigate to the frontend module
```bash
cd progresso-frontend
```
#### 4. Install dependencies
```bash
npm install --legacy-peer-deps
```
#### 5. Serve the application
```bash
ng serve
```
The frontend will be available at:
```bash
http://localhost:4200
```
#### 6. Initial Admin User
To get you started immediately, the application will auto-create a default administrator on first run.
- **Username:** `a.superuser.am1@progresso.com`  
- **Password:** `admin123`

Once logged in as **admin**, you can:
- Register new users
- Create projects
- Define teams
- Create and assign tasks

<h2 id="documentation">📄 Documentation</h2>

The full technical documentation, including use cases, system architecture, and testing details, is available in the thesis document (in Italian):

👉 [📘 View the full thesis (PDF)](./docs/thesis-documentation.pdf)

<h2 id="licensing">⚖️ Licensing</h2>
All contents of this repository — including source code, documentation, and the thesis document — are protected by copyright and distributed under a custom All Rights Reserved license.
  
👉 [📘 View the license file for details](./LICENSE)

