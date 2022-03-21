

# Challenge description

Yet another API for ‘user’ signup and login. You know the drill, GO! https://k33p-y0ur-53cr3t5.vishwactf.com/

-----------------------------------------------------------

In this challenge we have two endpoints. one of which is used by an admin . the goal is to become admin thru the jwt cookie we get with the signup endpoint



Using jwt-cracker we can crack the token

``` 
jwt-cracker abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789 eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9eyJ1c2VybmFtZSI6InRlc3QiLCJyb2xlIjoidXNlciIsImlhdCI6MTY0Nzc4ODI2Mn0.Py60wfbnD7sDP6ygXlV7q5TOHIDzGmzOxWRHdWYVeCc
``` 

this took a while but we found eventually the key used : ` "owasp" ` 