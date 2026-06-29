# Software-Testing-Portfolio
A portfolio of Java projects demonstrating unit testing, requirements-based testing, test automation, and quality assurance using JUnit 5.

### Contact Service

* `Contact.java`
* `ContactService.java`
* `ContactTest.java`
* `ContactServiceTest.java`

The Contact Service manages contact records using a unique, non-updatable contact ID. It validates required fields, enforces length and format restrictions, prevents duplicate IDs, and supports adding, deleting, retrieving, and updating contacts. The accompanying JUnit tests verify valid behavior, boundary conditions, null values, invalid formats, duplicate records, and operations involving nonexistent contacts.


### How do I interpret user needs and incorporate them into a program?

I begin by separating user needs into clear functional requirements, constraints, and expected outcomes. For the Contact Service, the user needed to create, delete, and update contact records while preserving a unique contact ID. Each field also had a specific rule, such as a maximum length or required format. I translated those statements into constructor validation, setter validation, service methods, and corresponding unit tests. This created traceability between what the user requested, how the program implemented it, and how the tests verified it.

I also consider how a user may interact with the software incorrectly. Users can enter missing data, mistype a phone number, attempt to reuse an ID, or request a contact that does not exist. Incorporating these scenarios makes the program more reliable because it responds predictably instead of failing silently. When requirements are unclear, I would ask clarifying questions, document assumptions, and confirm acceptance criteria before implementation.

### How do I approach designing software?

I approach software design by first understanding the requirements and dividing the system into components with focused responsibilities. In the Contact Service, the `Contact` class represents and validates a single contact, while the `ContactService` class manages the collection of contacts and performs service-level operations. A `HashMap` stores contacts by ID, which directly supports uniqueness checks and efficient retrieval. This separation makes the code easier to understand, test, and modify.

I also design with testability and maintainability in mind. Repeated validation logic is centralized, descriptive method names communicate intent, and each test focuses on a specific behavior. I prefer to implement the simplest design that fully satisfies the current requirements rather than adding unnecessary features. After the initial design is working, I review the code for duplication, unclear responsibilities, untested edge cases, and opportunities to improve readability without changing required behavior.

## Testing Approach

The Contact Service test suite uses:

* Positive testing to confirm valid contacts and service operations work correctly
* Boundary-value testing for maximum permitted field lengths
* Negative testing for null values, excessive lengths, malformed phone numbers, duplicate IDs, and missing records
* Regression testing by rerunning the complete test suite after code changes


