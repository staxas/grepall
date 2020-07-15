# grepall
Two solutions for non-positional bound AND grepping

grepa internally creates all possible combinations of AND regexes and connects them up with OR:
```
.*word1.*word2|.*word2.*word1
```
grepc creates a chain of piped greps, each filtering one of the words given as input:

```
grep word1 | grep word2
```

For both commands, only the keywords need to be given as parameters:

```
cat test.txt | grepa word1 word2
```
or
```
cat test.txt | grepc word1 word2
```
