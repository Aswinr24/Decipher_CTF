### Be Relentless
<img src="https://github.com/user-attachments/assets/aa8da956-62af-40b2-b8e2-8b09258fd66d" width="400">

Lets open the link, We get a Web Page with a Login button <br/>
Lets just enter a random username, click login and try if we can get our flag or anything nearby

<img src="https://github.com/user-attachments/assets/f311d84f-2391-4dd5-8b54-89249387a616" width="900">

And as you would have anticipated, it didn't reveal much of anything

As we scroll down we get a button there and the description says shortcuts don't work <br/>
Lets click the button and check out.

<img src="https://github.com/user-attachments/assets/ecd4c591-14b7-4fbf-bdc1-9eb351c66f15" width="900">

Well it gives us some base 64 encoded code, lets try and decrypt this

<img src="https://github.com/user-attachments/assets/f32ad5d4-a44e-43bd-921a-c40fba0c1afe" width="500">

And as expected it leads us to nothing, dont try to decrypt the morse code btw it ain't giving you anything ( so shortcuts don't work indeed :( )

Lets read the question description once again..it says something related to hunger, appetite what would that mean you reckon..? cookies maybe?

For now lets just check out the robots.txt file if we can get anything there

<img src="https://github.com/user-attachments/assets/aac6d9fc-0b35-4050-968b-5ba7d94201ea" width="900">

It does give us an endpoint, let us advance there

<img src="https://github.com/user-attachments/assets/c3181cfb-85d8-4d02-92f2-00a894fae4f7" width="900">

We get a flag that definitely ain't the right one since this ain't a 50 pt question <br/>
But lets check out the page source 

<img src="https://github.com/user-attachments/assets/bd881ae6-373b-49ee-85d4-e064be01cda9" width="900">

It again has a hidden flag in the tags which again isn't the one, but it does give us some interesting info..<br/>
the words in the last div tags confirm where we should be heading to, yep lets check the cookies

<img src="https://github.com/user-attachments/assets/3b0ddac1-53ed-412e-ab80-2d8c0d93f0b7" width="900">

And there you go, two cookies are generated as soon as we login with the user name and user type is set to 'user' by default seems like
<br/>
Now the obvious classic move would be to change the user type to a higher privilege, lets change it to admin and look out what we can get 

<img src="https://github.com/user-attachments/assets/0f4f90e6-ae34-45ab-9c87-23de2f2c710c" width="900">

And there we get the flag (which is fishy..says something doesn't it?)
<br/>
lets try it out first though

<img src="https://github.com/user-attachments/assets/e6583153-0825-4231-afea-572a547e8228" width="400">

And as probably expected isn't the right one but we are very close to our flag we must believe
<br/>
Lets do a directory/endpoint enumeration using gobuster to check if anymore endpoints exist

<img src="https://github.com/user-attachments/assets/709c990a-f0e2-4956-9e62-17a1ffd578d6" width="700">

And we do get two new endpoints
<br/>
lets advance to '/admin' first

<img src="https://github.com/user-attachments/assets/af3dd286-324a-4376-815a-e6e3ff372609" width="900">

We don't get the flag in the web page, but it says something interesting, 'climb a step higher'

What do you think a step higher than admin is ? <br/>
The page source definitely has a flag which obviously isn't the right one but has a different purpose to serve maybe..

the flag ``decipher{high3r_privil4ges_are_SUPERb}`` captilizes and highlights the word 'super'
does it hint to use the word in our cookie? <br/>

The description, 'a step higher than admin' and the flag 'higher previlages are SUPERb' <br/>
does it mean to set the userType to superuser or superadmin? 

Lets try them out

<img src="https://github.com/user-attachments/assets/581456ad-b2ab-4e36-b17a-2ced27e880bc" width="900">

we don't get anything with 'superuser'
<br/>
lets try 'superadmin' then!

<img src="https://github.com/user-attachments/assets/d6b6c817-6158-47d3-9200-958a1fb9d568" width="900">

And there you go, we get a flag ``decipher{c3VwZXIgKDI3IG1vcmUgdG8gZ28pOiAgPkRlZk46ITY5eSgxYClLVUYldEVobFdDJDJidDY2akw-NDx2bWxJbztJeD1TQ35SMiJudmRMQjI8diVrQQ}``, probably base 64 encoded

Lets try and decode this in cyber chef

<img src="https://github.com/user-attachments/assets/5043c400-72a3-4ec0-beb5-9ada40c2e562" width="700">

It says 'super' and '27 more to go' and gives us another code

27 more, does it mean base91?
<br/>
Lets check out

<img src="https://github.com/user-attachments/assets/7e011f32-e4c2-456f-a5e8-bcb5c75d4ec6" width="700">

There it gives us another word '_admin' and a bunch of hex codes, These first words are parts of the flag you reckon?
<br/>
Decode the hex codes first

<img src="https://github.com/user-attachments/assets/dcaa7915-c748-4cfb-97a7-df1b7b544d8f" width="700">

And there we have our last word '_is_underr4t3d'

Remember each first word we get after decoding each encrypted code, lets add them up and we get 'super_admin_is_underr4t3d'
<br/>
replacing the initial base64 code with this we get our flag ``decipher{super_admin_is_underr4t3d}`` <br/>
Which turns out to be indeed the actual flag.

<img src="https://github.com/user-attachments/assets/0939d15a-c4f5-4961-a376-f653d93f08b3" width="400">


Hope you had great fun reading this..and as the challenge said, you had to 'Be Relentless' to solve this
