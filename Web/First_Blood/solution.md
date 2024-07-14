### First Blood

<img src="https://github.com/user-attachments/assets/b41bcaa7-83b3-4728-8d8f-9dc3965fe21e" width="500">

As we open the link provided in the description we get this web page

<img src="https://github.com/user-attachments/assets/dfe48072-dbf7-4f90-8307-fb5834e33525" width="900">

As the info in the page says 'have some fun and bots' it's pretty clear where we must be heading to. Let's access the robots.txt file of the page

<img src="https://github.com/user-attachments/assets/0068cdeb-44f3-4c32-9e3a-dfef6c8585a4" width="900">

And there you go, we get a flag which might just not turn out to be the actual one since we got some more interesting info in the file. But for a start, let's try that flag out

<img src="https://github.com/user-attachments/assets/b64042b4-8056-47c1-9dca-23f9687ef5a9" width="400">

As expected, this doesn't turn out to be the one. Let's check the endpoints mentioned in the file now, starting with '/robots'.

Here we do get another flag but this might as well not be the actual one, the description following the flag also hints the same.

<img src="https://github.com/user-attachments/assets/90304bc8-874e-4b3b-9bb0-78d41fac88c2" width="440" height="410">
&nbsp; &nbsp;
<img src="https://github.com/user-attachments/assets/775d111a-b5f6-491b-8f31-f6aed74d03de" width="410">

Let's go to the second endpoint '/botsbots' now. We get another flag here, which again does not turn out to be the actual one.

But it has some interesting info following though, says to keep an eye out for 'd and p'. Now what might they mean, probably html tags you reckon? Let's just check out the source file.

<img src="https://github.com/user-attachments/assets/d2b04fa7-dc69-457b-8e41-62d5372c2733" width="900">

Unfortunately, we don't get anything quite interesting here in the page source. 

Let's just move on to our last endpoint '/bots'.

<img src="https://github.com/user-attachments/assets/a1f7659a-6989-4818-943d-3f1f88e4eaad" width="900">

And we do get this webpage here which doesn't quite reveal the flag but has something interesting.

It says 'hi and hello' are different. Now, what would that mean you reckon? Let's just check the page source.

<img src="https://github.com/user-attachments/assets/5b39691f-7912-45e3-a0f2-669813e6fb63" width="900">

And there you go, we might have something we are just looking out for. As the hint said 'hi and hello are different', we can probably find the parts of the flag in the tags with the classname 'hello' and only in the 'p' tags which connects it to the previous hint as well.

Adding up the parts, it leads us to our actual flag `decipher{fin4lly_0ne_f0und}`

<img src="https://github.com/user-attachments/assets/389949ce-9ec1-448e-9091-6bdb97e64fd2" width="500">
