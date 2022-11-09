![image](https://user-images.githubusercontent.com/68239030/200747342-37e7e3a5-bbd3-4350-8804-7128abf896ad.png)
Step 1: Download the files and move it to kali.
Now we need try to get more information on hari.gif using exiftool.
Command: exiftool hari.gif  
![image](https://user-images.githubusercontent.com/68239030/200747436-5bbfbcf2-f247-4036-bd71-5a09bd73e9ad.png)
After running the command we see that 1337haribahadur is the handle of the Author, to find the users social we use the tool SHERLOCK to identify on which social media site the username is registered on.
Command : python3 sherlock 1337haribahadur --timeout 1
![image](https://user-images.githubusercontent.com/68239030/200747624-50fe4b5f-102f-4c93-b210-e26c63f9a4c1.png)
Going through the websites above, only valid account is of Pintrest
![image](https://user-images.githubusercontent.com/68239030/200747660-3fdade74-1c46-4eee-933b-c7689b21c5b2.png)
In the profile we can see the URL of the CTF: GitHub - 1337mickey/oh-ho
We are welcomed with the GitHub page, after downloading the README.md file when we try to edit it we get the following things:
![image](https://user-images.githubusercontent.com/68239030/200747904-730f4d8e-ef83-446d-98ac-cefa89c4d946.png)
We find that <span style="color:1337madanbahad1 has some social media"></span>   In addition to the readme file . Color:13377…. Isn’t a real color so,
Let’s find what 1337madanbahad1 means with the help of Sherlock 
![image](https://user-images.githubusercontent.com/68239030/200747932-2f68f1c5-a281-439a-a423-2f8dbb8493b7.png)
Among the results twitter account seems to have an account which has multiple tweets on April 04
The tweets are:
1.	unko ghar kathmandu ho hai
2.	aba arko directory jam teso va ghar malik ko name bata, ani OSINT ko antya garam, jay sambhu
3.	lu lu hari bahadur hack handinu paro k sir,
4.	yo **BSSID** 20:57:AF:3E:BF:90 unko ghar ko ho re
5.	tapai ta hacker pani po ho re ta
6.	tyo agadi ko bato chai tyo ximeki xa ni maile man parako wala, tesko name ho
7.	was waiting for you to come here, hari bahadur dai ho?
8.	k xa gaich aaye pugeu

What is BSSID?
 Ans: BSSID stands for Basic Service Set Identifier, and it’s the MAC physical address of the access point or wireless router that is used to connect to the Wi-Fi.
When we search the BSSID 20:57:AF:3E:BF:90 on wiggle we get the following results:
![image](https://user-images.githubusercontent.com/68239030/200748018-17dcc9c6-090d-4233-84f0-e69f35045838.png)
![image](https://user-images.githubusercontent.com/68239030/200748042-837fe170-c91d-4bae-b9fb-40de3c422e4c.png)

After that we know from tweet no.2 we got that the next directory is Pratikxya, but what is the main domain where /pratikxya is located ?
For that we need to again analysis the  EH_Assignment1.pdf  file.
After installing and running the pdfxplx through GitHub we get the following result
![image](https://user-images.githubusercontent.com/68239030/200748095-c26dc33c-5435-429c-88dc-9574cf7211b5.png)

Through link 1 we found the main domain of the puzzle. i.e  https://haridai.sushilphuyal.com.np/
![image](https://user-images.githubusercontent.com/68239030/200748179-12ba694f-19f6-42fd-875b-ce6d436b00b8.png)
Now we found that the address is https://haridai.sushilphuyal.com.np/Pratikxya 
When we go the site and play around, after a while we find the right click is disabled.  Why is that?
![image](https://user-images.githubusercontent.com/68239030/200748205-45e6949a-cc19-49e3-85e4-cb36c314ebf6.png)
To view the source code we have many options.
1)	press CTRL+SHIFT+I ( which also seems disabled)
2)	click on the 3 bars on the right of the Firefox application and navigate to more tools>web developer options
3)	Type view-source:URL to view the source code of the website.
(view-source:https://haridai.sushilphuyal.com.np/Pratikxya/)
![image](https://user-images.githubusercontent.com/68239030/200748243-a79070e7-d187-4664-ab97-2c27b52f0c11.png)
![image](https://user-images.githubusercontent.com/68239030/200748263-9f500f7c-da51-4c43-9b8b-00286c37a562.png)
We can see that there are some numbers and a comment in the source code i.e (alhabet=a-z  hint: left or right then xeh it). Which is HEX in reverse? 
After that value we got lets decode it using cyber chef.
Indeed it’s a HEX value.
![image](https://user-images.githubusercontent.com/68239030/200748354-a21c72ae-02ef-4bd9-9e37-c2c130ac6901.png)
Which leads to **tlyvahohzhpyhtyv** . This looks like a cipher text. 
After going to https://www.dcode.fr we found that the hidden code is "**merotahasairamro**"

![image](https://user-images.githubusercontent.com/68239030/200748441-95f50657-1c2c-4d9d-8579-637f605c1675.png)
Therefore the other directory is “**merotahasairamro**”

After finding the new directory: https://haridai.sushilphuyal.com.np/Pratikxya/merotahasairamro/
We can see the same properties of the page are same as other pages and we can use view-source: to see the hidden contents:
![image](https://user-images.githubusercontent.com/68239030/200748545-9508ce9a-7b14-4683-9f4d-89b25ab4adc0.png)
We got a random number 9006AE0503F215E1886570817A4A379A and a hit which says that the hash name starts from N.
What is a hash or a hash value?
Ans : A hash value (or simply hash), also called a message digest, is a number generated from a string of text. The hash is substantially smaller than the text itself, and is generated by a formula in such a way that it is extremely unlikely that some other text will produce the same hash value.
After going to the website https://www.onlinehashcrack.com 
we see that one ALGORITHM that starts with N. i.e NTML let’s try that
![image](https://user-images.githubusercontent.com/68239030/200748659-78f4e68a-52db-4009-bd79-1d6012a8ed88.png)

Or let’s go to https://crackstation.net and try to find hash.
![image](https://user-images.githubusercontent.com/68239030/200748708-324fa5ef-ec3a-4919-b213-6d92648cee31.png)
And it worked!
Hash                            	Type  Result
9006AE0503F215E1886570817A4A379A	NTLM	blue97

The hashing type is NTLM and the work/Result is blue97
When we add blue97 to the website:
https://haridai.sushilphuyal.com.np/Pratikxya/merotahasairamro/ 
 i.e 
https://haridai.sushilphuyal.com.np/Pratikxya/merotahasairamro/blue97 
We hear a voice singing pretending it to be a song.  But have some high frequency sound from the ending of 11 second mark. 
When we cut the sound and upload it to audio decoder > Morse Decoder we get namaste as a result.
Again adding Namaste to the link leads us to : 
https://haridai.sushilphuyal.com.np/Pratikxya/merotahasairamro/blue97/namaste
![image](https://user-images.githubusercontent.com/68239030/200748864-04c5b693-7fb9-4381-8de2-bab955c0d00f.png)
Which I turned on my dark mode and saw “the next path format YYYY-YYYY” we can also see it through Command: view-source: URL

![image](https://user-images.githubusercontent.com/68239030/200748937-3a58f329-ded0-4262-8968-3f9443bf3148.png)

With the help of google we got to know the birth year of Hari Bansha Acharya (role player as Hari Bahadur) is 1957 and his wife (Meera Acharya) died on 2011.


![image](https://user-images.githubusercontent.com/68239030/200748971-8da0e0fe-7c15-45a2-95bf-87a051c5184b.png) ![image](https://user-images.githubusercontent.com/68239030/200748983-01951f4f-3e3d-4b50-82ce-99ae8bc04572.png)

Finally we get an address i.e: https://haridai.sushilphuyal.com.np/Pratikxya/merotahasairamro/blue97/namaste/1957-2011
This says: 
![image](https://user-images.githubusercontent.com/68239030/200749032-41188954-dbd3-42f9-acfd-64c9c0f80d6f.png)


Before that what is a User-Agent?
When a developer wants to give a similar experience to all the users visiting their website, irrespective of devices (phone, tablet, PC), environment (windows, kali) or platform (Opera-mini, Firefox, Chrome) they are using to view the page to do that User-Agent is used. User-Agent is used to identify what device is used so that optimum settings can be provided to the user for similar experience.
And now, what does that Haribahadur can only access means?
Haribahadur in this case is the user-Agent which shows a specific response when the value is: 
 User-Agent : HariBahadur 
instead of 
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:91.0) Gecko/20100101 Firefox/91.0
We can do that by going to the developer mode with CTRL+SHIFT+i 

![image](https://user-images.githubusercontent.com/68239030/200749084-c3930575-3107-48cc-a252-c65cb40b0f8d.png)

And click on Resend> Edit and resend > replace Mozilla/5.0 (X11; Linux x86_64……. With  HariBahadur >  and click on Send 
![image](https://user-images.githubusercontent.com/68239030/200749131-8e60421f-e0cd-44ad-b9a9-bac4065c0347.png)

What to do when we see “Can you print the fl⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠ag”?
We can see almost no hits after this message. It says if we can print the flag? Technically we cannot print the text flag, so there must be something in the text. Probably there is a private message with zero-width characters. 
What is a zero-width character? 
Also known as ZWSP is a non-printing character which is used to hide secret message in a plane text. 
When we try to decode : “can you print the fl⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠⁠ag? “
On https://neatnik.net/steganographr we get bWFoYV9qb2Rp  
![image](https://user-images.githubusercontent.com/68239030/200749162-0d56d2df-9654-4494-9792-a87ecedc7866.png)

The above word can be a secret message so we will use cyberchef to decode that.
![image](https://user-images.githubusercontent.com/68239030/200749191-9ccffeac-6a05-49cb-9341-7dad5491c992.png)

With the help of magic feature it recommends we convert it from Base64:

![image](https://user-images.githubusercontent.com/68239030/200749221-90148e65-0dc1-4444-bbbb-46880d9a2e8d.png)

We get maha_jodi as an unencrypted word. 
Adding it to the directory we get : https://haridai.sushilphuyal.com.np/Pratikxya/merotahasairamro/blue97/namaste/1957-2011/maha_jodi/

![image](https://user-images.githubusercontent.com/68239030/200749244-de70a985-b4da-42c1-bd85-0ce6824c1ad5.png)

When we click on the congratulation button we are shown a flag i.e flag{maha_sanchar_made_my_childhood_awesome} 
Indicating the CTF is over and we captured the flag

![image](https://user-images.githubusercontent.com/68239030/200749283-9d303460-971c-4ff8-8beb-6140f1a3067d.png)



Answer the questions below ( https://tryhackme.com/room/haribahadur )

![image](https://user-images.githubusercontent.com/68239030/200749695-e339a514-554d-499b-8572-f1ce9c480fbb.png)






