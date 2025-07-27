# 💼 Job Post REST API with Spring Boot & PostgreSQL

A minimal and clean RESTful API to manage job postings using:
- **Spring Boot**
- **Spring Data JPA**
- **Spring Data REST**
- **PostgreSQL**

> No controller or service layers — endpoints are exposed automatically using Spring Data REST.

---

## 🚀 Features
- Full CRUD operations for JobPost entity
- Custom search using method naming conventions
- PostgreSQL integration for persistent storage
- Loads demo data with a `/load` endpoint *(implement if not present)*

---

## 🛠️ Tech Stack

| Layer        | Technology             |
|-------------|------------------------|
| Language     | Java 17+               |
| Framework    | Spring Boot            |
| ORM          | Spring Data JPA        |
| REST Engine  | Spring Data REST       |
| Database     | PostgreSQL             |
| Build Tool   | Maven                  |

---

## 📦 Getting Started

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/mhnuk2007/spring-data-rest-demo.git
cd spring-data-rest-demo
```

### 2️⃣ Configure PostgreSQL
Make sure PostgreSQL is running and a database is created:
- **DB Name:** `jobportal`

Update `src/main/resources/application.properties`:
```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/jobportal
spring.datasource.username=your_username
spring.datasource.password=your_password
spring.jpa.hibernate.ddl-auto=update
```

### 3️⃣ Run the Application
```bash
./mvnw spring-boot:run
```

---

## 🌐 API Endpoints
Spring Data REST automatically generates all endpoints for the `JobPost` entity.

### Base Path
```
http://localhost:8080/jobPosts
```

### CRUD Endpoints
| Method | Endpoint            | Description              |
|--------|---------------------|--------------------------|
| GET    | `/jobPosts`         | Get all job posts        |
| GET    | `/jobPosts/{id}`    | Get job post by ID       |
| POST   | `/jobPosts`         | Add new job post         |
| PUT    | `/jobPosts/{id}`    | Update job post          |
| DELETE | `/jobPosts/{id}`    | Delete job post          |

### Search Endpoint
| Method | Endpoint                                                                                      | Description                 |
|--------|-----------------------------------------------------------------------------------------------|-----------------------------|
| GET    | `/jobPosts/search/findByPostProfileContainingOrPostDescContaining?postProfile=X&postDesc=Y`  | Search by profile or desc   |

### Load Sample Data
```http
GET /load
```
Loads predefined job posts into the database. *(If not implemented, remove or add this feature)*

---

## 📘 Example JSON
```json
{
  "postProfile": "Java Developer",
  "postDesc": "Experience with Spring Boot",
  "reqExperience": 2,
  "postTechStack": ["Java", "Spring Boot", "MySQL", "Jakarta EE"]
}
```

---

## 📌 Notes
- No controller or service layer is needed due to `Spring Data REST`.
- Custom endpoints can still be added via `@RestController` if needed.

---

## 🙌 Author
Built with ❤️ by [Mohan Lal](https://github.com/mhnuk2007)

---

## 📄 License
This project is licensed under the MIT License.
