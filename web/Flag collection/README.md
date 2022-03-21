# Challenge description

We are collecting cool flag names for our next CTF, please suggest us some cool names and we’ll store them in our database for our next CTF. https://fl4g-c0ll3ct10n.vishwactf.com/

-----------------------------------------------------------

in this challenge we find some interesting thing in the source code




The above are config settings for a firebase app, we can use these to access the database which will eventually contain the flag


searching for a while found a good resource here :
*** https://book.hacktricks.xyz/pentesting/pentesting-web/buckets/firebase-database ***

i tried using a python script , some other tools. eventually the tool Baserunner worked !

first step is to collect all the config elements as well as the db url !! which is the most important, then you have to READ a collection. replacing ==COLLECTION== with flag will print out all the elements inside the flag table/collection.

![image](https://user-images.githubusercontent.com/58823465/159277688-8f8e8fec-574f-4ac2-b8bb-616429eae4be.png)

output:
![image](https://user-images.githubusercontent.com/58823465/159277880-b3e912cf-f49c-4819-a251-9d397593b8cd.png)


And there's our flag:

``` Flag : vishwactf{c0nfigur3_y0ur_fir3b@s3_rule$} ```
