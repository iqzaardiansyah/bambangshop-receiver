<details>
<summary>Tutorial Module 7</summary>

<details>
<summary>Reflection Subscriber-1</summary>

1. In this tutorial, we used **RwLock<>** to synchronise the use of **Vec** of **Notifications**. Explain why it is necessary for this case, and explain why we don’t use **Mutex<>** instead?

    In the provided code, the usage of **RwLock<Vec<Notification>>** is essential to synchronize access to the shared **Vec** of **Notifications** within the **NotificationRepository**. This choice ensures that multiple threads can safely read from the data structure concurrently or allow a single thread to modify it at a time, preventing data races and maintaining thread safety. **RwLock** is preferred over **Mutex** in this scenario because it allows multiple threads to read the notifications list concurrently, improving concurrency and performance, particularly in scenarios with frequent read operations. Using **Mutex** would restrict access to a single thread at a time, potentially leading to unnecessary blocking and reduced concurrency. Therefore, **RwLock** is the appropriate choice when both read and write access need to be coordinated effectively to maximize concurrency while ensuring thread safety.

2. In this tutorial, we used **lazy_static** external library to define **Vec** and **DashMap** as a “**static**” variable. Compared to Java where we can mutate the content of a **static** variable via a **static** function, why didn't Rust allow us to do so?

    In Rust, static variables are immutable by default, meaning they cannot be modified after initialization, aligning with Rust's emphasis on safety and preventing common programming errors like data races. This design choice ensures thread safety by preventing concurrent modification of static variables, contributing to Rust's reputation for safety and reliability in concurrent programming scenarios. Conversely, in Java, static variables can be mutated via static functions, which can lead to mutable shared state and potential concurrency issues if not managed carefully. While this approach offers flexibility, it also introduces risks, such as data races and unpredictable behavior in concurrent environments. Rust's enforcement of immutability for static variables underscores its commitment to safety and reliability in concurrent programming, even if it requires more explicit handling of shared state compared to Java.

</details>

<details>
<summary>Reflection Subscriber-2</summary>

1. Have you explored things outside of the steps in the tutorial, for example: src/lib.rs? If not, explain why you didn’t do so. If yes, explain things that you’ve learned from those other parts of code.

    The `src/lib.rs` file defines essential components for a Rust application, including configuration handling (`AppConfig`), error handling utilities (`Result`, `Error`, `ErrorResponse`, `compose_error_response`), and initialization of a Reqwest HTTP client (`REQWEST_CLIENT`). These components are crucial for building a robust and functional application beyond the scope of a tutorial. Understanding and exploring these additional parts of the codebase is essential for gaining insights into various aspects of Rust programming and developing more robust and maintainable Rust applications.

2. Since you have completed the tutorial by now and have tried to test your notification system by spawning multiple instances of Receiver, explain how Observer pattern eases you to plug in more subscribers. How about spawning more than 1 instance of Main app, will it still be easy enough to add to the system?

    The Observer pattern facilitates the integration of additional subscribers into the notification system by providing a flexible and scalable architecture. Each subscriber acts as an observer that receives notifications from the main application, allowing for easy customization and extensibility. By adhering to the Observer pattern, adding new subscribers involves implementing the subscriber interface and registering them with the main application, without requiring modifications to the core functionality. Furthermore, spawning multiple instances of the main application is also straightforward, as each instance can maintain its list of subscribers independently, enabling parallel processing of notifications. This modular and scalable design ensures that the notification system can accommodate growth and handle increased workload efficiently while maintaining flexibility for future expansion.

3. Have you tried to make your own Tests, or enhance documentation on your Postman collection? If you have tried those features, tell us whether it is useful for your work (it can be your tutorial work or your Group Project)

    Creating tests in tools like Postman enables developers to automate the process of verifying API endpoints and responses, ensuring application reliability and stability through automated regression testing and validation against expected behaviors. On the other hand, enhancing documentation within Postman collections by including descriptions, examples, and usage instructions fosters better communication and collaboration within development teams, reduces onboarding time for new developers, and ensures consistency in API usage across the project. Overall, leveraging these features can significantly improve the development process, software quality, and collaboration among team members in various projects.

</details>
</details>