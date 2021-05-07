# Vue.js Katas

This is a sseries of katas to strengthen your existing Vue.js knowledge, as well as practice the newly learned concepts like computed, life cycle hooks, new event listeners, patterns for validations etc.

The katas follow no particular order. There is no definitive answer to the katas. Deconstruct the instructions. Analyse wich elements, event listeners, methods, computeds, data fields and directives you might need to solve the problem. Draw your layout by hand to get a better picture of how the interface could look like.

## Kata 0

---

Create a vue repository with `vue-router` and `vuetify` enabled. Create different routes for the individual katas. Push your project to GitHub and invite @gabrielheinrich and @valeriakori to your project so we can do a code review. Feel free to ask for advice and review at any time!

## Kata 1 - Trivia Quiz API with Vuetify

---

Fetch some true/false questions from the [Trivia API](https://opentdb.com/api_config.php) and display the questions with their respective answer in an [expansion panel](https://vuetifyjs.com/en/components/expansion-panels/)

## Kata 2 - Wikipedia API

---

Add the [wikipedia package](https://www.npmjs.com/package/wikipedia) to your project. Create an input field and fetch the page of the input value. Think about edge cases like error handling when no pages are returned as well as displaying multiple responses to your request.

## Kata 3 - Text to L33T5P34K

---

```bash
leetspeak "Hello World"
H3ll0 W0rld
```

Write an interface that converts an input value into leetspeak, i.e. letters are replaced as follows:

```none
a => 4
b => 8
e => 3
g => 6
i => 1
o => 0
s => 5
t => 7
```

[Example](https://alexdevero.com/labs/leetspeak/)

## Kata 4 - Number to Words

---

Create an interface that display the value of a numbers input field typed out as words.

```none

1234 => thirteen  thousand four hundred fifty three
8392 =>  eight  thousand three hundred ninety two
42 => fourty two
```

Use this function to do the actual conversion:

```js
function converter(numberInput) {
  let oneToTwenty = [
    "",
    "one ",
    "two ",
    "three ",
    "four ",
    "five ",
    "six ",
    "seven ",
    "eight ",
    "nine ",
    "ten ",
    "eleven ",
    "twelve ",
    "thirteen ",
    "fourteen ",
    "fifteen ",
    "sixteen ",
    "seventeen ",
    "eighteen ",
    "nineteen ",
  ];
  let tenth = [
    "",
    "",
    "twenty",
    "thirty",
    "forty",
    "fifty",
    "sixty",
    "seventy",
    "eighty",
    "ninety",
  ];

  if (numberInput.toString().length > 7) return (myDiv.innerHTML = "overlimit");
  console.log(numberInput);

  let num = ("0000000" + numberInput)
    .slice(-7)
    .match(/^(\d{1})(\d{1})(\d{2})(\d{1})(\d{2})$/);
  console.log(num);
  if (!num) return;

  let outputText =
    num[1] != 0
      ? (oneToTwenty[Number(num[1])] ||
          `${tenth[num[1][0]]} ${oneToTwenty[num[1][1]]}`) + " million "
      : "";

  outputText +=
    num[2] != 0
      ? (oneToTwenty[Number(num[2])] ||
          `${tenth[num[2][0]]} ${oneToTwenty[num[2][1]]}`) + "hundred "
      : "";
  outputText +=
    num[3] != 0
      ? (oneToTwenty[Number(num[3])] ||
          `${tenth[num[3][0]]} ${oneToTwenty[num[3][1]]}`) + " thousand "
      : "";
  outputText +=
    num[4] != 0
      ? (oneToTwenty[Number(num[4])] ||
          `${tenth[num[4][0]]} ${oneToTwenty[num[4][1]]}`) + "hundred "
      : "";
  outputText +=
    num[5] != 0
      ? oneToTwenty[Number(num[5])] ||
        `${tenth[num[5][0]]} ${oneToTwenty[num[5][1]]} `
      : "";

  return outputText;
}
console.log("numberInput(1234) :", converter(13453));
```

## Kata 5

---

Create an interface that displays todays date as a locale string. Locale means, a string is formatted to the regions standart, e.g.

```none
german locale: 'de-DE'
7.5.2021

us locale: 'en-US'
5/7/2021
```

[Locale Date String Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/toLocaleDateString)

**Bonus:** Create a [dropdown menu](https://vuetifyjs.com/en/components/selects/#usage) to select between different language options.
