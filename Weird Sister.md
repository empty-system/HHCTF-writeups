## Challenge informations

- Name: Weird sister
- Flag: HHCTF{d3v1lbru73f0rc3216}
- Difficulty: Medium
- Creators: Romain, Tim, Quentin

## Description

Your friend's sister has a zip with a password on her desk, so your friend got it and asked you to find her password knowing you have computer skills. The only thing you have is her Instagram: [https://www.instagram.com/safiyyahh.216/](https://www.instagram.com/safiyyahh.216/ "‌")
He also knows that she spreads her life a bit too much on the networks, maybe there are some clues?

- No need to bruteforce the instagram account
- No need to reverse the images
- No need to contact followers and subscribers of the account
- DON'T WRITE BELOW PICTURES!

# For admin/mod

Tools:
cupp -> wordlist ([https://github.com/Mebus/cupp](https://github.com/Mebus/cupp "‌"))
[https://fr.wikipedia.org/wiki/Leet_speak](https://fr.wikipedia.org/wiki/Leet_speak "‌")
john -> bruteforce ([https://github.com/openwall/john](https://github.com/openwall/john "‌"))
[https://linuxconfig.org/how-to-crack-zip-password-on-kali-linux](https://linuxconfig.org/how-to-crack-zip-password-on-kali-linux "‌")
bruteforce-salted-openssl ([https://github.com/glv2/bruteforce-salted-openssl](https://github.com/glv2/bruteforce-salted-openssl "‌"))

## Writeup

./cupp.py -i
..creating the wordlist (enable leetmode!) 

**First pass: H4j4r1999**
- zip2john DontTouchUntilIDie.zip > hash.txt
- john --wordlist=/path/to/the/wordlist hash.txt

**Second pass: Sh4y74n1022**
- bruteforce-salted-openssl -f /path/to/the/wordlist -d sha256 -c aes128 testament.openssl
- openssl enc -aes128 -salt -in decrypt -out blc.txt -d -k 'Sh4y74n1022'
