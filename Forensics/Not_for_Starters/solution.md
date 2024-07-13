### Not for Starters

<img src="https://github.com/user-attachments/assets/8c20699f-5e7b-470b-92fe-e7439308b713" alt="Not for Starters" width="500">

<br/>
In this challenge we are given two image files a png and a jpg. On downloading you fill find that the png file is corrupted whereas the jpg file is an almost plain green coloured image with some text beneath which is visible very slightly.
<br/><br/>
  <img src="https://github.com/user-attachments/assets/ac1ff4f8-6830-4358-b7dd-f998d9d3fc60" alt="Screenshot 2024-07-13 224550" width='400'>
  &nbsp; &nbsp;  &nbsp; &nbsp;
  <img src="https://github.com/user-attachments/assets/62603925-e965-4d05-8f27-ca8f966976a1" alt="Screenshot 2024-07-13 001847" width='455'>


Starting with the first file, we obviously open the hex editor to check if anything is messed with the hex code

<img src="https://github.com/user-attachments/assets/915628bd-8991-4de5-ba46-6ac24d32287a" alt="Screenshot 2024-07-13 002418" width="660">

As you can find the hex signature is indeed messed up. The correct file signature for a png file is `89 50 4E 47 0D 0A 1A 0A`, every png file starts with these bytes.

Further moving on to the other chunks in the png file, we find the IHDR chunk which comes right after the PNG signature is also incorrect, the correct sequnce for the chunk being `49 48 44 52`

On Correcting it we find the next chunk-IDAT is pretty fine and move on to the last chunk, the IEND chunck which sits at the bottom of the file.

We again find the hex code for this chunk to be messed up and replace it with the correct sequence `49 45 4E 44`


<img src="https://github.com/user-attachments/assets/792ccd6a-80bb-450a-9eca-b3689eaea0a7" alt="Screenshot 2024-07-13 003621" width="660">


Now on saving and downloading this corrected file, we find a blank blue coloured image with some very partially visible text hidden beneath, hinting at colour superimposition

<img src="https://github.com/user-attachments/assets/1a2a143c-1014-4318-a174-fdccf9cd49c3" alt="onee" width="500">

So we obviously try and superimpose colour on the image, first let us try uploading the image on [aperi solve](https://www.aperisolve.com/) to see if can find it directly.

On uploading and going through the results we do find half a flag in the superimposed view section `decipher{m3ta_}` and also we don't get anything of interest in the file metadata nor do we find any file embedded within the image file, which means the other half of the flag most likely lies in the second jpg file.

<img src="https://github.com/user-attachments/assets/a72633c8-e8dd-4313-b5eb-5d5dcf082a2a" alt="Screenshot 2024-07-13 004619" width="600">
<br/><br/>
So Lets Move on with the second file:

Lets check if it is also superimposed since it has something beneath the green background which is visible partially

<img src="https://github.com/user-attachments/assets/89cd7901-2619-463c-a200-e2f3be2592a7" alt="image" width="600">

So we obviously don't quite get the remaining half here, further checking the metadata we find a base64 encoded info in the decription tag of the image, on decoding we get something which seems like the second part of the flag

<img src="https://github.com/user-attachments/assets/37a298b7-4cf6-46bf-99e7-28402ec4601b" alt="image" width="460">
&nbsp; &nbsp; &nbsp;
<img src="https://github.com/user-attachments/assets/f8b8f068-f7c3-4955-8622-fbfd37f0826a" alt="image" width="380">

On entering the complete flag is when we realise it unfortunately doesn't turn about to be the right one.


Moving on further the steghide data in [aperi solve](https://www.aperisolve.com/) does show something is hidden/embedded in the file but has a passphrase, let's check if we can crack the passphrase

Instead of straightaway going with a passphrase cracking tool like stegcracker, lets check if we can find anything of help from the question itself The question is titled 'Not for Starters' so why not try entering the phrase 'starters' itself? 🤔

<img src="https://github.com/user-attachments/assets/91ba6f75-654c-4252-8b89-4e1a9d470697" alt="twotwo" width="500">

And there we get another second half of our flag!..lets join both the halves and check out if this flag is right now `decipher{m3ta_dat4_st3rt3r_p4ck}`

<img src="https://github.com/user-attachments/assets/7e723dc0-7d2e-4d9e-bec0-7af31f453a82" alt="image" width="500">
<br/>
And as anticipated this turns out be to be indeed the right Flag.
<br/>
Hope you had a great time reading this..
and as the description says this challenge was indeed Not for Starters :)
