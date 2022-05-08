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

<img alt="CleanShot 2022-05-08 at 15 08 57@2x" src="https://user-images.githubusercontent.com/66764591/167317968-64f856c8-f09b-4f13-8351-4e5d3d3c4b09.png" width = “660” height = “252”>

* Type the following code in "config" file.

```
Host ieng6
    Hostname ieng6.ucsd.edu
    User cs15lsp22aau 
```

* Now when I type `ssh ieng6`, it will log in faster and easier

<img alt="CleanShot 2022-05-08 at 15 13 18@2x" src="https://user-images.githubusercontent.com/66764591/167317976-cdc31849-f1b2-4db8-a5bc-664906637604.png" width = “660” height = “628”>


### **Setup Github Access from ieng6**

### **Copy Whole Directories with `scp -r`**
