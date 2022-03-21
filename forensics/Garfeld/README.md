# Challenge description

Garfeld can hide secrets pretty well.

-----------------------------------------------------------

We were given a wav file which contained a pastebin link in it's spectrum. 

Using sonic visualizer we can see it:


this link had what seems to be a hexdump of a file.


After alot of searching i found out that this is jpeg image, and we can tell because of the file headers

Notice we have:

and a JPEG header would look like this:

``` FF D8 FF E0 00 10 4A 46 49 46 00 01 ``` 

Changing the headers to the correct ones:


We get this image



we can see there's a text that looks like the flag but it's encrypted :



This took me the longest.. but i finally figured it out. We have to find the date of this image and use it as a Key for a gronsfeld cipher which is a version of vigenere that takes numbers as a key




``` Flag : vishwaCTF{i_heckin_love_lasagna} ```