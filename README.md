<img src="https://tryhackme-images.s3.amazonaws.com/room-icons/fafc074a97207f99929f2ee28bea87ac.jpeg" alt="Logo" width="100" height="auto">

## Crack The Hash 

###### Can you complete the level 1 tasks by cracking the hashes?

###### This repository is dedicated to show how i go through Hacking challenges.

###### Created only for learning pourposes and all the solutions and tricks are used at controlled environments.

### Happy Hacking Phreaks 😃


Can you complete the level 1 tasks by cracking the hashes?


  # Hash 01 ⬇️
  
  ````
  48bb6e862e54f2a795ffc4e541caed4d
  ```` 
  - You need to find out what of hash you're dealing with to know what method you'll gonna use to crack it.
  - So for this first hash i'll be using "Hash Identifier"
  - You can check out more information about this tool here 🔜  [Hash Identifier](https://www.kali.org/tools/hash-identifier/)
    
    <img src="screenshots/01/01.png" alt="Logo" width="700" height="auto">
  
  - You can type this in your terminal:
  
    ````
    hash-identifier
    ````
  - Now you paste your hash and the output should be somethin like this:
    
    <img src="screenshots/01/02.png" alt="Logo" width="700" height="auto">
  
  - So now you know what type of password you're cracking!!!!
  - Now let's jump into "Jhon The Reaper" tool which is my choice this time
  - If don't know this tool yet you can take a look at the docs clicking here 🔜  [John The Reaper](https://www.openwall.com/john/)
  - First you send your hash to a file just like this:
   
    ````
    echo "48bb6e862e54f2a795ffc4e541caed4d" > hash_01.txt           
    ````
  - The command for john is the following:
   
    ````
    john --format=raw-md5 --wordlist=~/Downloads/rockyou.txt hash_01.txt
    ````
  - Now you should see some output like this one:

    <img src="screenshots/01/03.png" alt="Logo" width="700" height="auto">
  
  - Second command to see the hash this time is:
       
    ````
    john --show --format=raw-md5 hash_01.txt     
    ````
  
  - And there is the cracked password:

    <img src="screenshots/01/04.png" alt="Logo" width="700" height="auto">
  
  - Our job is done for this one:

    <img src="screenshots/01/05.png" alt="Logo" width="700" height="auto">
  

 # Hash 02 ⬇️
  
  ````
  CBFDAC6008F9CAB4083784CBD1874F76618D2A97
  ```` 
  - Let's do the same with this one:

    <img src="screenshots/02/01.png" alt="Logo" width="700" height="auto">
  
  - Send the hash to a ".txt" file:
  
    <img src="screenshots/02/02.png" alt="Logo" width="700" height="auto">

  
  - Crack the hash using Jhon:
  
    <img src="screenshots/02/03.png" alt="Logo" width="700" height="auto">

  
  - There it is:
  
    <img src="screenshots/02/04.png" alt="Logo" width="700" height="auto">

 # Hash 03 ⬇️
  
  ````
  1C8BFE8F801D79745C4631D09FFF36C82AA37FC4CCE4FC946683D7B336B63032
  ```` 
- Let's do the same with this one:

    <img src="screenshots/03/01.png" alt="Logo" width="700" height="auto">
  
- Send the hash to a ".txt" file:

  <img src="screenshots/03/02.png" alt="Logo" width="700" height="auto">


- Crack the hash using Jhon:

  <img src="screenshots/03/03.png" alt="Logo" width="700" height="auto">


- There it is:

  <img src="screenshots/03/04.png" alt="Logo" width="700" height="auto">

  
- Our job is done for this one too:

  <img src="screenshots/03/05.png" alt="Logo" width="700" height="auto">

# Hash 04 ⬇️
  
  ````
  $2y$12$Dwt1BZj6pcyc3Dy1FWZ5ieeUznr71EeNkJkUlypTsgbX1H68wsRom
  ```` 
- If you try to run this against the hash-identifier you'll not get the type of hash
- So you can go to the [HashCat Website](https://hashcat.net/wiki/doku.php?id=example_hashes)
- There's a list of hash types so you can a take a look and find out more information about 
  
  <img src="screenshots/04/01.png" alt="Logo" width="700" height="auto">

- Bcrypt hashes are hard to crack because it takes patience by the attacker
- So, in this case you'll be using "hashcat" for cracking
- As may noticed, the image above has a number (3200)
- Each hash hash its "code mode" so for bcrypt hashes we'll use "3200"
  
  ````
  hashcat -m 3200 <your_hash.txt> path/to/your/wordlists/rockyou.txt --force -O
  ````   
- --force: Forces hashcat to continue despite encountering an error or warning. It's used to ensure that the cracking process continues even if there are issues.
- -O: Enables optimized kernels for the cracking process, which can improve performance.
  
  <img src="screenshots/04/02.png" alt="Logo" width="700" height="auto">

  ##### Now you may go and take some coffee because its taking a very long time depending on your machine setup ☕