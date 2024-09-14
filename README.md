# Employee_Time_Tracking_Application

The Employee Time Tracking Application is designed to help employees track and manage their daily tasks and working hours. It includes features for task management, role-based access control, and graphical reporting through charts.

## Features

- Task Management:
  - Employees can add, edit, and delete tasks.
  - Task details include employee name, role, project, date, time duration, task category (e.g., Meeting, Training), and task description.
  
- Role-Based Access Control (RBAC):
  - Associate: Manage personal tasks and view reports.
  - Admin: View task reports for any employee or project.
  
- Duration Tracking: Displays the total hours worked in daily, weekly, and monthly formats.

- Chart Visualizations:
  - Associates can view their tasks as pie charts (daily) or bar charts (weekly/monthly).
  - Admins can view charts for any selected employee or project.

## Technical Considerations

- **No duplicate task entries**: Tasks for the same date and time cannot overlap.
- **Maximum task duration**: Each task's duration is capped at 8 hours per day.
  
## Setup Instructions

### Prerequisites

- **Java Development Kit (JDK 8 or above)**: [Download JDK](https://www.oracle.com/java/technologies/javase-jdk8-downloads.html)
- **Apache Tomcat (version 9 or above)**: [Download Tomcat](https://tomcat.apache.org/download-90.cgi)
- **MySQL**: [Download MySQL](https://dev.mysql.com/downloads/)
- **Maven**: [Download Maven](https://maven.apache.org/download.cgi)
- **D3.js**: For chart rendering.
- **Gson Library**: For JSON conversion.
- **Jakarta EE**: For handling servlets and JSP files.

### Installation Steps

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Nirmal-Seervi/Employee_Time_Tracking_Application.git
   ```

2. **Database Setup**:
   - Create a MySQL database:
     ```sql
     CREATE DATABASE employee_time_tracker;
     ```
   - Import the SQL schema provided in the `/db` folder to set up the necessary tables:
     ```bash
     mysql -u root -p employee_time_tracker < /path/to/schema.sql
     ```

3. **Configure the Database Connection**:
   - Update the database credentials in the `DBConnection.java` file to match your MySQL setup:
     ```java
     private static final String URL = "jdbc:mysql://localhost:3306/employee_time_tracker";
     private static final String USER = "your_username";
     private static final String PASSWORD = "your_password";
     ```

4. **Build the Application**:
   - Navigate to the project directory:
     ```bash
     cd Employee_Time_Tracking_Application
     ```
   - Build the project using Maven:
     ```bash
     mvn clean install
     ```

5. **Deploy to Apache Tomcat**:
   - Copy the generated `.war` file from the `target` folder into the `webapps` folder of your Tomcat installation.
   - Start your Tomcat server:
     ```bash
     <tomcat_directory>/bin/startup.sh
     ```

6. **Access the Application**:
   - Open your browser and go to `http://localhost:8080/Employee_Time_Tracking_Application`.

## Usage

### 1. **Login**:
   - Employees and Admins can log in to their respective dashboards.

### 2. **Task Management**:
   - Employees can add tasks by specifying time duration, category, and description.

### 3. **Reports & Charts**:
   - Employees can view their task hours in daily, weekly, or monthly formats.
   - Admins can view task reports for any employee or project.

## Database Schema

The database schema includes the following tables:
- `Employee`: Stores employee information (name, role, etc.).
- `Tasks`: Stores details of tasks (task name, description, date, duration).
- `EmployeeProgress`: Tracks task status (Pending/Completed).

## Future Enhancements

- Add support for additional roles like Manager.
- Notifications for task deadlines.
- Improve UI/UX with modern frameworks.

## Contributing

We welcome contributions! Please fork this repository and create a pull request with your changes.

## License

This project is licensed under the MIT License.

---

You can now update your GitHub repository’s README file by adding this content to the `README.md` file.
