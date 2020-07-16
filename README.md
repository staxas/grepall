# grepall
Four solutions for non-positional bound AND grepping


For all commands, keywords need to be given as parameters:

```
cat test.txt | {command} word1 word2
```


grepc creates a chain of piped greps, each filtering one of the words given as input:

```
grep word1 | grep word2
```

grepr uses a regex command based on positive look-ahead:

```
grep -P "^(?=.*word1)(?=.*word2)"
```

grepa renders all possible combinations of AND-like positional regexes and connects them up with OR:

```
grep -E "word1.*word2|word2.*word1"
```

awka uses awk instead of grep:

```
awk "/word1/ && /word2/"
```
