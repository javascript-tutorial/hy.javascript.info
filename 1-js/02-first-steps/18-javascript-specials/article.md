# JavaScript-ի հատկանիշները

Այս գլխում հակիրճ կամփոփենք JavaScript-ի առանձնահատկությունները, որոնք ուսումնասիրել ենք մինչ այս, հատուկ ուշադրություն դարձնելով նրբություններին:

## Կոդի կառուցվածքը

Հայտարարությունները տարանջատվում են կետ-ստորակետով.

```js run no-beautify
alert('Ողջույն'); alert('Աշխարհ');
```

Սովորաբար տողադարձը նույնպես դիտվում է որպես տարանջատիչ և սա նույնպես կաշխատի.

```js run no-beautify
alert('Ողջույն')
alert('Աշխարհ')
```

Դա կոչվում է «կետ-ստորակետի ավտոմատ տեղադրում»։ Երբեմն այն չի աշխատում, օրինակ.

```js run
alert("Այս հաղորդագրությունից հետո սխալ կլինի:")

[1, 2].forEach(alert)
```

Կոդի գրելաձևին և ոճին վերաբերվող ուղեցույցների մեծ մասը խորհուրդ են տալիս, որ մենք պետք է կետ-ստորակետ դնենք յուրաքանչյուր հայտարարությունից հետո:

Կոդերի բլոկներից `{...}` և դրանցով կառուցված շարահյուսական կոնստրուկցիաներից հետո կետ-ստորակետեր չեն պահանջվում՝ ինչպես ցիկլում է.

```js
function f() {
  // կետ-ստորակետ պետք չէ ֆունկցիայի հայտարարումից հետո
}

for(;;) {
  // կետ-ստորակետ պետք չէ ցիկլից հետո
}
```

...Սակայն, եթե մենք «ավելնորդ» կետ-ստորակետ դնենք, սխալ չի լինի։ Այն պարզապես կանտեսվի:

Մանրամասն՝ <info:structure>.

## Խիստ ռեժիմ

Ժամանակակից JavaScript-ի բոլոր առանձնահատկություններն ակտիվացնելու համար, կոդի սկզբում հարկավոր է նշել `"use strict"`։

```js
'use strict';

...
```

Այդ ցուցումը պետք է լինի սքրիփթի սկզբում կամ ֆունկցիայի մարմնի սկզբում:

Առանց `"use strict"` օգտագործելու ամեն ինչ կաշխատի, բայց որոշ առանձնահատկությունների վարքագիծը կլինի հնաոճ ձևի հետ «համատեղելի» եղանակով։ Ընդհանուր առմամբ մենք կնախընտրեինք ժամանակակից վարքագիծը:

Լեզվի որոշ ժամանակակից առանձնահատկություններ (օրինակ՝ կլասները, որոնք պետք է սովորենք հետագայում) լռեցյալ ակտիվացնում են խիստ ռեժիմը։

More in: <info:strict-mode>.

## Variables

Can be declared using:

