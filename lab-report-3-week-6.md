# Lab Report 3
---
## CSE 15L - Spring 2022
---

### **Contents**

1. [Streamlining ssh Configuration](#streamlining-ssh-configuration)
2. [Setup Github Access from ieng6](#setup-github-access-from-ieng6)
3. [Copy Whole Directories with `scp -r`](#copy-whole-directories-with-scp-r)


### **Streamlining `ssh` Configuration**

* First, find the `.ssh` folder. The command for finding it is `Command - shift - g`
* Open the `.ssh` folder with VS Code.

<img width="660" height="252" alt="CleanShot 2022-05-08 at 15 08 57@2x" src="https://user-images.githubusercontent.com/66764591/167318352-472640cf-9abd-4c9f-b699-973883bda62e.png">

* Type the following code in "config" file.

```
Host ieng6
    Hostname ieng6.ucsd.edu
    User cs15lsp22aau 
```

* Now when I type `ssh ieng6`, it will log in faster and easier

<img width="660" height="628" alt="CleanShot 2022-05-08 at 15 13 18@2x" src="https://user-images.githubusercontent.com/66764591/167318420-e99c9077-29f0-4427-9dac-3637658035b1.png">

* I've created a new txt file using alias and sing command `scp Hello.txt ieng6:~`
* As can be seen from using `ls` commmand, there's a new txt file. 

<img width="660" height="454" alt="CleanShot 2022-05-08 at 17 50 30@2x" src="https://user-images.githubusercontent.com/66764591/167323376-eddab866-8707-4784-a6af-4b9230d96871.png">

### **Setup Github Access from ieng6**

* I created an `ssh` key by using `ssh-keygen -t ed25519 -C "1kaungminkhant1@gmail.com"`
* Then, co to `.ssh` file by using `ssh-add -K~/.ssh/id_ed25519`
* Then, copy the key by using `pbcopy < ~/.ssh/id_ed25519.pub`
* Then, add ssh key to github by pasting the key copied above. 

<img width="660" height="859" alt="CleanShot 2022-05-08 at 16 20 40@2x" src="https://user-images.githubusercontent.com/66764591/167320071-b37da3de-f1e1-4f24-9fd6-208382fab5cc.png">

* Now, you can see `ssh` key added in your github.

<img width="660" height="590" alt="CleanShot 2022-05-08 at 16 26 30@2x" src="https://user-images.githubusercontent.com/66764591/167320134-62769224-a802-4cf3-b183-0c8261b0818f.png">

* Click [here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) for detailed process of generating a new `ssh` key
* CLick [here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account) for detailed process of adding a `ssh` key to github.

* The `ssh` key is stored in my `ieng6` account in `.ssh` 

<img width="660" height = "454" alt="CleanShot 2022-05-08 at 16 30 38@2x" src="https://user-images.githubusercontent.com/66764591/167320811-d58d9bd8-ef97-4c0d-8e5a-808caa9e3959.png">


* After making a change to MArkdownParse.java, 
* Follow these commands to commit: `git add`, `git commit -m "adding a line"`.
* Enter `git push origin main`

<img width="660" height = "464" alt="CleanShot 2022-05-16 at 11 45 55@2x" src="https://user-images.githubusercontent.com/66764591/168661284-53e7d2f3-24ec-421c-afdc-24f799019383.png">


* [Here](https://github.com/kaung-min-khant/skillDemonstration1/commit/a921d32f63f263c04bc956124580d9b14be55dad) is the commit on github website.


### **Copy Whole Directories with `scp -r`**

* Use command `scp -r ./markdown-parser ieng6:~/markdown-parser` to copy the whole directory.

<img width="660" height="845" alt="CleanShot 2022-05-08 at 15 51 11@2x" src="https://user-images.githubusercontent.com/66764591/167319292-2f2bc547-dfa4-4edd-b3fc-128062f761ea.png">

* To test if the directory transferred successfully, I logged in to ieng6 by using command `ssh ieng6` and `cd markdown-parser` and `ls`

<img width="660" height="454" alt="CleanShot 2022-05-08 at 15 53 25@2x" src="https://user-images.githubusercontent.com/66764591/167319334-85380313-3712-4244-8868-915a19c6f98f.png">


* Now, we can run the test directly in `ieng6`

<img width="660" height="498" alt="CleanShot 2022-05-08 at 17 04 22@2x" src="https://user-images.githubusercontent.com/66764591/167321389-c5b52cb8-e9f9-4e5f-88c1-263112eb095b.png">

* You can also copy the whole directory and run the tests by combining the commands in one line. `scp -r *.java *.md lib/ ieng6:markdown-parse; ssh ieng6"cd markdown-parser; javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java; java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest"`

<img width="660" height="289" alt="CleanShot 2022-05-08 at 15 08 57@2x" src="https://user-images.githubusercontent.com/66764591/167322746-f19a59ae-3fe0-41cf-93f8-9ed1b1c61129.png">

