Multi-Threaded Proxy Server with Caching
This project implements a multi-threaded proxy server in C, designed to handle multiple client requests concurrently, cache responses for quick retrieval, and manage access through synchronization mechanisms like semaphores.

High Level Design:-

![image alt](diagram-export-11-15-2024-12_42_18-PM.png)

Low Level Design

![image alt](uml_diagram.jpeg)

Limitations
1)Cache Redundancy:  If a URL opens multiple clients simultaneously, each client’s response is cached separately, which can fragment responses.
2)Fixed Cache Size: Larger websites may not fit into the cache.

Future Extensions
1)Multiprocessing: The proxy could be enhanced to use multiprocessing for better performance.
2)Advanced Access Control: Specify which types of websites should be allowed.
3)Extended Request Handling: Implement additional HTTP methods like POST.
