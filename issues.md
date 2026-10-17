# Lab 5: Static Code Analysis — Issue Log

File analyzed: library\_catalog\_system.py
Tools: Pylint, Bandit, Flake8

|Issue|Type|Original line(s)|Description|Fix Approach|
|-|-|-:|-|-|
|Shell command execution (B605)|Security - High|58|os.system() executes a shell command using a constructed string.|Remove unnecessary shell execution and use safe Python output.|
|Weak MD5 hash (B324)|Security - High|47|MD5 is unsuitable for security-sensitive hashing.|Use a suitable modern hash or redesign the function according to its actual purpose.|
|Dynamic eval (B307)|Security - Medium|42|eval() can execute arbitrary Python expressions.|Replace it with direct fine calculation using validated numeric inputs.|
|Silent exception (B110)|Quality/Security - Low|23-27|A broad exception is silently ignored.|Catch the expected exception and handle invalid book IDs explicitly.|
|Insecure random PIN (B311)|Security - Low|50-51|random is unsuitable for security-sensitive PIN generation.|Use the secrets module for PIN generation.|
|Mutable default argument (W0102)|Bug risk|15|active\_issues=\[] is shared between calls.|Use None as the default and create a new list when needed.|
|Unused import (F401)|Style|6|csv is imported but never used.|Remove the import if it is unnecessary.|
|Unused variables (F841/W0612)|Quality|31, 41|late\_fee and days are assigned but unused.|Remove them or use them meaningfully.|
|Incorrect None comparison (E711/C0121)|Style|32|Uses == None instead of is None.|Change the comparison to is None.|
|File handling (W1514/R1732)|Quality|55-57|File encoding is unspecified and the file is not managed by a context manager.|Use with open(..., encoding="utf-8").|
|Naming convention (C0103)|Style|15|issueBook does not use snake\_case.|Rename to issue\_book and update its callers.|
|Missing docstrings (C0116)|Maintainability|Multiple|Functions lack descriptions.|Add concise docstrings.|
|Missing final newline (C0304/W292)|Style|73|File does not end with a newline.|Add a final newline.|



\## Verification Results



\### Before fixes

\- Pylint score: 5.32/10

\- Bandit: 5 findings (2 High, 1 Medium, 2 Low)

\- Flake8: 6 findings



\### After fixes

\- Pylint score: 10.00/10

\- Bandit: No issues identified

\- Flake8: No violations reported



\### Flake8 findings addressed

\- F401: Removed unused csv import.

\- E722: Removed bare exception handling.

\- F841: Removed unused late\_fee and days variables.

\- E711: Changed comparison with None to an is None check.

\- W292: Added the final newline.



Note: Line numbers refer to the original file and may change after fixes.

