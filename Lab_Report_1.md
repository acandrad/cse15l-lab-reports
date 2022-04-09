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
1. Try some commands like `cd`, `ls`, and `pwd` on both your computer and the remote computer
2. You can also try other commands like:
* `mkdir`
* `cp`
* `cd ~`
* `ls -a`
* `ls -t`
* `ls -lat`
3. You should get different outputs when running the same command on your computer versus the remote computer like ![this](Screenshots/Command_1.png) or like ![this](Screenshots/Command_2.png)

---

## Moving Files with `scp`
1. Create a file on your computer called `WhereAmI.java` and put the following code in it 
```
class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```
2. Run `WhereAmI.java` using `javac` and `java` on your computer and note down the output
3. In the terminal from the directory where the file is located on your computer run the command         
`scp WhereAmI.java cs15lsp22anw@ieng6.ucsd.edu:~/`      
with the "anw" replaced by the letters in your account
4. You should next enter your password to your account when asked
5. Log into the ieng6 server using the `ssh` command and use the `ls` command
6. `WhereAmI.java` should now be in the home directory and can be run on the ieng6 computer using `javac` and `java`
7. The output should be different on the ieng6 computer compared to your computer and should look something like ![this](Screenshots/WhereAmI_Output.png)

---

## Setting a SSH Key
1. 