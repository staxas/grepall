# grepall
Four solutions for non-positional bound AND grepping

grepa internally creates all possible combinations of AND regexes and connects them up with OR:
```
.*word1.*word2|.*word2.*word1
```

grepc creates a chain of piped greps, each filtering one of the words given as input:

```
grep word1 | grep word2
```

grepp concatenates a regex command using positive look-ahead:

```
^(?=.*word1)(?=.*word2)
```

awka uses awk instead of grep:

```
'/word1/ && /word2/'
```

For all commands, only the keywords need to be given as parameters:

```
cat test.txt | {command} word1 word2
```
