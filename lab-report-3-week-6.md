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

* Now, testing it, I copied `markdown-parser` to `ieng6` by using command `scp -r ./markdown-parser ieng6:~/markdown-parser`

<img width="660" height="845" alt="CleanShot 2022-05-08 at 15 51 11@2x" src="https://user-images.githubusercontent.com/66764591/167319292-2f2bc547-dfa4-4edd-b3fc-128062f761ea.png">

* To test if the file transferred, I logged in to ieng6 by using command `ssh ieng6` and `cd markdown-parser` and `ls`

<img width="660" height="454" alt="CleanShot 2022-05-08 at 15 53 25@2x" src="https://user-images.githubusercontent.com/66764591/167319334-85380313-3712-4244-8868-915a19c6f98f.png">

### **Setup Github Access from ieng6**



### **Copy Whole Directories with `scp -r`**
