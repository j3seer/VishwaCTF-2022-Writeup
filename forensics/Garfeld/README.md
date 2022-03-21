# Challenge description

Garfeld can hide secrets pretty well.

-----------------------------------------------------------

We were given a wav file which contained a pastebin link in it's spectrum. 

Using sonic visualizer we can see it:

![image](https://user-images.githubusercontent.com/58823465/159286765-adfb9f18-19c0-4d6c-9927-70ad9ea30ecb.png)

this link had what seems to be a hexdump of a file.

![image](https://user-images.githubusercontent.com/58823465/159286736-8f76caa4-ac33-46f0-b63a-89bbd35fba44.png)


After alot of searching i found out that this is jpeg image, and we can tell because of the file headers

Notice we have:

![image](https://user-images.githubusercontent.com/58823465/159286831-4f4c6772-76f4-4395-808b-0b2920272df0.png)

and a JPEG header would look like this:

``` FF D8 FF E0 00 10 4A 46 49 46 00 01 ``` 

The common bytes are ``49 46 00 01``

Changing the headers to the correct ones:

![image](https://user-images.githubusercontent.com/58823465/159286948-3a4aa766-b522-47ad-ae92-eb95117c554d.png)


We get this image

![bruh](https://user-images.githubusercontent.com/58823465/159286972-e0821f7d-cf03-44f3-bfc5-6882dccaea09.jpeg)


we can see there's a text that looks like the flag but it's encrypted :

```xjslxjKCH{j_hidtqw_npvi_mjajioa}```

This took me the longest.. but i finally figured it out. We have to find the date of this image and use it as a Key for a gronsfeld cipher which is a version of vigenere that takes numbers as a key


![image](https://user-images.githubusercontent.com/58823465/159287042-455a4b92-8960-4d49-8cbf-76f268937ada.png)


``` Flag : vishwaCTF{i_heckin_love_lasagna} ```
