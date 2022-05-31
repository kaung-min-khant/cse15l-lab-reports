# Lab Report 4
---
## CSE 15L - Spring 2022
---

### **Contents**

1. [Snippet 1](#snippet-1)
2. [Snippet 2](#snippet-2)
3. [Snippet 3](#snippet-3)

[My `markdown-parser` repository](https://github.com/kaung-min-khant/markdown-parser) and 
[Repository My Group Reviewed](https://github.com/Luke-Sheltraw/markdown-parser/)

### Snippet 1

```
`[a link`](url.com)

[another link](`google.com)`

[`cod[e`](google.com)

[`code]`](ucsd.edu)

```

### Snippet 2

```
[a [nested link](a.com)](b.com)

[a nested parenthesized url](a.com(()))

[some escaped \[ brackets \]](example.com)

```

Expected output: ``[`google.com, google.com, ucsd.edu]``

Junit Test

```
@Test
    public void snippetTest1() throws IOException {
        List<String> expected = List.of("%60google.com", "google.com", "ucsd.edu");
        List<String> actual = MarkdownParse.getLinks("snippetTest1.md");
        assertEquals(expected, actual);
    }
    
```

Output for my repository


<img width="660" height="442" alt="CleanShot 2022-05-30 at 19 11 54@2x" src="https://user-images.githubusercontent.com/66764591/171094550-3752194d-9324-4ef5-8b81-2c737085dcf2.png">


### Snippet 3

```
[this title text is really long and takes up more than 
one line

and has some line breaks](
    https://www.twitter.com
)

[this title text is really long and takes up more than 
one line](
https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule
)


[this link doesn't have a closing parenthesis](github.com

And there's still some more text after that.

[this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/


)

And then there's more text
```
