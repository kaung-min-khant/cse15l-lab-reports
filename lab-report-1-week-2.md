<style>
H1{color:Black !important;}
H2{color:DarkOrange !important;}
H3{color:DarkBlue !important;}
H4{color:Green !important;}
p{color:Black !important;}
</style>


# Lab Report 1
## CSE 15L - Spring 2022

### **Contents**

1. [Installing VS Code](#installing-vs-code)
2. [Remotely Connecting](#remotely-connecting)
3. [Trying Some Commands](#trying-some-commands)
4. [Moving Files with `scp`](#movineg-files-with-scp)
5. [Setting an SSH key](#setting-ssh-keys)
6. [Optimizing Remote Running](#optimizing-remote-running)


### **Installing VS Code**


* First, I installed [Visual Studio Code or VS Code](https://code.visualstudio.com/)
* VS Code looks like below when you open it.

<img alt="VS Code start" src="https://user-images.githubusercontent.com/66764591/162654164-6850a7cb-000a-4e79-a378-8dfb92fd0f64.png" width="800" height ="450">


### **Remotely Connecting**

* Look up course specific account, in this case, CSE15L account, [here](https://sdacs.ucsd.edu/~icc/index.php)


<img alt="Screen Shot 2022-04-10 at 7 30 18 PM" src="https://user-images.githubusercontent.com/66764591/162655264-faabef1e-a560-471a-833b-902b7bc3c2de.png" width="800" height ="450">

* Open a new terminal in VS Code - Terminal > New Terminal
* Type ssh cse15laccount@ieng6.ucsd.edu. Your terminal will look like this.
* Say 'yes' when prompted.

<img alt="Screen Shot 2022-04-01 at 8 27 43 AM" src="https://user-images.githubusercontent.com/66764591/162656118-56384222-46e3-441e-b85c-41db17306f22.png" width="800" height="900">

### **Trying Some Commands**

* Try running commandings like `cd ~` `cd` `ls -lat` `ls -a`


<img alt="Screen Shot 2022-04-10 at 7 45 39 PM" src="https://user-images.githubusercontent.com/66764591/162656594-6015243e-9856-4bc2-b78b-56ec0ff8ac59.png" width="800" height="412">

* When you want to exit, run the command `exit` or Ctrl-D


### **Moving Files with `scp`**

* You can copy and paste files between remote server and your computer.
* First create a file called `WhereAmI.java` on your computer 

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
* Run the command `scp WhereAmI.java cs15laausp22@ieng6.ucsd.edu:~/`.


<img alt="Screen Shot 2022-04-01 at 8 41 45 AM" src="https://user-images.githubusercontent.com/66764591/162657734-1403a65e-190e-4867-9b44-f40d9288169f.png" width="800" height="298">


* Run it using `javac` and `java`.

* When you run `ls`, you'll see the file on your remote server.


<img alt="Screen Shot 2022-04-10 at 8 00 35 PM" src="https://user-images.githubusercontent.com/66764591/162658020-490963b2-eaef-497b-8b24-4371b341de88.png" width="603" height="185">




### **Setting an SSH key**

* Run the command `ssh-keygen`
* When prompted like
```
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/<user-name>/.ssh/id_rsa): /Users/<user-name>/.ssh/id_rsa
Enter passphrase (empty for no passphrase): 
```
* do not add a passphrase.
* Once this is done, you can switch between the servers without entering password.

<img alt="Screen Shot 2022-04-01 at 9 14 07 AM" src="https://user-images.githubusercontent.com/66764591/162658431-33c19535-684c-4b14-b1f1-7979c280b388.png" width ="800" height="279">


### **Optimizing Remote Running**

* You can write commands in quotes at the end of `ssh` command so that you can directly run it on the remote server.
* `ssh cs15lsp22aau@ieng6.ucsd.edu "ls"`
* You can also use semicolons to run multiple commands. For example,
* `cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI`


<img alt="Screen Shot 2022-04-01 at 9 34 40 AM" src="https://user-images.githubusercontent.com/66764591/162660254-ccd64bcf-cddb-4fb2-a580-1330d663fe2d.png" width="800" height="150">
