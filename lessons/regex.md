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

## Video

<iframe src="https://docs.google.com/presentation/d/14CHpffJ8KOeENMpvM5WfgJcyxYik8JlW2-uPmYG1eu0/embed?start=false&loop=false" frameborder="0" class="google-slides" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true" height="600"></iframe>

## Outline

- Unicode code point escapes: \\u { }
- The Unicode flag: u
- Character ranges: [ - ]
- Shorthand character class escapes: e.g. \\d
- Control character escapes: e.g. \\n
- Repetition ranges: {min,max}
- Grouping: ( )
- Quantifiers: + \* ?

## Resources

- [Unicode Table](https://unicode-table.com/en/)
- [RegEx101](https://regex101.com/)

## Challenges

<h3 class="challenge" id="regex-8" data-points="1">RegEx: Match a Sequence</h3>

Using RegEx101, construct three different regular expressions using ranges. Each expression should match all the non-space characters of either the first, second, or third line in the following string; each should not match any characters from other lines.

```
the quick brown fox jumped over the lazy dog
THE QUICK BROWN FOX JUMPED OVER THE LAZY DOG
0123456789
!@#$%^&*()_+=-~
< ><	>,.{}[]
ÜÖÄßüöä
```

<h3 class="challenge" id="regex-9" data-points="1">RegEx: Match a Sequence</h3>

Using RegEx101, construct a regular expression that will capture all the non-space and non-punctuation characters from the following string. Hint: the language is Georgian.

```
ლორემ იფსუმ დოლორ სით ამეთ, სენსერით სუავითათე ყუო ნე. ეა ნათუმ ფოსთულანთ სცრიფსერით სით. სალე ულლუმ რეფორმიდანს უთ ჰის. მუნერე მელიუს მელიორე ან იუს, ინ სეა ერუდითი ფართიენდო ინცორრუფთე. ნო ველ მაზიმ ცჰორო.
```

<h3 class="challenge" id="regex-10" data-points="1">RegEx: Match a Sequence</h3>

Using RegEx101, construct a regular expression using shorthand character classes that matches every non-space character in all lines of the following string. Make sure you match by line, not just by character; this means you should see each line match as a whole, not just each individual character.

```
28aP
01tT
87xS
26pL
63fU
```

<h3 class="challenge" id="regex-11" data-points="1">RegEx: Match a Sequence</h3>

Using RegEx101, construct two different regular expressions using shorthand character classes. Each one should either only match the numbers or the whitespace characters in the following string.

```
1 sheep, 2 sheep, 3 sheep, 4 sheep, 5 sheep, 6 sheep, 7 sheep, 8 sheep, 9 sheep, 10 sheep

the whitespace class include newlines
and of course forget		tabs too
```

<h3 class="challenge" id="regex-12" data-points="1">RegEx: Match a Sequence</h3>

Using RegEx101, construct a regular expression that matches the first three lines in the following string. Assume the personal ID (part before '@') and the domain name (part after '@') can be arbitrarily long but must only be made up of word characters ' \\w '. Assume the suffix ('org' / 'com' / etc...) should be between 2 and 4 characters long and must only be made of lower-case letters.

There should be no partial matches on the other lines!

```
weofFKJHGKHShgdfkghdkfghkfh@sdoifj.com
BlUR_Gh@gmail.org
asdf_523@124453129837129874938754.zh

tomson@out#tag.se
megaman@mommy.s_eo
bigboy-@bumble.bee
tommy@gun.SQL
pase_12pf@yahoo.sucks
```

<h3 class="challenge" id="regex-13" data-points="1">RegEx: Match a Sequence</h3>

Using RegEx101, construct a regular expression that matches the first four lines of the following string. Do not use the range syntax ' {min,max} '; use only quantifiers.

It's okay this time if you get partial matches on the other lines.

```
/
/a/path/to/a/index.html
/2014-12-05/window.html
/path_with_underscores/component.html

/Post-01/example.html.html
/Post-01/example.html%##!
/Post-01/example
$$@&/Post-01/example.html
```
