# Challenge description

Meeting Topic: VishwaCTF22- The Threat Royale Meeting number: 26203542769 When: Sunday, 20 March, 2022, 6:00 pm (4 hrs) India Standard Time GMT+05:30 flag format is Bevigil-Viit{}

https://netacad.webex.com/netacad/j.php?MTID=m215611e4b7c1d0fe264d3d0a4328515a

Attend this webinar, a file will be provided, solve it to get the flag!

-----------------------------------------------------------

in this challenge we were provided a pdf with instructions and details about the challenge



to start off, i started looking at the full report in the Bevigil website of the "Clean your phone" App 
Found this pastebin link 

``https://pastebin.com/raw/ZTqJjZgN ``

Which has this : 

``` 
String targets_tracker_filename;
return http://54.203.2.101:35911/{} + targets_tracker_filename; 
```

at first it looked like some random garbage for some remote connection related to the malware but 
as the time moved forward i asked some of the admins and turns out, we need to use this to find the flag

After a bit of searching, i found this URL:

![image](https://user-images.githubusercontent.com/58823465/159283225-2d57a27b-5cf8-4310-a3c6-ea5819ce48a1.png)


```
https://lanchesrd2fffb.firebaseio.com/zombie_location.json 
```

![image](https://user-images.githubusercontent.com/58823465/159283373-3d925765-eceb-4465-939d-1c852bac9bd3.png)

Which contained a tracker filename !! So that could be related to the link before

Using this crafted link :
````
http://54.203.2.101:35911/96ad18382614e3f36ccf87752ccfa2a4
```` 

It downloads a file that contains what seems to be IPs for the zombie bots and some random Base64 string?

![image](https://user-images.githubusercontent.com/58823465/159282858-b8d4efc8-1e64-43f7-b7d0-c96f641f8cdd.png)

Turns out it is ! 

using cyberchef we can decode it:

![image](https://user-images.githubusercontent.com/58823465/159282765-a40f6110-7f39-44bb-9013-8d14592c537d.png)


**Note:** The challenge was badly written, alot of players thought the goal was to find the second pro-add-on app but apparently it's not even needed in this case. i also was in that loop but some of the admins cleared it to me.

``` Flag : Bevigil-Viit{7hr3at_4naly5i5_i5_FuN} ```
