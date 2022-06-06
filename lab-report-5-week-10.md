# Lab Report 5
---
## CSE 15L - Spring 2022
---
Edited `script.sh` file:
```
for file in test-files/*.md;
do
  echo "$file:"
  java MarkdownParse $file
done
```
Then, run `make test` and `time bash script.sh`. The added line `echo "$file:"` shows the test name before giving the output.
The differences are found using the command `vimdiff`.

### [Test File 519](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/519.md)
## Expected output

```
test-files/519.md:
[]
```

## My output

```
test-files/519.md:
[]
```

## cse15lsp22-markdown-parse output

```
[uri1]
```
The fix is 
```
int nextCloseBracket = markdown.indexOf("]", nextOpenBracket);

int openParen = markdown.indexOf("(", nextCloseBracket);
```
This will only search openParen after matching closing bracket is found. 

### [Test File 149](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/149.md)

## Expected output

```
test-files/149.md:
[]
```

## My output

```
test-files/149.md:
[okay.]
```

## cse15lsp22-markdown-parse output

```
test-files/149.md:
[]
```

The cse15lsp22-markdown-parse is correct. Since the test file contains string `okay.` and my code relies on `.` to find the link, the fix is 

```
ArrayList<Integer> periodList = new ArrayList<Integer>();
int currentIndex = 0;
while(currentIndex < markdown.length()) {
    int nextPeriodIndex = markdown.indexOf(".", currentIndex + 1);
    if(nextPeriodIndex != -1) {
        periodList.add(nextPeriodIndex);
        currentIndex = nextPeriodIndex;
    } else {
        break;
    }
}
for(int periodIndex: periodList) {
    int startIndex = periodIndex;
    int endIndex = periodIndex;
    ...
}
```

