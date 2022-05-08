# Lab Report 3-Improving Remote Operations
Alex Andrade-A16488469  
CSE15L  
Spring 2022

---

## Streamlining ssh Configuration
1. In order to streamline ssh Configuration, you first need to make a `config` file in the `.ssh` directory like ![this](Screenshots/ConfigPic.png) which you can do through VScode like ![this](Screenshots/ConfigEdit.png)
2. You can then move this `config` file into the `.ssh` directory from VScode and once you do that you should be able remotely log in from your computer using the alias you picked like ![this](Screenshots/SSHLog.png)
3. Now that it is easier to log in to the remote server, it becomes easier to `scp` files as you don't need to type out the whole username and address and instead only need a simple command like ![this](Screenshots/SCPCopy.png) and you can see the results in the remote server ![here](Screenshots/SCPSuccess.png)

---

## Setup Github Access from ieng6
1. You will need to create a public and private key pair on your remote account using `ssh-keygen` like ![here](Screenshots/RemoteKeys.png) as you can see both the public and private key are now on the remote server.
2. Next, you need to add your public key to Github and you can follow [this link](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account) to find out how to add SSH keys to your Github account and your public key should look like ![this](Screenshots/PubKeyGithub.png)
3. Then, you will have to run ```eval `ssh-agent -s` ``` and `ssh add` with the name of your private key like ![this](Screenshots/SSHAgent.png) 
in order to remotely access Github.
4. Now that both Github and the remote account have the public keys, you can commit and push changes to Github from your remote account like ![this](Screenshots/RemoteGit.png) and these changes will now show up on your Github account under commits like [here](https://github.com/acandrad/SkillDemo/commit/65b1f94f9ca679aa8bdbd54f4a6c399816ed0752)

---

## Copy whole directories with `scp -r`
1. You can copy whole directories from your local computer to the remote server using `scp -r` in the directory you want to copy and while `scp -r . ieng6:markdown-parser` copies the whole directory, `scp -r *.java *.md lib/ ieng6:markdown-parser` would only copy the `.java`, `.md`, and `lib/` files as shown ![here](Screenshots/CopyDirect.png)
* (1a) When using `scp -r . ieng6:markdown-parser` the whole folder is copied over so it doesn't matter if the `markdown-parser` directory you are copying to exists or not as it will be created but when using `scp -r *.java *.md lib/ ieng6:markdown-parser` the `markdown-parser` directory has to already exist within the remote server
2. Once the whole directory is copied, you can now compile and run the tests in the remote server like ![this](Screenshots/RemoteTest.png)
3. You can also optimize this whole process to run in one line like ![here](Screenshots/OneLine.png) where the directory is copied over, the remote server is accessed, and the tests are run.
* (3a) When running the whole process from one line, the server uses an older version of java so the `javac` and `java` commands are not running on the correct version of java so instead replace them with `/software/CSE/oracle-java-17/jdk-17.0.1/bin/javac` and `/software/CSE/oracle-java-17/jdk-17.0.1/bin/java` respectively before your commands to fix this error

---

The source for this report and some of the code used was the lab 5 writeup at [this link](https://docs.google.com/document/d/1NQ17hecUPFKeoFyrEvK9DBlCS1JkDbMW6Ygrf_CJJJU/edit)
and the source for the new `javac` and `java` commands was at [this link](https://piazza.com/class/l0lgl3r7ph370k?cid=444)