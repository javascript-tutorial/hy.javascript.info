# Պայմանական ճյուղավորում. if, ?

Երբեմն, մենք կարիք ենք ունենում կատարել տարբեր գործողություններ՝ կախված տարբեր պայմաններից։

Դա անելու համար մենք կարող ենք օգտագործել `if` դրույթը և `?` պայմանական օպերատորը: Վերջինս նաև կոչվում է «հարցական նշան»-ի օպերատոր։

## «if» դրույթը

`if(...)` դրույթը արժեվորում է փակագծերում նշված պայմանը և, եթե արդյունքը `true` է, ապա կատարում է կոդի բլոկը:

Օրինակ.

```js run
let year = prompt('Ո՞ր թվականին է թողարկվել ECMAScript-2015 ստանդարտը:', '');

*!*
if (year == 2015) alert( 'Դուք ճիշտ եք:' );
*/!*
```

Վերոնշյալ օրինակում պայմանը ստուգում է պարզ հավասարություն (`year == 2015`), բայց այն կարող է շատ ավելի բարդ լինել:

Եթե մենք ցանկանում ենք կատարել մեկից ավել դրույթներ, ապա մեր կոդի հատվածը պետք է վերցնենք ձևավոր փակագծերի մեջ:

```js
if (year == 2015) {
  alert( "Ճիշտ է:" );
  alert( "Դուք այնքան խելացի եք․․․" );
}
```

Մենք խորհուրդ ենք տալիս պատել կոդի հատվածը `{}` ձևավոր փակագծերով ամեն անգամ, երբ օգտագործում եք `if` դրույթը, նույնիսկ եթե կատարման համար առկա է միայն մեկ դրույթ։ Այդպես բարելավվում է ընթեռնելիությունը:

## Բուլյան փոխակերպում

`if (…)` դրույթը գնահատում է իր փակագծերում առկա արտահայտությունը և արդյունքը դարձնում բուլյան:

Եկեք հիշենք փոխակերպման կանոնները <info:type-conversions> գլխից.

- `0` թիվը, դատարկ տողը `""`, `null`, `undefined` և `NaN`՝ սրանք բոլորը դառնում են `false`: Այդ պատճառով կոչվում են «կեղծ» արժեքներ։
- Մյուս արժեքները դառնում են `true`, ուստի դրանք կոչվում են «ճշմարիտ»:

Այսպիսով, այս պայմանի ներսում կոդը երբեք չի գործարկվի.

```js
if (0) { // 0-ն կեղծ է
  ...
}
```

...և այս պայմանի ներսում միշտ կգործարկվի.

```js
if (1) { // 1-ը ճշմարիտ է
  ...
}
```

Մենք կարող ենք նաև նախապես գնահատված բուլյան արժեք փոխանցել `if`-ին, այսպես.

```js
let cond = (year == 2015); // հավասարությունը գնահատվում է ճշմարիտ կամ կեղծ

if (cond) {
  ...
}
```

## «else» դրույթը

`if` դրույթը կարող է պարունակել կամընտրական, ոչ պարտադիր «else» բլոկ: Այն գործարկվում է, երբ պայմանը կեղծ է:

Օրինակ.
```js run
let year = prompt('Ո՞ր թվականին է հրապարակվել ECMAScript-2015 դասակարգումը:', '');

if (year == 2015) {
  alert( 'Դուք ճիշտ գուշակեցիք:' );
} else {
  alert( 'Ինչպե՞ս կարող եք այդքան սխալվել:' ); // ցանկացած արժեք, բացի 2015-ից
}
```

## Մի քանի պայմաններ. «else if»

Երբեմն մենք ցանկանում ենք փորձարկել պայմանի մի քանի տարբերակներ: `else if` դրույթը մեզ թույլ է տալիս անել դա:

Օրինակ.

```js run
let year = prompt('Ո՞ր թվականին է հրապարակվել ECMAScript-2015 դասակարգումը:', '');

if (year < 2015) {
  alert( 'Շատ վաղ է...' );
} else if (year > 2015) {
  alert( 'Շատ ուշ է' );
} else {
  alert( 'Ճիշտ այդպես:' );
}
```

