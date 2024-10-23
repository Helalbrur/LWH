# Include, Include Once, Require, and Require Once in PHP
## Include
The include statement is used to include and evaluate a specified file. If the file cannot be found, a warning is issued, but the script continues execution.

```php
Copy code
include 'header.php'; // Includes header.php
Include Once
The include_once statement is similar to include, but it ensures that the file is included only once during the script execution. If the file has already been included, it will not be included again.
```

```php
Copy code
include_once 'header.php'; // Includes header.php only once
Require
The require statement is similar to include, but if the specified file cannot be found, it produces a fatal error and stops the script execution.
```

```php
Copy code
require 'config.php'; // Requires config.php
Require Once
The require_once statement is similar to require, but it ensures that the file is included only once during the script execution.
```
```php
Copy code
require_once 'config.php'; // Requires config.php only once
Differences between Include, Include Once, Require, and Require Once
Feature	Include	Include Once	Require	Require Once
Behavior on Error	Warning (script continues)	Warning (script continues)	Fatal error (script stops)	Fatal error (script stops)
File Inclusion	Includes every time	Includes only once	Requires every time	Requires only once
```

### Differences between Include, Include Once, Require, and Require Once

| Feature                | Include                      | Include Once                  | Require                     | Require Once                |
|------------------------|------------------------------|-------------------------------|-----------------------------|-----------------------------|
| Behavior on Error      | Warning (script continues)   | Warning (script continues)    | Fatal error (script stops)  | Fatal error (script stops)  |
| File Inclusion         | Includes every time          | Includes only once            | Requires every time         | Requires only once          |
