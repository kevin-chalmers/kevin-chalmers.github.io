# Encrypting Folders on Cloud Storage

One of my first tasks when setting up a computer - a job I do several times a year - is accessing my encrypted folders in cloud storage.  My folder contains secure items I require to set up my machine.  I've recently moved my storage to pCloud as Dropbox's free account has become more restrictive, but the technique I present here will work on any cloud share that appears as folder on your computer.

This post will explain how to create an encrypted folder.  I will introduce cloud storage and encryption, and then describe the tool I use: EncFSMP.  I will then step through how you can create an encrypted folder in the cloud.  Finally, I will list the tools you can use to access your encrypted folder on other devices, before finally commenting on limitations.

## Cloud Storage

Cloud storage has become a utility we now take for granted.  Without Dropbox, Microsoft's OneDrive, Google Drive, or similar, we would still send files via email, share USB keys, or possibly send smoke signals to communicate data.

Today, companies offer terabytes of storage online, accessible across devices.  Sharing files is easy: they are on all the devices that have permission to access the shared folder.

There is a limitation, however.  Everything you store in the cloud is visible to the hosting company.  Worse, it may be visible to the broader Internet.  And if someone gained access to your account, they can access your private files.  Therefore, we need some method of protecting our files.  Therefore, we need encryption.

## Encryption

Encryption is the act of converting data into an obscured form of data that has been encoded using an algorithm.  In computing, we generally use key-based techniques - a method to encode and decode data using reproducible outcomes.  There are two key-based approaches:

- Single-key encryption.
- Two-key encryption.

EncFSMP uses single-key encryption.  I will post in future about how to use two-key encryption to encrypt a folder.

### Single-key Encryption

Single-key encryption, known as symmetric cryptography, relies on a single-key known to everyone.  The key allows encryption of plaintext and decryption of ciphertext.  Effectively, we have a password that allows the encryption and decryption of data.  This password is a shared secret - something that both the encryptor and decryptor must know to work together.

### EncFSMP

EncFS stands for **Enc**rypted **F**ile **S**ystem.  That is, we are able to encrypt part of the our file system (e.g., a folder) and "mount" the folder to access the encrypted data.  I use mount in the most liberal terms here.

EncFS uses single-key encryption.  You will choose a password that will be used to encrypt the data in your folder.  As with any password, the more complex your password the better to protect your data, but the harder to remember.

## Steps

Let us step through how to encrypt a folder in your cloud storage.

### Step 1 - Install EncFSMP

*If you are using Windows*, you can find the install [here](https://encfsmp.sourceforge.io/).  If you are using Linux or a Mac, the process is simpler - see the links in the tools section below.

### Step 2 - Create a Folder in Cloud Storage

Create a folder as you would normally in your cloud storage.  **WARNING** - do not directly store anything in this folder.  It will be filled with encrypted data.

### Step 3 - Create an Encrypted Volume via EncFSMP

Open EncFSMP.  You should see the following window:
