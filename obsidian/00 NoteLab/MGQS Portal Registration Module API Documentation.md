## Overview
The Registration Module enables students to register on the MGQS Portal. Students can either provide their **Chanda Number** (Jamaat Membership Number) to auto-fetch their information or manually input their details. The registration process categorizes students as **Accepted** or **Under Review** based on validation logic. The module is built using **C#** and integrates with an ASP.NET Core Web API.
---

### Notes
## Running Program Explanation

The **Running Program** refers to the course or program a student enrolls in during registration on the MGQS Portal. It is represented by the `RunningProgramEntity` and linked to a student's registration via `RunningProgramEntityId`. Key details:

- **Purpose**: Identifies the specific academic or training program the student is pursuing (e.g., "Software Engineering").
- **Attributes**:
  - `Id`: Unique identifier for the program.
  - `ProgramName`: Name of the course (e.g., "Networking").
  - `Description`: Brief overview of the program’s objectives and content.
- **Importance**: Ensures accurate tracking of a student’s enrollment and progress in the chosen course.
- **Additional Notes**:
  - Programs are predefined in the system by administrators.
  - Students select a program during registration, which must align with available offerings.
  - The `Jaamat` entity links the student to a specific community or chapter, which may influence program eligibility or requirements.
  - Validation ensures the provided `RunningProgramEntityId` corresponds to an active program in the database.
## API Endpoints

### Base URL
`https://api.mgqsportal.com/v1`

### Authentication
- **No authentication** is required for registration endpoints as they are public-facing for new users.
- Future endpoints (e.g., profile updates) may require JWT-based authentication.

---

### 1. Register Student with Chanda Number
**POST** `/registrations/chanda`

Registers a student by fetching their details using the provided Chanda Number (Jamaat Membership Number).

#### Request
- **Content-Type**: `application/json`
- **Body**:
```json
{
  "jamaatMembershipNumber": "string",
  "runningProgramEntityId": "string"
}
```

#### Response
- **Status**: `201 Created`
- **Body**:
```json
{
  "userId": "string",
  "firstName": "string",
  "lastName": "string",
  "middleName": "string",
  "highestQualification": "string",
  "dateOfBirth": "yyyy-MM-dd",
  "phoneNumber": "string",
  "guidianPhoneNumber": "string",
  "email": "string",
  "state": "string",
  "city": "string",
  "street": "string",
  "gender": "string",
  "jamaatMembershipNumber": "string",
  "runningProgramEntityId": "string",
  "jaamatId": "string",
  "status": "Accepted | Under Review"
}
```
- **Error Responses**:
  - `400 Bad Request`: Invalid or missing Chanda Number.
  - `404 Not Found`: Chanda Number not found in the Jamaat database.
  - `500 Internal Server Error`: Server-side error.

#### Example
```bash
curl -X POST https://api.mgqsportal.com/v1/registrations/chanda \
-H "Content-Type: application/json" \
-d '{
  "jamaatMembershipNumber": "JM123456",
  "runningProgramEntityId": "PROG789"
}'
```

---

### 2. Register Student Manually
**POST** `/registrations/manual`

Registers a student by manually providing all required details.

#### Request
- **Content-Type**: `application/json`
- **Body**:
```json
{
  "firstName": "string",
  "lastName": "string",
  "middleName": "string",
  "highestQualification": "string",
  "dateOfBirth": "yyyy-MM-dd",
  "phoneNumber": "string",
  "guidianPhoneNumber": "string",
  "email": "string",
  "state": "string",
  "city": "string",
  "street": "string",
  "gender": "string",
  "jamaatMembershipNumber": "string",
  "runningProgramEntityId": "string",
  "jaamatId": "string"
}
```

#### Response
- **Status**: `201 Created`
- **Body**:
```json
{
  "userId": "string",
  "firstName": "string",
  "lastName": "string",
  "middleName": "string",
  "highestQualification": "string",
  "dateOfBirth": "yyyy-MM-dd",
  "phoneNumber": "string",
  "guidianPhoneNumber": "string",
  "email": "string",
  "state": "string",
  "city": "string",
  "street": "string",
  "gender": "string",
  "jamaatMembershipNumber": "string",
  "runningProgramEntityId": "string",
  "jaamatId": "string",
  "status": "Accepted | Under Review"
}
```
- **Error Responses**:
  - `400 Bad Request`: Missing or invalid fields.
  - `409 Conflict`: Email or phone number already registered.
  - `500 Internal Server Error`: Server-side error.