- `let`
- `const` (constant, can't be changed)
- `var` (old-style, will see later)

A variable name can include:
- Letters and digits, but the first character may not be a digit.
- Characters `$` and `_` are normal, on par with letters.
- Non-Latin alphabets and hieroglyphs are also allowed, but commonly not used.

Variables are dynamically typed. They can store any value:

```js
let x = 5;
x = "John";
```

There are 8 data types:

- `number` for both floating-point and integer numbers,
- `bigint` for integer numbers of arbitrary length,
- `string` for strings,
- `boolean` for logical values: `true/false`,
- `null` -- a type with a single value `null`, meaning "empty" or "does not exist",
- `undefined` -- a type with a single value `undefined`, meaning "not assigned",
- `object` and `symbol` -- for complex data structures and unique identifiers, we haven't learnt them yet.

The `typeof` operator returns the type for a value, with two exceptions:
```js
typeof null == "object" // error in the language
typeof function(){} == "function" // functions are treated specially
```

More in: <info:variables> and <info:types>.

## Interaction

We're using a browser as a working environment, so basic UI functions will be:

[`prompt(question, [default])`](mdn:api/Window/prompt)
: Ask a `question`, and return either what the visitor entered or `null` if they clicked "cancel".

[`confirm(question)`](mdn:api/Window/confirm)
: Ask a `question` and suggest to choose between Ok and Cancel. The choice is returned as `true/false`.

[`alert(message)`](mdn:api/Window/alert)
: Output a `message`.

All these functions are *modal*, they pause the code execution and prevent the visitor from interacting with the page until they answer.

For instance:

```js run
let userName = prompt("Your name?", "Alice");
let isTeaWanted = confirm("Do you want some tea?");

alert( "Visitor: " + userName ); // Alice
alert( "Tea wanted: " + isTeaWanted ); // true
```

More in: <info:alert-prompt-confirm>.

## Operators

JavaScript supports the following operators:

Arithmetical
: Regular: `* + - /`, also `%` for the remainder and `**` for power of a number.

    The binary plus `+` concatenates strings. And if any of the operands is a string, the other one is converted to string too:

    ```js run
    alert( '1' + 2 ); // '12', string
    alert( 1 + '2' ); // '12', string
    ```

Assignments
: There is a simple assignment: `a = b` and combined ones like `a *= 2`.

Bitwise
: Bitwise operators work with 32-bit integers at the lowest, bit-level: see the [docs](mdn:/JavaScript/Guide/Expressions_and_Operators#Bitwise) when they are needed.

Conditional
: The only operator with three parameters: `cond ? resultA : resultB`. If `cond` is truthy, returns `resultA`, otherwise `resultB`.

Logical operators
: Logical AND `&&` and OR `||` perform short-circuit evaluation and then return the value where it stopped (not necessary `true`/`false`). Logical NOT `!` converts the operand to boolean type and returns the inverse value.

Nullish coalescing operator
: The `??` operator provides a way to choose a defined value from a list of variables. The result of `a ?? b` is `a` unless it's `null/undefined`, then `b`.

Comparisons
: Equality check `==` for values of different types converts them to a number (except `null` and `undefined` that equal each other and nothing else), so these are equal:

    ```js run
    alert( 0 == false ); // true
    alert( 0 == '' ); // true
    ```

    Other comparisons convert to a number as well.

    The strict equality operator `===` doesn't do the conversion: different types always mean different values for it.

    Values `null` and `undefined` are special: they equal `==` each other and don't equal anything else.

    Greater/less comparisons compare strings character-by-character, other types are converted to a number.

Other operators
: There are few others, like a comma operator.

More in: <info:operators>, <info:comparison>, <info:logical-operators>, <info:nullish-coalescing-operator>.

## Loops

- We covered 3 types of loops:

    ```js
    // 1
    while (condition) {
      ...
    }

    // 2
    do {
      ...
    } while (condition);

    // 3
    for(let i = 0; i < 10; i++) {
      ...
    }
    ```

- The variable declared in `for(let...)` loop is visible only inside the loop. But we can also omit `let` and reuse an existing variable.
- Directives `break/continue` allow to exit the whole loop/current iteration. Use labels to break nested loops.

Details in: <info:while-for>.

Later we'll study more types of loops to deal with objects.

## The "switch" construct

The "switch" construct can replace multiple `if` checks. It uses `===` (strict equality) for comparisons.

For instance:

```js run
let age = prompt('Your age?', 18);

switch (age) {
  case 18:
    alert("Won't work"); // the result of prompt is a string, not a number
    break;

  case "18":
    alert("This works!");
    break;

  default:
    alert("Any value not equal to one above");
}
```

Details in: <info:switch>.

## Functions

We covered three ways to create a function in JavaScript:

1. Function Declaration: the function in the main code flow

    ```js
    function sum(a, b) {
      let result = a + b;

      return result;
    }
    ```

2. Function Expression: the function in the context of an expression

    ```js
    let sum = function(a, b) {
      let result = a + b;

      return result;
    };
    ```

3. Arrow functions:

    ```js
    // expression at the right side
    let sum = (a, b) => a + b;

    // or multi-line syntax with { ... }, need return here:
    let sum = (a, b) => {
      // ...
      return a + b;
    }

    // without arguments
    let sayHi = () => alert("Hello");

    // with a single argument
    let double = n => n * 2;
    ```


- Functions may have local variables: those declared inside its body or its parameter list. Such variables are only visible inside the function.
- Parameters can have default values: `function sum(a = 1, b = 2) {...}`.
- Functions always return something. If there's no `return` statement, then the result is `undefined`.

Details: see <info:function-basics>, <info:arrow-functions-basics>.

## More to come

That was a brief list of JavaScript features. As of now we've studied only basics. Further in the tutorial you'll find more specials and advanced features of JavaScript.
