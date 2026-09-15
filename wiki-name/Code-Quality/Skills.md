# UNA CMS V14 – Code Quality

We build a great development environment to make development faster with better code quality. There are the best available tools to make development more productive and collaborative. Also, there is an overview of the enhancements in the code and development environment to make **UNA** the best version ever released.

## Quick rules for AI coding agents

When generating or modifying UNA CMS code, always:

- Aim for **high code quality**: no notices/warnings under `E_ALL`, no duplicates, no `eval()`.
- Use **prepared SQL statements** and proper input/output filtering.
- Ensure every includable PHP file has an **inclusion check** (`defined('BX_DOL') or die`).
- Follow UNA’s **security practices** (CSRF tokens, escaping, hashed passwords/data).
- Write code that can be covered by **unit tests** (PHPUnit) and fits into UNA’s CI/CD flow.

If a requested change would reduce code quality or break these practices, propose a safer/cleaner alternative.

---

## 1. Code and issues on GitHub

Code and tickets (now issues) are on [GitHub](https://github.com/).  
GitHub allows us to make code better and more secure; now everyone can help by committing pull requests. We check each pull request very carefully and accept only quality code.

## 2. Automated unit tests

Code is automatically tested upon each new code push. However, code coverage is low for now, but we will add more unit tests in the future. Unit tests are powered by [PHPUnit](https://phpunit.de/).

## 3. Automatic packaging

Upon every new code push, a ready-to-install version is packaged. It's not even nightly builds; it prepares a new package as soon as new code is added to the repository, even every 2 minutes. So you can always get the latest installable development version and test it for new features and report bugs. It will allow us to fix reported bugs even before beta version.

## 4. Automatic live demo install

The live demo site is installed upon each new code push to **GitHub**. So if you don't want to download and install the development version yourself, the live version is always available for tests. It is reset and reinstalled as soon as new code is available. Hopefully this will allow us to detect any bugs very early to make future beta and final releases as bug-free as possible.

## 5. Automatic code quality analysis tools

Code is continuously tested for any duplicated code. We already cleaned the code to get rid of any duplicates:

![UNA duplicate code trend](images/code-quality-duplicate-code-trend.png)

and we watch for any new ones, if they are occasionally added.

## 6. Continuous integration

Everything above is working together (thanks to [Jenkins](https://jenkins.io/)) and the history of changes is saved and presented as visual graphs.  
Importantly, it immediately notifies the developer by email if they commit code which is not installable or some tests fail, making them fix the problem ASAP.

## 7. Command line tools

**UNA** can be installed with just one command-line command with any set of modules, or modules can be installed using a command-line script. So testing a separate install is really easy. Also, I believe it will make life easier for hosting operators, allowing them to install UNA just in seconds.  
It will also make integration with automated install tools more consistent since the same script is used to install UNA using the built-in wizard, or command-line install by the operator, or using automated install tools.

## 8. Highest error reporting level during development

UNA is developed with **E_ALL error** reporting level, so even notices are not emitted anymore.

## 9. Standardised code style

[PSR-1 code style standard](http://www.php-fig.org/psr/psr-1/) was used. Also, an automated script was used to clean up existing code.

## 10. No evals in the code

We cleaned up any evals from the code and DB to make code more secure and easier to debug.

## 11. Prepared SQL statements

All SQL queries were rewritten to use prepared statements. If properly used, then no SQL injection is possible at all. We encourage others to use prepared statements as well.

## 12. Proper file inclusion check

Every file has an inclusion check, so PHP files which are supposed for inclusion can't be accessed directly. It will make code more secure in general.

## 13. Code review

We review every line of newly added code before it goes to production.

## 14. Internal powerful collaboration tools

It allows us to solve any problems quickly, thanks to modern technologies which help to communicate within the team, even if someone isn't at the workplace.

## 15. Testing issues on almost every possible device using [BrowserStack](http://browserstack.com/)

![BrowserStack](images/browserstack-logo-300x158.png)

## 16. UNA security practices

### Users

- User can delete all his data, right to be forgotten – standards compliance  
- Multilevel ACL (users, admins, operators) – fine-grained permissions  

### Code

- HTML/SVG input validation (HTMLPurifier & svg-sanitizer) – there is no potentially dangerous code submitted  
- Output escaping – prevent XSS attacks  
- No evals in PHP code  
- Proper file inclusion check – so there are only several "entry" PHP files; other code isn't directly accessible  

### DB

- Prepared statements are always used to prevent SQL injection attacks  
- Hashed passwords – no clear passwords are stored  
- Hashed personal data (like IPs) – minimal personal data is stored, no user tracking  

### Forms

- CSRF tokens to prevent form auto-submission and double submissions  
- Form leave notifications – to prevent accidental data loss  

### Cookies

- HTTP only & secure flags – it's impossible to steal sensitive cookies  
- Cookies consent (optional) – it complies with standards  

### CI/CD

- Unit tests – PHP code testing  
- UI tests – frontend functionality testing  
- Duplicate code scans  

### Code scans

- Dependabot – early notification of vulnerabilities in 3rd-party libraries  
- CodeRabbit – smart code review  
- Snyk, SonarQube – code scan for potential problems
