---
title: 'Software Architecture'
weight: 1
---

## The Twelve Factor App
1. Codebase - One codebase tracked in revision control, many deploys
2. Dependencies - Explicitly declare and isolate dependencies
3. Config Store config in the environment
4. Backing services Treat backing services as attached resources
5. Build, release, run Strictly separate build and run stages
6. Processes Execute the app as one or more stateless processes
7. Port binding Export services via port binding
8. Concurrency Scale out via the process model
9. Disposability Maximize robustness with fast startup and graceful shutdown
10. Dev/prod parity Keep development, staging, and production as similar as possible
11. Logs Treat logs as event streams
12. Admin processes Run admin/management tasks as one-off processes
[Written by Adam Wiggins](https://12factor.net/)

## API Strategy
* The factors to consider while designing an API Strategy:
* Reusability
* Maintainability
* Scalability
* API Documentation
* Security
* Versioning
* Error Handling
* Traceability
* API Deployment
* API Naming Conventions

## Solid Principles
* Single responsibility principle - A class should only have a single responsibility, that is, only changes to one part of the software’s specification should be able to affect the specification of the class. 
* Open—closed principle - “Software entities … should be open for extension but closed for modification.”
* Liskov substitution principle - “Objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program.” See also design by contract
* Interface segregate - Many client-specific interfaces are better than one general-purpose interface.”
* Dependency inversion principle - One should “depend upon abstractions, not concretions.”  





