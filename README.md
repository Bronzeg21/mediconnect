# MediConnect - Healthcare Management System

A modern healthcare management system with Spring Boot backend and responsive frontend.

## 🚀 Key Features

### Patient Portal
- Secure user authentication and profile management
- Interactive dashboard with appointments and prescriptions
- Online appointment scheduling system
- Prescription refill requests
- Medical records access

### Doctor Workspace
- Professional registration with license verification
- Daily appointment management
- Patient medical history access
- Digital prescription management
- Customizable appointment slots

## 🛠 Technical Stack
- **Backend**: Java 17, Spring Boot 3.2.0, Spring Security, JPA/Hibernate
- **Frontend**: HTML5, CSS3, JavaScript (ES6+), Fetch API
- **Database**: MySQL 8.0+ / H2 (development)
- **Build Tool**: Maven 3.8+
- **Security**: Session-based authentication, BCrypt password hashing

## 🚀 Quick Start

### Prerequisites
- Java 17 JDK
- Maven 3.8+
- MySQL 8.0+ (or use H2 for development)
- 2GB+ free RAM (1GB minimum with optimizations)

### Running Locally

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/mediconnect-springboot.git
   cd mediconnect-springboot
   ```

2. **Configure Database**
   - For MySQL, update `application.properties`:
     ```properties
     spring.datasource.url=jdbc:mysql://localhost:3306/mediconnect
     spring.datasource.username=your_username
     spring.datasource.password=your_password
     ```
   - Or use H2 in-memory DB for development (no setup needed)

3. **Run with Memory Optimization**
   ```bash
   # For development (low memory usage)
   mvn spring-boot:run -Dspring-boot.run.jvmArguments="-Xmx256m -Xms128m -XX:MaxMetaspaceSize=128m -XX:+UseSerialGC"

   # For production
   mvn clean package
   java -Xmx256m -Xms128m -jar target/mediconnect-springboot-1.0.0.jar
   ```

4. **Access the Application**
   - Frontend: http://localhost:8080
   - H2 Console (if enabled): http://localhost:8080/h2-console

## 🔧 Configuration

### Memory Optimization (Optional)
Add to `application.properties` for better performance on low-memory systems:
```properties
# Reduce memory footprint
spring.main.lazy-initialization=true
spring.datasource.hikari.maximum-pool-size=2
spring.jpa.open-in-view=false
```

## 📂 Project Structure

```
mediconnect-springboot/
├── src/
│   ├── main/
│   │   ├── java/com/mediconnect/
│   │   │   ├── config/        # Spring configuration
│   │   │   ├── controller/    # REST endpoints
│   │   │   ├── dto/           # Data Transfer Objects
│   │   │   ├── entity/        # JPA entities
│   │   │   ├── repository/    # Data access
│   │   │   ├── service/       # Business logic
│   │   │   └── MediConnectApplication.java
│   │   └── resources/
│   │       ├── static/        # Frontend assets
│   │       │   ├── css/       # Stylesheets
│   │       │   ├── js/        # JavaScript files
│   │       │   └── images/    # Image assets
│   │       ├── application.properties
│   │       └── schema.sql     # Database schema
│   └── test/                  # Test files
└── pom.xml                    # Maven configuration
```

## 🐛 Troubleshooting

### Common Issues

#### 1. Memory Errors
```
Java HotSpot(TM) 64-Bit Server VM warning: INFO: os::commit_memory failed
```
**Solution:**
- Use the provided JVM memory arguments
- Close other memory-intensive applications
- Increase system page file size
- Use H2 database instead of MySQL for development

#### 2. Chunked Encoding Error
**Symptoms:** Incomplete responses or browser console errors
**Solution:**
- Clear browser cache (Ctrl+F5)
- Verify backend is returning proper DTOs (not JPA entities)
- Check server logs for serialization errors

#### 3. Database Connection Issues
**Solution:**
- Verify database service is running
- Check credentials in `application.properties`
- Ensure database exists and user has permissions
- Run `schema.sql` to initialize tables if needed


Built with ❤️ for better healthcare management

