# What is a SQL Injection?

SQL Injection is an attack that poisons dynamic SQL statements to comment out certain parts of the statement or appending a condition that will always be true. It takes advantage of the design flaws in poorly designed web applications to exploit SQL statements to execute malicious SQL code.

## How SQL Injection Works

The types of attacks that can be performed using SQL injection vary depending on the type of database engine. The attack works on dynamic SQL statements. A dynamic statement is a statement that is generated at run time using parameters password from a web form or URI query string.

Let’s consider a simple web application with a login form. The code for the HTML form is shown below.

```php
<form action=‘index.php’ method="post">

<input type="email" name="email" required="required"/>

<input type="password" name="password"/>

<input type="checkbox" name="remember_me" value="Remember me"/>

<input type="submit" value="Submit"/>

</form>
```

Here, the above form accepts the email address, and password then submits them to a PHP file named index.php and it has an option of storing the login session in a cookie. We have deduced this from the remember_me checkbox. It uses the post method to submit data. This means the values are not displayed in the URL.


## Steps to prevent SQL injection attacks
Though SQL injection attacks are still the most dangerous threat to web administrators, the good news is that there are plenty website owners can do to mitigate the danger.  

Here are 5 steps you can take to significantly reduce the risk of falling victim to a SQL injection attack:

### Validate User Inputs
> A common first step to preventing SQL injection attacks is validating user inputs. First, identify the essential SQL statements and establish a whitelist for all valid SQL statements, leaving unvalidated statements out of the query. This process is known as input validation or query redesign.  
Additionally, you should configure inputs for user data by context. For example, input fields for email addresses can be filtered to allow only the characters in an email address, such as a required “@” character. Similarly, phone numbers and social security numbers should only be filtered to allow the specific number of digits for each.  
While this action alone won’t stop SQLi attackers, it is an added barrier to a common fact-finding tactic for SQL injection attacks. 

### Sanitize Data By Limiting Special Characters
> Another component of safeguarding against SQL injection attacks is mitigating inadequate data sanitization. Because SQLi attackers can use unique character sequences to take advantage of a database, sanitizing data not to allow string concatenation is critical. 
One way of doing this is configuring user inputs to a function such as MySQL’s mysql_real_escape_string(). Doing this can ensure that any dangerous characters such as a single quote ‘ is not passed to a SQL query as instructions. A primary method of avoiding these unauthenticated queries is the use of prepared statements. 

### Enforce Prepared Statements And Parameterization
> Sadly, input validation and data sanitization aren’t fix-alls. It’s critical organizations also use prepared statements with parameterized queries, also known as variable binding, for writing all database queries. By defining all SQL code involved with queries, or parameterization, you can distinguish between user input and code.  
While dynamic SQL as a coding technique can offer more flexible application development, it can also mean SQLi vulnerabilities as accepted code instructions. By sticking with standard SQL, the database will treat malicious SQL statements inputted like data and not as a potential command.  

### Use Stored Procedures In The Database
> Similar to parameterization, using stored procedures also requires variable binding. Unlike the prepared statements approach to mitigating SQLi, stored procedures reside in the database and are called from the web application. Stored procedures are also not immune to vulnerabilities if dynamic SQL generation is used.  
Organizations like OWASP say only one of the parameterized approaches is necessary, but neither method is enough for optimal security. Crafting parameterized queries should be done in conjunction with our other recommendations. 

### Actively Manage Patches And Updates
> Vulnerabilities in applications and databases that are exploitable using SQL injection are regularly discovered and publicly identified. Like so many cybersecurity threats, it’s vital organizations stay in tune with the most recent news and apply patches and updates as soon as practical. For SQLi purposes, this means keeping all web application software components, including database server software, frameworks, libraries, plug-ins, and web server software, up to date. 
If your organization struggles to consistently patch and update programs, a patch management solution might be worth the investment. 

## License
[XIXX](https://github.com/xixxdev/)