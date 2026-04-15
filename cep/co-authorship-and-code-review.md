# Co-authorship and Code Review

For all code merged into the main branch, there must be evidence that either co-authorship or code review occurred. Co-authorship of code or code reviews must be used to identify and eliminate any code that may cause harm.

There are three approved methods. Other methods may be approved if they are secure and require user authentication with a trusted system.

```mermaid
graph LR
    A[Software Engineer 1] -- Submits Pull Request --> B[Software Engineer 2]
    B -- Accepts Pull Request --> C[Pull Request Merged]

    D[Software Engineer 1] -- Commits & Pushes to Main Branch --> E[Software Engineer 2]
    E -- Comments on Commit --> F[Commit Reviewed]

   ```