#### Example
```bash
curl -X POST https://api.mgqsportal.com/v1/registrations/manual \
-H "Content-Type: application/json" \
-d '{
  "firstName": "Awwal",
  "lastName": "Balogun",
  "middleName": "Olu",
  "highestQualification": "BSc",
  "dateOfBirth": "1995-05-15",
  "phoneNumber": "+2348012345678",
  "guidianPhoneNumber": "+2348098765432",
  "email": "awwal.balogun@example.com",
  "state": "Lagos",
  "city": "Ikeja",
  "street": "123 Main Street",
  "gender": "Male",
  "jamaatMembershipNumber": "JM123456",
  "runningProgramEntityId": "PROG789",
  "jaamatId": "JAM456"
}'
```

---

### 3. Get Registration Status
**GET** `/registrations/{userId}/status`

Retrieves the registration status for a given user.

#### Request
- **Parameters**:
  - `userId` (path): The unique identifier of the user.
- **Example**: `GET /registrations/123e4567-e89b-12d3-a456-426614174000/status`

#### Response
- **Status**: `200 OK`
- **Body**:
```json
{
  "userId": "string",
  "status": "Accepted | Under Review"
}
```
- **Error Responses**:
  - `404 Not Found`: User not found.
  - `500 Internal Server Error`: Server-side error.

#### Example
```bash
curl -X GET https://api.mgqsportal.com/v1/registrations/123e4567-e89b-12d3-a456-426614174000/status
```

---

## Data Models

### Student Registration Model
```csharp
public class StudentRegistration
{
    public string? UserId { get; set; }
    public IdentityUser User { get; set; }
    public string FirstName { get; set; }
    public string LastName { get; set; }
    public string MiddleName { get; set; }
    public string HighestQualification { get; set; }
    public DateOnly DateOfBirth { get; set; }
    public string PhoneNumber { get; set; }
    public string GuidianPhoneNumber { get; set; }
    public string Email { get; set; }
    public string State { get; set; }
    public string City { get; set; }
    public string Street { get; set; }
    public string Gender { get; set; }
    public string JamaatMembershipNumber { get; set; }
    public string? RunningProgramEntityId { get; set; }
    public RunningProgramEntity RunningProgram { get; set; }
    public string JaamatId { get; set; }
    public Jaamat Jaamat { get; set; }
}
```

### RunningProgramEntity
```csharp
public class RunningProgramEntity
{
    public string Id { get; set; }
    public string ProgramName { get; set; }
    public string Description { get; set; }
    public ICollection<Students> {get;set} = [] // many to one mapping
    // Other relevant properties
}
```

### Jaamat
```csharp
public class Jaamat
{
    public string Id { get; set; }
    public string Name { get; set; }
    public string Location { get; set; }
    // Other relevant properties
}
```

---

## UML Diagrams

### Class Diagram

![[class 1.png]]
### Activity Diagram (Registration with Chanda Number)

![[activity.png]]

### Activity Diagram (Manual Registration)

![[activity-manual.png]]

---

## Implementation Notes
- **Technology Stack**:
  - **C#** with **ASP.NET Core** for the API.
  - **Entity Framework Core** for database operations.
  - **ASP.NET Identity** for user management.
- **Validation**:
  - Chanda Number validation involves querying an external Jamaat database or service.
  - Manual input fields are validated for format (e.g., email, phone number) and required fields.
- **Status Logic**:
  - **Accepted**: If all details are valid and meet predefined criteria (e.g., verified Chanda Number, complete profile).
  - **Under Review**: If manual verification is needed (e.g., incomplete details, unverified Chanda Number).
- **Database**:
  - Use a relational database ( SQL Server, PostgreSQL) to store `StudentRegistration`, `RunningProgramEntity`, and `Jaamat` entities.
  - Ensure foreign key constraints for `RunningProgramEntityId` and `JaamatId`.

---

## Error Handling
- All endpoints return standardized error responses:
```json
{
  "error": {
    "code": "string",
    "message": "string"
  }
}
```
- Example:
```json
{
  "error": {
    "code": "INVALID_CHANDA_NUMBER",
    "message": "The provided Chanda Number is invalid or not found."
  }
}
```

---

## Security Considerations
- **Input Sanitization**: Prevent SQL injection and XSS by sanitizing all inputs.
- **Rate Limiting**: Apply rate limiting to prevent abuse of registration endpoints.
- **Data Privacy**: Ensure compliance with data protection regulations (e.g., GDPR, CCPA) for storing personal information.
- **HTTPS**: All API calls must use HTTPS to encrypt data in transit.

---

## Future Enhancements
- Implement email verification during registration.
- Add an admin endpoint to approve/reject registrations marked as **Under Review**.
