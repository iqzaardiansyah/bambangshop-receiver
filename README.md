<details>
<summary>Tutorial Module 7</summary>

<details>
<summary>Reflection Subscriber-1</summary>

1. In this tutorial, we used **RwLock<>** to synchronise the use of **Vec** of **Notifications**. Explain why it is necessary for this case, and explain why we don’t use **Mutex<>** instead?

    In the provided code, the usage of **RwLock<Vec<Notification>>** is essential to synchronize access to the shared **Vec** of **Notifications** within the **NotificationRepository**. This choice ensures that multiple threads can safely read from the data structure concurrently or allow a single thread to modify it at a time, preventing data races and maintaining thread safety. **RwLock** is preferred over **Mutex** in this scenario because it allows multiple threads to read the notifications list concurrently, improving concurrency and performance, particularly in scenarios with frequent read operations. Using **Mutex** would restrict access to a single thread at a time, potentially leading to unnecessary blocking and reduced concurrency. Therefore, **RwLock** is the appropriate choice when both read and write access need to be coordinated effectively to maximize concurrency while ensuring thread safety.

2. In this tutorial, we used **lazy_static** external library to define **Vec** and **DashMap** as a “**static**” variable. Compared to Java where we can mutate the content of a **static** variable via a **static** function, why didn't Rust allow us to do so?

    In Rust, static variables are immutable by default, meaning they cannot be modified after initialization, aligning with Rust's emphasis on safety and preventing common programming errors like data races. This design choice ensures thread safety by preventing concurrent modification of static variables, contributing to Rust's reputation for safety and reliability in concurrent programming scenarios. Conversely, in Java, static variables can be mutated via static functions, which can lead to mutable shared state and potential concurrency issues if not managed carefully. While this approach offers flexibility, it also introduces risks, such as data races and unpredictable behavior in concurrent environments. Rust's enforcement of immutability for static variables underscores its commitment to safety and reliability in concurrent programming, even if it requires more explicit handling of shared state compared to Java.

</details>

</details>