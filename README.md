# Creating SSH Keys without Password for GitHub

When working with GitHub repositories, you may want to use SSH authentication instead of HTTPS authentication. This can be especially useful if you don't want to enter your username and password every time you interact with a repository.

In this guide, we'll go over the steps required to create SSH keys for use with GitHub, and configure your GitHub account to use these keys. We'll also show you how to create SSH keys without passwords, so that you can avoid having to enter a password each time you use a key.

## Prerequisites

Before you begin, you'll need:

- A GitHub account
- Git installed on your local machine

## Step 1: Generating an SSH Key

To generate an SSH key, you can use the `ssh-keygen` command in a terminal window. To create an ssh key without a password, simply press enter when prompted for a passphrase:

## code
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/you/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase):
Enter same passphrase again:

By pressing enter twice, you are creating an SSH key pair without a password attached to it.

This creates a new RSA key pair with a length of 4096 bits, using the specified email address as a label.

## Step 2: Adding Your Public Key to GitHub

Now that you have generated an SSH key pair, you need to add the public key to your GitHub account. To do this, follow these steps:

1. Log in to your GitHub account.
2. Click on your user icon in the upper right-hand corner of the screen, and select **Settings** from the drop-down menu.
3. In the settings sidebar, click on **SSH and GPG keys**.
4. Click on **New SSH key**.
5. Enter a title for your key in the **Title** field. This can be anything you like.
6. Open the `public_key.txt` file that you created earlier.
7. Copy the entire contents of the file to your clipboard.
8. Paste the contents of the public key file into the **Key** field on GitHub.
9. Click **Add SSH key**.

This will add your public key to your GitHub account, and allow you to authenticate with GitHub using the corresponding private key.

## Step 3: Using Your SSH Key

Now that you have added your public key to your GitHub account, you can use your private key to authenticate with GitHub.

To do this, simply clone an existing repository or create a new one:

### code

$ git clone git@github.com:yourusername/your-repo.git
Cloning into 'your-repo'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
```

When you clone a repository via SSH, Git automatically uses your private key to authenticate with GitHub. You should not be prompted for a username or password.

Congratulations! You've successfully created an SSH key without a password, added it to your GitHub account, and used it to authenticate with GitHub.