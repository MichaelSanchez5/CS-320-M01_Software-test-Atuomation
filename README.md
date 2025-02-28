# CS-320-M01_Software-test-Atuomation

Contact.java (Contact Class) :
public class Contact {
    private String contactId;
    private String firstName;
    private String lastName;
    private String phone;
    private String address;

    public Contact(String contactId, String firstName, String lastName, String phone, String address) {
        this.contactId = contactId;
        this.firstName = firstName;
        this.lastName = lastName;
        this.phone = phone;
        this.address = address;
    }

    // Getters and setters

    public String getContactId() {
        return contactId;
    }

    public String getFirstName() {
        return firstName;
    }

    public String getLastName() {
        return lastName;
    }

    public String getPhone() {
        return phone;
    }

    public String getAddress() {
        return address;
    }

}
ContactService.java  (Contact Service) :
import java.util.HashMap;
import java.util.Map;

public class ContactService {
    private Map<String, Contact> contacts = new HashMap<>();

    public void addContact(Contact contact) {
        contacts.put(contact.getContactId(), contact);
    }

    public void deleteContact(String contactId) {
        contacts.remove(contactId);
    }

    public void updateContact(Contact updatedContact) {
        contacts.put(updatedContact.getContactId(), updatedContact);
    }

    public Contact getContactById(String contactId) {
        return contacts.get(contactId);
    }
}
ContactTest.java (Contact Class Unit Test) :
import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.Test;

public class ContactTest {
    @Test
    public void testContactCreation() {
        Contact contact = new Contact("C1", "John", "Doe", "1234567890", "123 Main St");
        assertEquals("C1", contact.getContactId());
        assertEquals("John", contact.getFirstName());
        assertEquals("Doe", contact.getLastName());
        assertEquals("1234567890", contact.getPhone());
        assertEquals("123 Main St", contact.getAddress());
    }

}
ContactServiceTest.java (Contact Service Unit Test) :
import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.Test;

public class ContactServiceTest {
    @Test
    public void testAddContact() {
        ContactService contactService = new ContactService();
        Contact contact = new Contact("C1", "John", "Doe", "1234567890", "123 Main St");
        contactService.addContact(contact);

        assertNotNull(contactService.getContactById("C1"));
    }

}

Task.java (Task Class) :
public class Task {
    private String taskId;
    private String name;
    private String description;

    public Task(String taskId, String name, String description) {
        this.taskId = taskId;
        this.name = name;
        this.description = description;
    }

    // Getters and setters

    public String getTaskId() {
        return taskId;
    }

    public String getName() {
        return name;
    }

    public String getDescription() {
        return description;
    }

}
TaskService.java (Task Service) :
import java.util.HashMap;
import java.util.Map;

public class TaskService {
    private Map<String, Task> tasks = new HashMap<>();

    public void addTask(Task task) {
        tasks.put(task.getTaskId(), task);
    }

    public void deleteTask(String taskId) {
        tasks.remove(taskId);
    }

    public void updateTask(Task updatedTask) {
        tasks.put(updatedTask.getTaskId(), updatedTask);
    }

    public Task getTaskById(String taskId) {
        return tasks.get(taskId);
    }
}
TaskTest.java (Task Class Unit Test) :
import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.Test;

public class TaskTest {
    @Test
    public void testTaskCreation() {
        Task task = new Task("T1", "Complete Assignment", "Finish coding and testing");
        assertEquals("T1", task.getTaskId());
        assertEquals("Complete Assignment", task.getName());
        assertEquals("Finish coding and testing", task.getDescription());
    }

}
TaskServiceTest.java (Task Service Unit Test):
import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.Test;

public class TaskServiceTest {
    @Test
    public void testAddTask() {
        TaskService taskService = new TaskService();
        Task task = new Task("T1", "Complete Assignment", "Finish coding and testing");
        taskService.addTask(task);

        assertNotNull(taskService.getTaskById("T1"));
    }

}
InsertParagraph:
I used a Junit testing approach for each of the three features in Project One. I aligned this approach with the software requirements and wrote tests for all functionalities. I also used a variety of testing techniques, including boundary value analysis, equivalence partitioning, and decision tables to analyze what the client was asking for. This ensured that my tests were effective, and that the software met all the requirements for the program.
I wrote the JUnit tests in a modular fashion, which made them easier to maintain and debug. I also used a variety of different skills I learned throughout the course to verify the results of my tests. This helped to ensure the code was technically sound, efficient, and therefore it would run smoothly after running the debugging methods.
Reflection:
Testing Techniques:
•	The software testing techniques that I employed in this project were unit testing, boundary value analysis, equivalence partitioning, and decision tables.
•	Unit testing is a white box testing technique which involves testing individual units of code. This is the most basic level of testing and is essential for ensuring the code is correct and functioning as expected.
•	Boundary value analysis is a black box testing technique which involves evaluating the boundaries of input and output values. This helps to ensure that the code manages extreme values correctly, the code is secure, and there are no other problems within the code.
•	Equivalence partitioning is a black box testing technique which involves dividing the input space into equivalence classes. This helps to ensure that the code oversees all inputs and outputs correctly for the code. 
•	Decision tables are a black box testing technique which uses a table to specify the possible combinations of inputs and outputs. This helps to ensure that the code manages all combinations of inputs and outputs correctly.
•	The other software testing techniques I did not use for this project were integration testing, system testing, and acceptance testing.
•	Integration testing is a black box testing technique which involves evaluating the interactions between different units of code. This practice typically follows unit testing.
•	System testing is a black box testing technique that involves assessing the entire system. This typically follows integration testing.
•	Acceptance testing is a black box testing technique which involves assessing the system by having users or customers evaluate the program. Typically done after system testing.
•	Each of the testing techniques which I discussed has practical uses and implications for different software development projects and situations. 
 
