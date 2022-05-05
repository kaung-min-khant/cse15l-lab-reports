<style>
H1{color:Black !important;}
H2{color:DarkOrange !important;}
H3{color:DarkBlue !important;}
H4{color:Green !important;}
p{color:Black !important;}
</style>


# Lab Report 2
## CSE 15L - Spring 2022

### Code Change 1


<img alt="test 1 code change" src="https://user-images.githubusercontent.com/66764591/166862449-a941c65c-a387-48d2-b87d-3901d7f552b0.jpeg" width="660" height ="454">

[Failure Inducing Input 1](https://github.com/kaung-min-khant/markdown-parser/blob/c69db6f8b6c32b0a3dcd549a714c73f428edb3d6/test1..md)

Before the code is changed, below is the output with run command `javac MarkdownParse.java` `java MarkdownParse test1.md`

<img alt="test1-output" src="https://user-images.githubusercontent.com/66764591/166863970-7cef9dd7-a117-4019-8cb5-1e3d51903343.png" width ="660" height = "276">

Failure inducing input = `[a link!] google.com` doesn't have a parenthesis around `google.com`
Symptom of the code = `No such file exception`

* Add `if` statement to solve a bug input when there is no parenthesis. 

``
if (markdown.indexOf('(') !=1)
``

### Code Change 2

<img alt="test 2 code change" src="https://user-images.githubusercontent.com/66764591/166865589-602e2ca5-4e92-434d-a973-c5efe9f62699.png" width="660" height ="454">

[Failue Inducing Input 2](https://github.com/kaung-min-khant/markdown-parser/blob/cce8ccadc35ef79d901984994e105c52cbbe5f44/test2.md)

Before the code is changed, below is the output with run command `javac MarkdownParse.java` `java MarkdownParse test2.md`

<img alr="test 2 output" src = "https://user-images.githubusercontent.com/66764591/166864903-4643054f-4eae-4683-a75c-50b45906419e.png" width = "660" height = "48.6">

Failure inducing input = `link (apple.com)` doesn't have square bracket around `link`
Symptom of the code = the file doesn't run

* Add another `if` statement to solve a bug input when there is no parenthesis and bracket. 

``
if (markdown.indexOf('(' != -1 && markdown.indexOf("[") != -1){
...
}
``

### Code Change 3

<img alt="test 3 code change" src="https://user-images.githubusercontent.com/66764591/166866307-63a90cb3-89ee-4c54-9fb3-7e7e51f33e35.png" width="660" height ="454">

[Failue Inducing Input 3](https://github.com/kaung-min-khant/markdown-parser/blob/eb570d6b65a0bfb51dc7ab692efd9781d725332c/test3.md)

Before the code is changed, below is the output with run command `javac MarkdownParse.java` `java MarkdownParse test3.md`

<img alr="test 3 output" src = "https://user-images.githubusercontent.com/66764591/166865826-994b16bc-1a3e-4eb3-9ff6-81eab4acbfc4.png" width = "660" height = "66.6">

Failure inducing input = there's a space between `[link]` and `(facebook.com)`
Symptom of the code = the output returns `[facebook.com]`

* Add another if statement as below so that the output would not mistakenly produce `[facebook.com]` but instead return `[]` and end the program.

``
if (openParen- closeBracket == 1){
   toReturn.add(markdown.substring(openParen + 1, closeParen));
}
 ``
