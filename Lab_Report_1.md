# Lab Report 1-Setting up Remote Access
Alex Andrade-A16488469  
CSE15L  
Spring 2022

---

## How to Install VS Code 
1. Navigate to the VS Code website at [this link](https://code.visualstudio.com/) and click the correct download button for your operating system
2. Once installed on your computer, open up the application and it should look like ![this](Screenshots/VS_Code_1.png)
3. Once you reach this page you have finished installing VS Code
---
## How to Connect Remotely 
1. Find your CSE15L account at [this link](https://sdacs.ucsd.edu/~icc/index.php) and mark it down for future reference
2. Open a terminal in VS Code and enter the command     
`$ ssh cs15lsp22anw@ieng6.ucsd.edu`                           
but with the "anw" replaced by the letters in your account
![example](Screenshots/Terminal_1.png)
3. A message will probably appear asking if you want to connect to this server as this will probably be your first time connecting to this server.
4. Say `yes` to this message but if it appears too often, your connection may not be private.
5. Enter your password and your screen should now look like ![this](Screenshots/Login_1.png)
6. Your computer (called the client) is now connected to a computer in the CSE building (called the server) and commands will be run on this computer
---
## Trying Commands
1. Try some commands like `cd`, `ls`, and `pwd` on both your computer and the server computer
2. You can also try other commands like:
* `mkdir`
* `cp`
* `cd ~`
* `ls -a`
* `ls -t`
* `ls -lat`
3. You should get different outputs when running the same command on the client versus the server like ![this](Screenshots/Command_1.png) or like ![this](Screenshots/Command_2.png)
---
## Moving Files with `scp`