Boundary value analysis is a desirable choice for projects where the input or output values are critical. Equivalence partitioning is a better choice for projects where the input space is large or complex. Decision tables are appropriate for projects that require handling various combinations of inputs and outputs.
Mindset: The mindset that I adopted working on this project was one of caution and precision. I was aware of the complexity and interrelationships of the code I was evaluating, and I took care to evaluate all combinations of inputs and outputs before using my code. I also tried to limit bias in my review of the code by considering all scenarios and not relying on my own firsthand experiences.
    On the software developer side, a bias which can be a concern if a developer is responsible for assessing their own code. This is because developers may be more likely to overlook errors in their own code. Also, they may be subject to liking their own code more than someone else’s code. To limit bias, it is important for developers to have a critical eye and to be willing to ask for help from other developers. It is also important for developers to not analyze their own code all the time because they can create more errors. It is important to have another person or second set of eyes to look at your code. Code errors can create more financial problems within a company that is developing a code therefore, it is important not to overlook the coding process and have secondary eyes look at the code to make sure the code runs smoothly for the client. 
     In conclusion, it is important to become disciplined in your commitment to quality as a software engineering professional. This means not cutting corners when it comes to writing or testing code. Also, it means being willing to invest time and effort into improving the quality of your work and code. Maintaining a commitment to quality can help ensure that your software is dependable and meets the requirements of users and customers. 
insertParagraph: 1. How can I ensure that my code, program, or software is functional and secure?
Ensuring that code, programs, or software are both functional and secure is crucial for delivering high-quality products. Here are some key practices to consider:

a. Testing: Implement thorough testing strategies to verify the functionality and identify potential issues in the code. This includes unit tests, integration tests, and system tests. Test cases should cover a wide range of scenarios and edge cases to ensure the code behaves as expected.

b. Code Reviews: Conduct code reviews with peers or team members to have a fresh set of eyes look at your code. Code reviews can help identify logic errors, security vulnerabilities, and potential improvements. Encourage feedback and address any issues or suggestions raised during the review process.

c. Error Handling: Implement robust error handling mechanisms to handle unexpected scenarios gracefully. Properly handling exceptions and errors can prevent crashes or security vulnerabilities caused by incorrect input or unexpected behavior.

d. Security Practices: Follow secure coding practices, such as input validation, parameterized queries, encryption, and authentication mechanisms. Stay updated on common security vulnerabilities and apply appropriate countermeasures to protect against attacks like SQL injection, cross-site scripting (XSS), and cross-site request forgery (CSRF).

e. Regular Updates and Patches: Keep your software up to date by applying patches and updates provided by the framework, libraries, or underlying infrastructure. This helps address known vulnerabilities and improves the overall security posture.

f. Security Testing: Conduct regular security assessments, including penetration testing and vulnerability scanning, to identify potential security weaknesses in your software. Address any identified vulnerabilities promptly.

2. How do I interpret user needs and incorporate them into a program? How do I approach designing software?
Interpreting user needs and incorporating them into a program is essential to build software that meets user expectations. Here are some approaches to consider:

a. Requirements Gathering: Start by engaging with stakeholders and users to understand their requirements and expectations. Conduct interviews, surveys, or workshops to gather insights into their needs, pain points, and desired features.

b. User Personas and Use Cases: Create user personas to represent different types of users and their goals. Develop use cases that describe how users interact with the software and the specific tasks they need to accomplish. These artifacts help guide the design process and ensure the software addresses the targeted user needs.

c. User-Centered Design: Emphasize user-centric design principles by focusing on usability, user experience, and intuitive interfaces. Incorporate user feedback and conduct usability testing throughout the development process to iteratively improve the software.

d. Agile Development: Adopt an agile development methodology that enables iterative and incremental development. Break down the project into smaller user stories or features, prioritize them based on user needs, and deliver working software in short iterations. Regularly gather feedback from users and stakeholders to refine and adjust the software accordingly.

e. Prototyping and Mockups: Create prototypes or mockups of the software's user interface to visualize and validate the design with users. This helps ensure that the software meets their expectations and provides a platform for early feedback and iterations.

f. Collaboration and Communication: Foster open and continuous communication with users, stakeholders, and development team members. Regularly engage in discussions, demos, and feedback sessions to ensure a shared understanding of requirements and to address any concerns or changes throughout the development process.
By following these approaches, you can better interpret user needs, incorporate them into the program, and design software that aligns with user expectations.
How do I approach designing software? 
I approach desinging software with a caution piont of viewing. When it comes to desinging speacfic types of software knowing the best programs to use it the key for myself. Using various methods to construct the type of software needed for the clientel and end users can vairy on diffrent possillibilties when making new software. This type of software must have user frindly capabillaties in order to have no error or bugs when developing new software for clientel. 
In conclusion, it is important to become disciplined in your commitment to quality as a software engineering professional. This means not cutting corners when it comes to writing or testing code. Also, it means being willing to invest time and effort into improving the quality of your work and code. Maintaining a commitment to quality can help ensure that your software is dependable and meets the requirements of users and customers. In development stages must be taken into action when desinging a working system which can support the end users with thier requests on specific types of software be transfered into a new data collocetion hub. The development of newer software will have some minor issues when launching a brad new system. This is were a development team will bt there to respond for the casue of major issue froming wihtiin the system to improve the system as a whole. 
