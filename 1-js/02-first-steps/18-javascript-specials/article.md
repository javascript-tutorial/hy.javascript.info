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

Ավելին՝ <info:strict-mode>։

## Փոփոխականներ

Կարող ենք հայտարարել, օգտագործելով․

- `let`
- `const` (հաստատուն, չի կարող փոփոխվել)
- `var` (հին ոճ, կդիտարկենք ավելի ուշ)

Փոփոխականի անվանումը կարող է ներառել․
- Տառեր և թվեր, բայց առաջին նիշը չի կարող լինել թիվ:
- `$` և `_` նիշերը նորմալ են, համարժեք են տառերին։
- Թույլատրվում են նաև ոչ լատինական այբուբեններ և հիերոգլիֆներ, բայց սովորաբար չեն օգտագործվում:

Փոփոխականները տեսակավորվում են դինամիկ կերպով և կարող են պահել ցանկացած արժեք.

```js
let x = 5;
x = "Պողոս";
```

Տվյալների 8 տեսակ կա.

- `number` ինչպես կոտորակային, այնպես էլ ամբողջ թվերի համար,
- `bigint` կամայական երկարության ամբողջ թվերի համար,
- `string` տողերի համար,
- `boolean` տրամաբանական արժեքների համար: `true/false`,
- `null` -- մեկ արժեք ունեցող տեսակ `null`, նշանակում է «դատարկ» կամ «գոյություն չունի»,
- `undefined` -- մեկ արժեք ունեցող տեսակ `undefined`, նշանակում է «չնշված»,
- `object` և `symbol` -- բարդ տվյալների կառուցվածքների և յուրահատուկ նույնացուցիչների համար, մենք դեռ չենք սովորել դրանք։

`typeof` օպերատորը վերադարձնում է արժեքի տեսակը, երկու բացառությամբ.
```js
typeof null == "object" // սխալ լեզվում
typeof function(){} == "function" // ֆունկցիաները վերարտադրվում են առանձնահատուկ կերպով
```

Ավելին՝ <info:variables> և <info:types>։

## Փոխազդեցություն

Մենք բրաուզերն ենք օգտագործում որպես աշխատանքային միջավայր, ուստի UI-ի (օգտվողի ինտերֆեյս) հիմնական ֆունկցիաները կլինեն.

[`prompt(question, [default])`](mdn:api/Window/prompt)
: Հարց է տալիս՝ `question`, այնուհետև վերադարձնում է այն, ինչ մուտքագրել է այցելուն կամ՝ `null`, եթե այցելուն սեղմել է «Cancel»:

[`confirm(question)`](mdn:api/Window/confirm)
: Հարց է տալիս՝ `question` և առաջարկում ընտրություն կատարել՝ «Ok» կամ «Cancel». Ընտրությունը վերադարձվում է որպես `true/false`։

[`alert(message)`](mdn:api/Window/alert)
: Ցուցադրում է հաղորդագրություն՝ `message`։

Բոլոր այս ֆունկցիաները *մոդալ* են, նրանք դադարեցնում են կոդի կատարումը և թույլ չեն տալիս այցելուներին փոխազդեցություն ունենալ էջի հետ, մինչև նրանք չպատասխանեն։

Օրինակ.

```js run
let userName = prompt("Ձեր անո՞ւնը:", "Ալիսա");
let isTeaWanted = confirm("Թեյ կցանկանա՞ք:");

alert( "Այցելու` " + userName ); // Ալիսա
alert( "Թեյ ուզեց՝ " + isTeaWanted ); // true
```

Ավելին՝ <info:alert-prompt-confirm>։

## Օպերատորներ

JavaScript-ը սպասարկում է հետևյալ օպերատորները.

Թվաբանական
: Կանոնավոր` `* + - /`, նաև `%` մնացորդի համար և `**` աստիճան բարձրացնելու համար:

    Բինար գումարումը `+` միացնում է տողերը։ Եթե օպերանդներից մեկը տող է, մյուսը նույնպես վերածվում է տողի.

    ```js run
    alert( '1' + 2 ); // '12', տող
    alert( 1 + '2' ); // '12', տող
    ```

Վերագրում
: Կա պարզ վերագրում `a = b` և համակցված վերագրում `a *= 2`:

Բիթային
: Բիթային օպերատորները աշխատում են 32-բիթ ամբողջ թվերի հետ ամենացածր՝ բիթային մակարդակում. տեսեք [docs](mdn:/JavaScript/Guide/Expressions_and_Operators#Bitwise)-ում, երբ դրա կարիքը լինի:

Պայմանական
: Միակ օպերատորը երեք պարամետրով՝ `cond ? resultA : resultB`։ Եթե `cond` պայմանը ճշմարիտ է, վերադարձվում է `resultA`, հակառակ դեպքում՝ `resultB`։

Տրամաբանական օպերատորներ
: Տրամաբանական ԵՎ `&&` ու ԿԱՄ `||` օպերատորները իրականացնում են «կարճ միացման» արժեվորում, այնուհետև վերադարձնում են արժեք՝ որտեղ կանգ են առել (պարտադիր չէ `true`/`false`). Տրամաբանական ՈՉ `!` կերպափոխում է օպերանդը տրամաբանական տեսակի և վերադարձնում է հակառակ արժեքը։

Զրոյական միավորման օպերատոր
: `??` օպերատորը փոփոխականնների ցանկից հատկանշված արժեքի ընտրության հնարավորություն է տալիս: `a ?? b`-ի արդյունքը կլինի `a`, եթե այն `null/undefined` չէ, հակառակ դեպքում՝ `b`:

Համեմատություններ
: հավասարության ստուգումը `==` տարբեր տեսակի արժեքների դեպքում նրանց կերպափոխում է թվի (բացի `null` և `undefined` տեսակներից, որոնք միայն իրար կարող են հավասար լինել), այսպիսով սրանք հավասար են.

    ```js run
    alert( 0 == false ); // true
    alert( 0 == '' ); // true
    ```

    Այլ համեմատությունները նույնպես կերպափոխում են թվի:

    Խիստ հավասարության օպերատորը `===` չի կատարում փոխակերպում․ նրա համար տարբեր տեսակներ միշտ նշանակում է տարբեր արժեքներ։

    `null` և `undefined` արժեքները հատուկ են․ նրանք հավասար են `==` իրար և ուրիշ ոչնչի հավասար չեն։

    Մեծ/փոքր համեմատությունները տողերին համեմատում են նիշ-առ-շիշ, մյուս տեսակներին կերպափոխվում են թվի։

Այլ օպերատորներ
: Կա մի քանի ալյ օպերատոր, օր․՝ ստորակետի օպերատորը։

Ավելին՝ <info:operators>, <info:comparison>, <info:logical-operators>, <info:nullish-coalescing-operator>.

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
