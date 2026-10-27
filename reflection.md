# Lab 5: Static Code Analysis — Reflection

## 1. What is static code analysis?

Static code analysis examines source code without executing the program. It helps identify potential bugs, security vulnerabilities, coding standard violations, and maintainability issues.

## 2. What are the purposes of Pylint, Bandit, and Flake8?

- **Pylint:** Checks code quality, naming conventions, missing docstrings, unused variables, and potential programming errors.
- **Bandit:** Detects common security vulnerabilities and unsafe coding practices.
- **Flake8:** Checks Python style guidelines, formatting, line length, and other code quality issues.

## 3. What issues were identified in this program?

The tools identified issues including mutable default arguments, unsafe use of `eval()`, weak MD5 hashing, insecure random PIN generation, shell command execution, a hardcoded secret, missing docstrings, naming violations, unused variables, and formatting errors.

## 4. How were the issues fixed?

The code was modified to use a `None` default for the member log, replace `eval()` with a numeric discount-rate parameter, use SHA-256 hashing and secure PIN generation, remove shell execution and the hardcoded secret, improve file handling, add docstrings, follow snake_case naming, and fix formatting issues.

## 5. What were the final analysis results?

- Initial Pylint score: 4.81/10
- Final Pylint score: 10.00/10
- Initial Bandit findings: 6
- Final Bandit findings: 0
- Final Flake8 report: No issues reported.

## 6. What did you learn from this lab?

This lab demonstrated that static analysis tools can identify problems before a program is executed. Pylint helped improve code quality, Bandit highlighted insecure coding practices, and Flake8 helped enforce consistent formatting. Running the tools again after making changes helped verify that the reported issues had been addressed.
