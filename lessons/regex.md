<iframe src="https://docs.google.com/presentation/d/1KswRAusERu5fcyHyWG76uQWxzPalQj10Uaa8Vb10lXA/embed?start=false&loop=false" frameborder="0" class="google-slides" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true" height="600"></iframe>

## Outline

- Match a sequence: / /
- Escapes: \
- The global flag: g
- The wildcard: .
- Character sets: [ ]
- Excluded sets: [^ ]

## Resources

- [Unicode Table](https://unicode-table.com/en/)
- [RegEx101](https://regex101.com/)

## Challenges

<h3 class="challenge" id="regex-1" data-points="1">RegEx: Match a Sequence</h3>

Using RegEx101, construct a regular expression that matches both "pick" and "peck" and returns exactly 12 matches with the following string.

```
Peter Piper picked a peck of pickled peppers. A peck of pickled peppers Peter Piper picked. If Peter Piper picked a peck of pickled peppers, where’s the peck of pickled peppers Peter Piper picked?
```

<h3 class="challenge" id="regex-2" data-points="1">RegEx: Match a Sequence</h3>

Using RegEx101, construct a regular expression that matches "butter", "bitter", and "better" and returns exactly 13 matches with the following string.

```
Betty Botter bought some butter but she said the butter’s bitter. If I put it in my batter, it will make my batter bitter. But a bit of better butter will make my batter better. So ‘twas better Betty Botter bought a bit of better butter.
```

<h3 class="challenge" id="regex-3" data-points="1">RegEx: Match a Sequence</h3>

Using RegEx101, construct a regular expression that matches only the first line of the following string.

```
\b51+4\S
511149
```

<h3 class="challenge" id="regex-4" data-points="1">RegEx: Match a Sequence</h3>

Using RegEx101, construct a regular expression that matches only the first line of the following string.

```
\nabatha\s
abatha
nabathas
```

<h3 class="challenge" id="regex-5" data-points="1">RegEx: Match a Sequence</h3>

Using RegEx101, construct a regular expression that matches only the first three lines of the following string and returns exactly 3 matches.

```
aBa
AbA
ccc
CBa
BaC
ccb
ACA
```

<h3 class="challenge" id="regex-6" data-points="1">RegEx: Match a Sequence</h3>

Using RegEx101, construct a regular expression that matches only the first three lines of the following string and returns exactly 3 matches.

```
\so
m\t
m\n
me
m eee
 on
m	\n
\s
meon
```

<h3 class="challenge" id="regex-7" data-points="2">RegEx: Match a Sequence</h3>

Using RegEx101, construct a regular expression that matches everything except the first three lines of the following string. Hint: exclude \\n (newline) as well.

```
123
abc
ABC
gT4
331
CaA
cAa
4tG
```
