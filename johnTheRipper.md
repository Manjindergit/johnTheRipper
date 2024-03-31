# Lab Guide: Password Cracking with John the Ripper

## 1. Introduction
In this lab, we will explore the world of password cracking using John the Ripper. We will learn about hashing, decrypting zip files, and much more.

### Objectives of the Lab
- Understand the basics of password cracking and hashing.
- Learn how to use John the Ripper for various tasks.

## 2. Background

In the realm of cybersecurity, password cracking and hashing are two fundamental concepts. Password cracking is the process of guessing or recovering a password from stored locations or from data transmission systems. It is used to gain unauthorized access to systems. Hashing, on the other hand, is a method of cryptography that converts any form of data into a unique strings. Any slight change in this data will change the hash string.

John the Ripper is a popular password cracking tool widely used by cybersecurity professionals. It is designed to be both feature-rich and fast. This lab will provide hands-on experience with John the Ripper, demonstrating its capabilities and usage in various scenarios. The knowledge gained will be valuable for understanding the strengths and weaknesses of different password policies, and how to strengthen system security.

## 3. Pre-Lab Knowledge Check
Before we begin, let's ensure we understand the following concepts:
1. **Password Cracking**: It's the process of recovering passwords from data stored in or transmitted by a computer system.
2. **Hashing**: It's the process of converting data into a fixed-length string of letters and numbers.
3. **Types of Hashes**: These are different algorithms used to create hash values, common ones include MD5, SHA-2 and CRC32.
4. **Salts**: These are random data that's used as an additional input to a one-way function that hashes data, a password or passphrase.

## 4. Safety and Ethics 

Remember, with great power comes great responsibility. This lab is for educational purposes only. Always respect privacy and consent when using these skills. It's crucial to understand that misuse of these skills can lead to serious consequences. Therefore, let's ensure we use our knowledge ethically and responsibly, promoting a safer digital world.


## 5. Submission Requirements
Please submit the following upon completion of the lab:
- Screenshots of your work
- This completed .md file
- Any configuration files used or modified
- Use the `diff` command to show any changes made to configuration files

## 6. Procedure

### 6.1 Installation and Minimum Requirements
This section provides detailed steps for installing John the Ripper and a list of minimum system requirements.

