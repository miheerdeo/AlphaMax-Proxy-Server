Multi-Threaded Proxy Server with Caching
This project implements a multi-threaded proxy server in C, designed to handle multiple client requests concurrently, cache responses for quick retrieval, and manage access through synchronization mechanisms like semaphores. The proxy server can enhance browsing speed, restrict certain sites, and anonymize requests by concealing the client’s IP address from the server.

Table of Contents
Introduction
Basic Working Flow
Multi-Threading Implementation
Project Motivation
Features of the Proxy Server
Operating System Components Used
Limitations
Future Extensions
How to Run
Demo
Introduction
This project explores the implementation of a multi-threaded proxy server that processes client requests, caches responses, and manages access to resources concurrently. The proxy server improves browsing efficiency and offers functionalities such as website restriction and anonymized browsing.

Basic Working Flow
Client Request: The client sends a request to the proxy server for a webpage.
Request Handling: The proxy server checks its cache for a stored response.
If cache hit: The cached data is served.
If cache miss: The request is forwarded to the intended server.
Response Handling: The proxy receives the response from the target server, caches it, and forwards it to the client.
Multi-Threading Implementation
Multi-threading is achieved using semaphores for synchronization rather than condition variables and the pthread_join()/pthread_exit() functions. Key details:

Semaphore Use: sem_wait() and sem_post() functions are used, which do not require a specific thread ID, making them a simpler option for handling concurrency.
Avoiding pthread_join: Avoiding pthread_join() allows the proxy to run multiple threads without waiting for specific threads to finish.
Project Motivation
This project provides insights into:

The lifecycle of client-server requests.
Handling concurrent requests from multiple clients.
Concurrency through locking and synchronization.
Caching and managing cached responses to optimize performance


Operating System Components Used:-
Threading: Allows handling multiple client requests concurrently.
Locks: Ensures safe access to shared resources.
Semaphores: Manages synchronization between threads without specific thread dependencies.
Cache: Utilizes an LRU (Least Recently Used) algorithm to store and retrieve frequently accessed data.

Limitations
Cache Redundancy: If a URL opens multiple clients simultaneously, each client’s response is cached separately, which can fragment responses.
Fixed Cache Size: Larger websites may not fit into the cache.
Future Extensions
Multiprocessing: The proxy could be enhanced to use multiprocessing for better performance.
Advanced Access Control: Specify which types of websites should be allowed.
Extended Request Handling: Implement additional HTTP methods like POST.
