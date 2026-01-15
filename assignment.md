# Assignment (Optional)

## Brief

Create a Spring Boot project called SchoolManagementSystem and implement JPA entities with relationships using H2 database.

1. **Basic JPA Entity with CRUD Operations**
   - Add dependencies: Spring Data JPA, H2 Database, Spring Web, and Lombok
   - Configure H2 in `application.properties`:
     - Enable H2 console
     - Set database name to "school"
   - Create a `Student` entity with:
     - `@Entity` and `@Table(name = "student")` annotations
     - `Long id` with `@Id` and `@GeneratedValue(strategy = GenerationType.IDENTITY)`
     - `String firstName`, `String lastName`, `String email` with `@Column` annotations
     - Use Lombok's @Getter and @Setter
   - Create `StudentRepository` interface extending `JpaRepository<Student, Long>`
   - Create `StudentService` interface and implementation with methods:
     - `createStudent()`, `getAllStudents()`, `getStudent(Long id)`, `deleteStudent(Long id)`
   - Create `StudentController` with endpoints:
     - `POST /students` - Create a student
     - `GET /students` - Get all students
     - `GET /students/{id}` - Get a student by ID
     - `DELETE /students/{id}` - Delete a student
   - Create a `DataLoader` class with @Component and @PostConstruct to pre-populate 3 students
   - Test all endpoints and verify data in H2 console

2. **Implement Many-to-One Relationship**
   - Create a `Course` entity with:
     - `Long id`, `String courseName`, `String courseCode`
     - Use appropriate JPA annotations
   - Create `CourseRepository` extending `JpaRepository<Course, Long>`
   - Add a many-to-one relationship in Student entity:
     - `@ManyToOne(optional = false)`
     - `@JoinColumn(name = "course_id", referencedColumnName = "id")`
     - Field: `Course course`
   - Update `DataLoader` to:
     - Pre-populate 2 courses
     - Assign each student to a course
   - Create a nested route in StudentController:
     - `POST /courses/{id}/students` - Add a student to a course
   - Implement the corresponding service method to:
     - Retrieve the course by ID
     - Set the course on the student
     - Save and return the student
   - Test creating students with course associations
   - Verify in H2 console that the `student` table has a `course_id` foreign key column

## Submission (Optional)

- Submit the URL of the GitHub Repository that contains your work to NTU black board.
- Should you reference the work of your classmate(s) or online resources, give them credit by adding either the name of your classmate or URL.

## References
- Java: https://docs.oracle.com/javase/
- Spring Boot: https://docs.spring.io/spring-boot/docs/current/reference/html/
- PostgreSQL: https://www.postgresql.org/docs/
- OWASP: https://cheatsheetseries.owasp.org/