\# Lab 5: Static Code Analysis — Reflection



\### 1. What is static code analysis, and why is it useful?

Static code analysis examines source code without executing it. It helps identify potential bugs, security vulnerabilities, unused variables, and coding-style violations early in development.



\### 2. What issues did you identify and fix?

I fixed security issues involving `eval()`, MD5 hashing, insecure random PIN generation, shell command execution, and broad exception handling. I also corrected a mutable default argument, removed unused imports and variables, improved file handling, added docstrings, and fixed formatting issues.



\### 3. What did Pylint, Bandit, and Flake8 help you identify?

Pylint identified code-quality and maintainability issues, Bandit identified potentially insecure coding patterns, and Flake8 identified style and formatting violations. Using all three provided complementary checks.



\### 4. How did static analysis improve your program?

After the fixes, Pylint's score increased from 5.32/10 to 10.00/10. Bandit reported no issues, and Flake8 reported no violations. The process improved code readability, maintainability, and security while preserving the program's main functionality.