Վերևի կոդում JavaScript-ը նախ ստուգում է `year < 2015`-ը: Եթե դա կեղծ է, անցում է կատարում հաջորդ պայմանին՝ `year > 2015`: Եթե դա նույնպես կեղծ է, ցույց է տալիս վերջին `alert`-ը:

Կարող են լինել ավելի շատ `else if` բլոկներ: Վերջին `else`-ը կամընտիր է:

## Conditional operator '?'

Sometimes, we need to assign a variable depending on a condition.

For instance:

```js run no-beautify
let accessAllowed;
let age = prompt('How old are you?', '');

*!*
if (age > 18) {
  accessAllowed = true;
} else {
  accessAllowed = false;
}
*/!*

alert(accessAllowed);
```

The so-called "conditional" or "question mark" operator lets us do that in a shorter and simpler way.

The operator is represented by a question mark `?`. Sometimes it's called "ternary", because the operator has three operands. It is actually the one and only operator in JavaScript which has that many.

The syntax is:
```js
let result = condition ? value1 : value2;
```

The `condition` is evaluated: if it's truthy then `value1` is returned, otherwise -- `value2`.

For example:

```js
let accessAllowed = (age > 18) ? true : false;
```

Technically, we can omit the parentheses around `age > 18`. The question mark operator has a low precedence, so it executes after the comparison `>`.

This example will do the same thing as the previous one:

```js
// the comparison operator "age > 18" executes first anyway
// (no need to wrap it into parentheses)
let accessAllowed = age > 18 ? true : false;
```

But parentheses make the code more readable, so we recommend using them.

````smart
In the example above, you can avoid using the question mark operator because the comparison itself returns `true/false`:

```js
// the same
let accessAllowed = age > 18;
```
````

## Multiple '?'

A sequence of question mark operators `?` can return a value that depends on more than one condition.

For instance:
```js run
let age = prompt('age?', 18);

let message = (age < 3) ? 'Hi, baby!' :
  (age < 18) ? 'Hello!' :
  (age < 100) ? 'Greetings!' :
  'What an unusual age!';

alert( message );
```

It may be difficult at first to grasp what's going on. But after a closer look, we can see that it's just an ordinary sequence of tests:

1. The first question mark checks whether `age < 3`.
2. If true -- it returns `'Hi, baby!'`. Otherwise, it continues to the expression after the colon '":"', checking `age < 18`.
3. If that's true -- it returns `'Hello!'`. Otherwise, it continues to the expression after the next colon '":"', checking `age < 100`.
4. If that's true -- it returns `'Greetings!'`. Otherwise, it continues to the expression after the last colon '":"', returning `'What an unusual age!'`.

Here's how this looks using `if..else`:

```js
if (age < 3) {
  message = 'Hi, baby!';
} else if (age < 18) {
  message = 'Hello!';
} else if (age < 100) {
  message = 'Greetings!';
} else {
  message = 'What an unusual age!';
}
```

## Non-traditional use of '?'

Sometimes the question mark `?` is used as a replacement for `if`:

```js run no-beautify
let company = prompt('Which company created JavaScript?', '');

*!*
(company == 'Netscape') ?
   alert('Right!') : alert('Wrong.');
*/!*
```

Depending on the condition `company == 'Netscape'`, either the first or the second expression after the `?` gets executed and shows an alert.

We don't assign a result to a variable here. Instead, we execute different code depending on the condition.

**It's not recommended to use the question mark operator in this way.**

The notation is shorter than the equivalent `if` statement, which appeals to some programmers. But it is less readable.

Here is the same code using `if` for comparison:

```js run no-beautify
let company = prompt('Which company created JavaScript?', '');

*!*
if (company == 'Netscape') {
  alert('Right!');
} else {
  alert('Wrong.');
}
*/!*
```

Our eyes scan the code vertically. Code blocks which span several lines are easier to understand than a long, horizontal instruction set.

The purpose of the question mark operator `?` is to return one value or another depending on its condition. Please use it for exactly that. Use `if` when you need to execute different branches of code.