1. Download Kali Linux. 

    (https://cdimage.kali.org/kali-2024.1/kali-linux-2024.1-installer-amd64.iso)


2. Setup a Virtual Machine  
Recommended settings:  
1 CPU, 4 GB RAM, 20GB HDD

### 6.2 Decrypting a Zip File
Follow this step-by-step guide on how to use John the Ripper to decrypt a zip file.

As a digital forensic investigator for the RCMP, you have been tasked with gathering evidence for a criminal conspiracy case on a suspect's computer. You came across the zipped folder "Plans", and found it was password protected.


1. Copy the zip file to a format that John can crack.


2. Use John to crack your new file. This may take some time.


3. Extract the zip file. Take a screenshot of the file's contents.


    Hint: Make a zipped folder with the password "!@#$%^&". Include a txt or docx detailing a bank robbery plan or something

### 6.3 Decrypting Hashes in a Text File
This section provides instructions on how to decrypt hashes stored in a text file.

1. Crack the passwords from the .txt file with the command that finds the most passwords and that keeps the hashing algorithm in mind. List the command.  
(Hint: There should be at least four passwords cracked in one command)

2. Save the passwords taken from John's records in a file named "CrackedPasswords.txt" and add it to your submission.

### 6.4 Viewing Cracked Passwords
Learn how to view all cracked passwords in $JOHN/john.pot.

Use the command `./john hashes --pot=<> --show` to display all cracked passwords.

### 6.5 Decrypting a Numerical Only Password
This section provides steps to decrypt a numerical only password.

1. Create a hash of only numerical password.
2. Edit config file appropriately and run John.

Take a note of time John took to crack a numerical only password in comparison to a mix password of alphanumerical characters. 

### 6.6 Cracking an Old Password

Say you have an old password that you don't quite remember properly. You remember how it starts but don't remember what numbers are at the end, or what form of mangling is done to a certain phrase. Demonstrate John the Ripper's ability to crack your old password by creating a wordlist with variations of your phrase.

1. Create a john-local.conf file and define rules (e.x [0-9] to add a number from 0-9 at the end of your phrase) that John the Ripper will use to mangle your key phrase
2. Create a basic word list that includes the part of the password that you remember.
3. Generate a custom word list using John the Ripper using your wordlist and the rules you defined
4. Run John the Ripper with your custom word list, don't forget to enable mangling rules

### 6.7 Time Tracking
In this lab task, you will crack the same file using different modes and report back how long each attempt took.

You have been asked by your employer to test the various modes of John the Rippers and record how long it takes for each mode to crack the password. Test all the modes listed below, visualize your results in a chart and explain what scenario each mode will be best suited for.

#### Wordlist Mode

In the wordlist mode, John the Ripper compares the hash to a list of potential passwords. This mode relies entirely on the wordlist, checking if each possibility is a match without generating variations or a variety of combinations.

- Find a wordlist online or create your own for John the Ripper to use.
- Use John the Ripper to crack your file using your wordlist, specifying the location of the wordlist.

#### Mangling Rules Mode

The mangling mode is used to make the usage of the wordlist faster. It modifies the words in the wordlists, combining them with other likely passwords to create more possible combinations.

- Use your wordlist with the mangling mode enabled and record your results.

#### Incremental Mode

This mode is considered the “brute-force” method, trying every single possible combination of passwords and characters. Record the time taken for the attempt to complete.

#### External Mode

This mode allows you to use external modes. Create a configuration file containing functions programmed in C. Find functions made by other users and test them.

### 6.8 Speed up John the Ripper

The default setting for the "idle" mode in John the Ripper's configuration file is set to Y. This means that John the Ripper only uses idle processor cycles, which reduces its load on the processor for the purpose of not taking up too many resources. Change this setting to N and investigate the impact on the time it takes for John to crack a password.

## 7. Troubleshooting Guide

This section provides solutions for common errors or issues you may encounter.

|Error|Issue|Solution|
|--|--|--|
|No Hashes loaded|Empty or improperly formatted hash file| Verify the hash file contains valid hash values. Verify the integrity of the file|

## Reflection Questions

1. What did you learn from this lab about password cracking?

2. What are some real world applications for John the Ripper?

3. What challenges did you face while using John the Ripper and how did you overcome them?

4. What kind of passwords were the easiest for John the Ripper to guess?

5. What are the ethical considerations when using a tool like John the Ripper?

## Rubric for Evaluation
| Criteria | Excellent | Good | Satisfactory | Needs Improvement | Unsatisfactory |
|----------|-----------|------|--------------|-------------------|----------------|
| Understanding of Password Cracking | Demonstrates excellent understanding | Demonstrates good understanding | Demonstrates satisfactory understanding | Demonstrates a need for improvement in understanding | Demonstrates unsatisfactory understanding |
| Use of John the Ripper | Excellent use of tool | Good use of tool | Satisfactory use of tool | Use of tool needs improvement | Unsatisfactory use of tool |
| Lab Report Completion | All sections of the lab report are excellently completed | Most sections of the lab report are well completed | Lab report is satisfactorily completed | Lab report completion needs improvement | Lab report is unsatisfactorily completed |
| Reflection | Provides excellent reflection on the lab experience | Provides good reflection on the lab experience | Provides satisfactory reflection on the lab experience | Reflection on the lab experience needs improvement | Provides unsatisfactory reflection on the lab experience |
| Ethical Considerations | Demonstrates excellent understanding of ethical considerations | Demonstrates good understanding of ethical considerations | Demonstrates satisfactory understanding of ethical considerations | Understanding of ethical considerations needs improvement | Demonstrates unsatisfactory understanding of ethical considerations |