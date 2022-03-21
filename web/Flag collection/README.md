# Challenge description

We are collecting cool flag names for our next CTF, please suggest us some cool names and we’ll store them in our database for our next CTF. https://fl4g-c0ll3ct10n.vishwactf.com/

-----------------------------------------------------------

in this challenge we find some interesting thing in the source code




The above are config settings for a firebase app, we can use these to access the database which will eventually contain the flag


searching for a while found a good resource here :
*** https://book.hacktricks.xyz/pentesting/pentesting-web/buckets/firebase-database ***

i tried using a python script , some other tools. eventually the tool Baserunner worked !



And there's our flag:

``` Flag : vishwactf{c0nfigur3_y0ur_fir3b@s3_rule$} ```