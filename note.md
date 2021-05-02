### Weekend to do list 
- Read 3 walkthroughs every day

*** 
- Remote Code Execution due to unrestricted file Upload: 
	- Minutes later I decided to change the Content-Type to bypass the client-side validation. I changed the Content-Type from application/octet-stream to image/png and image/jpg and image/jpeg but no luck but I do had a thought about to changing the content type into image/gif to see how it parses the file.

	- I quickly directed to the reverse_shell.php file location to trigger the reverse shell and all of the processes are correct but I didn’t have a reverse shell. And I finally found out that the server was configured to block outbound TCP connections.

	- So I was thinking about how to bypass that and something came up to my mind what if I create a shell inside the server and view it inside the server, so I used [powny shell](https://github.com/flozz/p0wny-shell/blob/master/shell.php) to create RCE.

***
- Account Take Over by Response Manipulation 
	- Account take over vulnerability by Manipulating the login response. 

	- I figured out that the application is using an API to authenticate the user so I intercepted the request and observe how the API handles the login process. 

	- I observed that the signup and login responses are similar but some different changes so I decided to manipulate the login response with signup response. I quickly logged out and created another account and captured the signup response of account 2(@gmail.com).

	- Again logged_in with account_1(account1@gmail.com) same email ID but different password, Intercepted the login request, and applied do->intercept this request->response in burp suite proxy and changed the response 401 unauthorized of login response into acount2@gmail.com signup response with 200 OK. 



