# Lab 5: Static Code Analysis — Issue Documentation

## Issues Identified and Fixed

| Issue | Type | Tool | Description | Fix Applied |
|---|---|---|---|---|
| Mutable default argument | Bug | Pylint | `member_log=[]` was shared across function calls. | Changed default to `None` and initialized inside the function. |
| Unsafe `eval()` | Security | Pylint, Bandit | Evaluated a string as executable Python code. | Replaced the expression with a numeric discount-rate parameter. |
| Weak MD5 hash | Security | Bandit | MD5 is unsuitable for security-sensitive hashing. | Replaced MD5 with SHA-256. |
| Insecure random PIN | Security | Bandit | Standard `random` is not designed for security-sensitive values. | Used `secrets.randbelow()` to generate the PIN. |
| Shell command execution | Security | Bandit | `os.system()` could expose the program to command injection. | Removed shell execution and used `print()`. |
| Hardcoded secret | Security | Bandit | A secret was embedded directly in the source code. | Removed the hardcoded secret. |
| Bare exception | Code quality | Pylint, Flake8, Bandit | Used a broad `except` that silently ignored errors. | Used `dict.pop()` with a default value. |
| Missing docstrings | Code quality | Pylint | Functions did not explain their purpose. | Added function docstrings. |
| Naming convention | Style | Pylint | Function names did not follow snake_case. | Renamed functions using snake_case. |
| Unused variables and imports | Code quality | Pylint, Flake8 | Unused names reduced code clarity. | Removed unused imports and variables. |
| File handling | Code quality | Pylint | File was opened without a context manager or explicit encoding. | Used `with open(..., encoding="utf-8")`. |
| Line length and final newline | Style | Flake8 | Lines exceeded the style limit and the file lacked a final newline. | Reformatted lines and added a final newline. |

## Verification

- **Initial Pylint score:** 4.81/10
- **Final Pylint score:** 10.00/10
- **Initial Bandit findings:** 6
- **Final Bandit findings:** 0
- **Final Flake8 report:** No issues reported.
