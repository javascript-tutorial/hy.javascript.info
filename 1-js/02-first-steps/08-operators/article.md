# Մաթեմատիկական տարրական գործողություններ

Մենք գպրոցից գիտեն շատ գործողություններ։ Դրանցից են, օրինակ գումարում `+`, բազմապատկում `*`, հանում `-` և այլն։

Այս հատվածում, մենք կսկսենք պարզ գործողույթուններից, ապա կկենտրոնանանք JavaScript-ի հատուկ ասպեկտների վրա, որոնք գոյություն չունեն դպրոցական թվաբանության մեջ։

## "ունար", "բինար" և "օպերանդ" հասկացությունները

Մինչ առաջ անցնելը, եկեք հասկանանք որոշ տերմինների նշանակությունը։

-  *Նշան* -- հասկացություն, որը կազմում է գործողությունների հիմքը։ Օրինակ ՝ `5 * 2` –ի բազմապատկման մեջ կան երկու օպերանդներ՝ ձախ օպերանդը՝ `5`, իսկ աջը՝ `2`: Երբեմն, մարդիկ «օպերանդներ»-ի փոխարեն, անվանում են «արգումենտներ»:
- Գործողությունը համարվում է *ունար* եթե այն ունի միայն մեկ օպերանդ։ Օրինակ՝ ունար ժխտումը `-` հակադարձում է թվի նշանը:

    ```js run
    let x = 1;

    *!*
    x = -x;
    */!*
    alert( x ); // -1, կիրառվել է ունար ժխտում
    ```
- Գործողույթունը համարվում է *երկուական* եթե այն ունի երկու օպերանդ. Նույն մինուսը գոյություն ունի նաև հանման տեսքով:

    ```js run no-beautify
    let x = 1, y = 3;
    alert( y - x ); // 2, երկուական մինուսը ցույց է տալիս արժեքների տարբերությունը
    ```

  Վերը նշված օրինակներում մենք ունենք երկու տարբեր օպերատորներ, որոնք կիրառում են նույն նշանը. Ժխտման օպերատոր, նշանը հակադարձող ունարի օպերատոր և հանում օպերատոր, երկուական օպերատոր, որը հանում է մեկ թիվը մյուսից:

## Մաթեմատիկա

Հետևյալ մաթեմատիկական գործողությունները աջակցվում են․

- Գումարում `+`,
- Հանում `-`,
- Բազմապատկում `*`,
- Բաժանում `/`,
- Մնացորդ `%`,
- Աստիճան բարձրացնել (անգլ․՝ Exponentiation) `**`.

Առաջին չորս գործողությունները պարզ են, մինչդեռ `%` և `**` գործողությունների համար, մի քան խոսք ավելին։

### Մնացորդ %

Մնացորդի օպերատորը հետևյալն է `%`, չնայած նշանի պատկերմանը, դա կապված չէ տոկոսների հետ:

Հետրյալ հավասարման `a % b` արդյունքը [remainder](https://en.wikipedia.org/wiki/Remainder) `a` բաժանած `b` մնացորդն է։

Օրինակ՝

```js run
alert( 5 % 2 ); // 1, 5-ը բաժանած 2-ի մնացորդը
alert( 8 % 3 ); // 2, 8-ը բաժանած 3-ի մնացորդը
```

### Աստիճան բարձրացնել  **

Աստիճան բարձրացնելու օպերատորը `a ** b` բարձրացնում է `a`-ն `b`-ի աստիճան.

Դպրոցական մաթեմատիկայում այն գրում ենք հետևյալ տեսքով a<sup>b</sup>։

Օրինակ՝

```js run
alert( 2 ** 2 ); // 2² = 4
alert( 2 ** 3 ); // 2³ = 8
alert( 2 ** 4 ); // 2⁴ = 16
```

Ինչպես մաթեմատիկայում, այստեղ նույնպես հետևայալ օպերատորը կարող ենք կիրառել ոչ ամբողջ թվերի դեպքում։

Օրինակ՝ ½-ի աստիճանը:

```js run
alert( 4 ** (1/2) ); // 2 (power of 1/2 is the same as a square root)
alert( 8 ** (1/3) ); // 2 (power of 1/3 is the same as a cubic root)
```


## Տողերի միավորումը երկուական +-ով

Եկեք ծանոթանանք JavaScript-ի հնարավորությունների հետ, որոնք հիմքում ընկած է դպրոցական թվաբանությունը։

Սովորաբար, `+` գործողությունը գումարում է թվերը։

Բայց, երբ երկուական `+`-ը կիրառովում է տողերի համար, դա միացնում է դրանք․

```js
let s = "my" + "string";
alert(s); // mystring
```

Նշում, եթե ցանկացած օպրանդ տող է, ապա մյուս օպերանդը նույնպես ձևափոխվում է տողի։

Օրինակ՝

```js run
alert( '1' + 2 ); // "12"
alert( 2 + '1' ); // "21"
```

Կապ չունի այն, որ առաջին օպերանդն է տող, թե երկրորդը․

Դիտարկենք ավելի բարդ օրինակ՝

```js run
alert(2 + 2 + '1' ); // "41", այլ ոչ թե "221"
```

Այստեղ օպերատորները աշխատում են հաջորդաբար։ Առաջին `+`-ը գումարում է երկու թվերը, վարադարձնում է `4`, ապա հաջորդ `+`-ը ավալցանում`1` տողային փոփոխականը, այսպիսով դա նման է հետևյալին `4 + '1' = '41'`.

```js run
alert('1' + 2 + 2); // "122", այլ ոչ թե "14"
```
Այստեղ առաջին օպերանդը տող է, կոմպիլյատորը վերաբերվում է մյուս օպերանդներին նույնպես տող . `2`-ը կմիավորվի `'1'`-ի հետ, այսպիսով դա նման է հետևյալին `'1' + 2 = "12"` և `"12" + 2 = "122"`.

Երկուական `+`-ը միակ օպերատորնե, որը նման կերպ է վարվում տողերի հետ։ Մյուս թվաբանական օպերատորները աշխատում են միայն թվերի հետ և միշտ կերպափոխում են օպերանդները թվերի։

Դիտարկենք հանման և բաժանման ցուցադրությունը․

```js run
alert( 6 - '2' ); // 4, '2'-ը ձևափոխվում է թվի
alert( '6' / '2' ); // 3, երկու օպերանդներնել ձևափոխվում են թվերի
```

## Թվային կերպափոխումներ, ունար +

Գոյություն ունի `+`-ի երկու տեսակ․ երկուական տեսակ, որը մենք կիրառեցինք վերևում և ունար տեսակ։

Ունար գումարում կամ մեկ այլ խոսքով `+` որը կիրառվում է մեկ արժեքների դեպքում, թվերի վրա չի ազդում։ Բայց եթե օպերանդը թիվ չէ, ապա ունար գումարումը այն կերպափոխում է թվի։

Օրինակ՝

```js run
// Թվերի վրա ազդեցություն չի ունենում
let x = 1;
alert( +x ); // 1

let y = -2;
alert( +y ); // -2

*!*
// Կերպափոխում է ոչ թվային արժեքները
alert( +true ); // 1
alert( +"" );   // 0
*/!*
```

Այն իրականում անում է նույնը, ինչ `Number(...)`-ը, բայց կարճ տարբերակով։

Տողերը թվերի կերպափոխելու անհրաժեշտությունը շատ հաճախ է առաջանում։ Օրինակ՝ եթե մենք ստանում ենք դաշտերը HTML ֆորմայից, դրանք սովորաբար տողային տիպի են։ Ի՞նչ կլինի այդ դեպքում դրանց գումարը։

Երկուական գումարումը դրանք կավելացնի իրար ինչպես տող։

```js run
let apples = "2";
let oranges = "3";

alert( apples + oranges ); // "23", երկուական գումարը միացնում է տողերը իրար հետ
```

Եթե մենք ուզում ենք նրանց վերաբերվել որպես թվերի, կարիք կա կերպափոխելու դրանք և կատարել դրանց գումարումը:

```js run
let apples = "2";
let oranges = "3";

*!*
// երկու արժեքները մինչև երկուական գումարմանը մասնակցելը, կերպափոխվում են թվերի
alert( +apples + +oranges ); // 5
*/!*

// երկար տարբերակը
// alert( Number(apples) + Number(oranges) ); // 5
```

Մաթեմատիկական տեսանկյունից, պլյուսների առատությունը կարող է տարօրինակ թվալ։ Բայց ծրագրավորողների տեսանկյունից, հատուկ ոչինչ չկա: ունար պլյուսը կիրառվում է սկզբից, դրանք կերպափոխում են տողերը թվերի, իսկ երկուական պլյուսը գումարում է դրանք։

Ինչու՞ է ունար պլյուսը կիրառվում սկզբից, նախքան երկուականը, դա կախված է *բարձր առաջնահերթություն*.

## Օպերատորների առաջնահերթություն

Եթե արդահայտությունը ունի մեկից ավել օպերատորներ, ապա կատարման հերթականությունը սահմանվում է կախված նրանց *առաջնահերթությունից*, կամ այլ բառով, օպերատորների կանխադրված առաջնահերթ կարգը։

Դպրոցից մենք գիտեն արտահայտությունում բազմապատկման կարգի մասին `1 + 2 * 2` պետք է կատարվի մինչ գումարումը։ Դա հենց առաջնահերթությունն է: Ասում են, որ բազմապատկումը ունի *ավելի բարձր առաջնահերթություն* քան թե գումարումը։

Փակագծերը ավելի առաջնահերթ են քան մյուսները, ուստի, եթե մենք համամիտ չենք առաջնահերթությունից, կարող ենք օգտագործել դրանք, այն փոխելու համար: Օրինակ՝ գրելով `(1 + 2) * 2`.

Կան բազմաթիվ օպերատորներ JavaScript-ում։ Յուրաքանչյուր օպերատոր ունի իր համապատասխան առաջնահերթության համարը: Ավելի մեծ թիվ ունեցողը կատարվում է առաջինը։ Եթե առաջնահերթությունը նույնն է, ապա կատարման հերթականությունը ձախից դեպի աջ է։

Ահա քաղվածքը [precedence table](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence) (դուք պարտավոր չեք հիշել սա, բայց նշեք, որ ունար օպերատորներն ավելի բարձր են, քան համապատասխան երկուականները):

| Առաջնահերթւոյուն | Անվանում | Նշան |
|------------|------|------|
| ... | ... | ... |
| 17 | ունար պլյուս | `+` |
| 17 | ունար ժխտում | `-` |
| 16 | ընդլայնում | `**` |
| 15 | բազմապատկում | `*` |
| 15 | բաժանում | `/` |
| 13 | գումարում | `+` |
| 13 | հանում | `-` |
| ... | ... | ... |
| 3 | վերագրում | `=` |
| ... | ... | ... |

Կարող ենք տեսնել, "ունար պլյուս"-ը ունի `17` գերակայությունը, որը մեծ է քան `13`-ը "գումարում" (երկուական պլյուս)։ Ահա թե ինչու  է, `"+apples + +oranges"` արտահայտությունում, ունար պլյուսը կատարվում նախքան գումարումը։

## Assignment

Let's note that an assignment `=` is also an operator. It is listed in the precedence table with the very low priority of `3`.

That's why, when we assign a variable, like `x = 2 * 2 + 1`, the calculations are done first and then the `=` is evaluated, storing the result in `x`.

```js
let x = 2 * 2 + 1;

alert( x ); // 5
```

### Assignment = returns a value

The fact of `=` being an operator, not a "magical" language construct has an interesting implication.

All operators in JavaScript return a value. That's obvious for `+` and `-`, but also true for `=`.

The call `x = value` writes the `value` into `x` *and then returns it*.

Here's a demo that uses an assignment as part of a more complex expression:

```js run
let a = 1;
let b = 2;

*!*
let c = 3 - (a = b + 1);
*/!*

alert( a ); // 3
alert( c ); // 0
```

In the example above, the result of expression `(a = b + 1)` is the value which was assigned to `a` (that is `3`). It is then used for further evaluations.

Funny code, isn't it? We should understand how it works, because sometimes we see it in JavaScript libraries.

Although, please don't write the code like that. Such tricks definitely don't make code clearer or readable.

### Chaining assignments

Another interesting feature is the ability to chain assignments:

```js run
let a, b, c;

*!*
a = b = c = 2 + 2;
*/!*

alert( a ); // 4
alert( b ); // 4
alert( c ); // 4
```

Chained assignments evaluate from right to left. First, the rightmost expression `2 + 2` is evaluated and then assigned to the variables on the left: `c`, `b` and `a`. At the end, all the variables share a single value.

Once again, for the purposes of readability it's better to split such code into few lines:

```js
c = 2 + 2;
b = c;
a = c;
```
That's easier to read, especially when eye-scanning the code fast.

## Modify-in-place

We often need to apply an operator to a variable and store the new result in that same variable.

For example:

```js
let n = 2;
n = n + 5;
n = n * 2;
```

This notation can be shortened using the operators `+=` and `*=`:

```js run
let n = 2;
n += 5; // now n = 7 (same as n = n + 5)
n *= 2; // now n = 14 (same as n = n * 2)

alert( n ); // 14
```

Short "modify-and-assign" operators exist for all arithmetical and bitwise operators: `/=`, `-=`, etc.

Such operators have the same precedence as a normal assignment, so they run after most other calculations:

```js run
let n = 2;

n *= 3 + 5;

alert( n ); // 16  (right part evaluated first, same as n *= 8)
```

## Increment/decrement

<!-- Can't use -- in title, because the built-in parser turns it into a 'long dash' – -->

Increasing or decreasing a number by one is among the most common numerical operations.

So, there are special operators for it:

- **Increment** `++` increases a variable by 1:

    ```js run no-beautify
    let counter = 2;
    counter++;        // works the same as counter = counter + 1, but is shorter
    alert( counter ); // 3
    ```
- **Decrement** `--` decreases a variable by 1:

    ```js run no-beautify
    let counter = 2;
    counter--;        // works the same as counter = counter - 1, but is shorter
    alert( counter ); // 1
    ```

```warn
Increment/decrement can only be applied to variables. Trying to use it on a value like `5++` will give an error.
```

The operators `++` and `--` can be placed either before or after a variable.

- When the operator goes after the variable, it is in "postfix form": `counter++`.
- The "prefix form" is when the operator goes before the variable: `++counter`.

Both of these statements do the same thing: increase `counter` by `1`.

Is there any difference? Yes, but we can only see it if we use the returned value of `++/--`.

Let's clarify. As we know, all operators return a value. Increment/decrement is no exception. The prefix form returns the new value while the postfix form returns the old value (prior to increment/decrement).

To see the difference, here's an example:

```js run
let counter = 1;
let a = ++counter; // (*)

alert(a); // *!*2*/!*
```

In the line `(*)`, the *prefix* form `++counter` increments `counter` and returns the new value, `2`. So, the `alert` shows `2`.

Now, let's use the postfix form:

```js run
let counter = 1;
let a = counter++; // (*) changed ++counter to counter++

alert(a); // *!*1*/!*
```

In the line `(*)`, the *postfix* form `counter++` also increments `counter` but returns the *old* value (prior to increment). So, the `alert` shows `1`.

To summarize:

- If the result of increment/decrement is not used, there is no difference in which form to use:

    ```js run
    let counter = 0;
    counter++;
    ++counter;
    alert( counter ); // 2, the lines above did the same
    ```
- If we'd like to increase a value *and* immediately use the result of the operator, we need the prefix form:

    ```js run
    let counter = 0;
    alert( ++counter ); // 1
    ```
- If we'd like to increment a value but use its previous value, we need the postfix form:

    ```js run
    let counter = 0;
    alert( counter++ ); // 0
    ```

````smart header="Increment/decrement among other operators"
The operators `++/--` can be used inside expressions as well. Their precedence is higher than most other arithmetical operations.

For instance:

```js run
let counter = 1;
alert( 2 * ++counter ); // 4
```

Compare with:

```js run
let counter = 1;
alert( 2 * counter++ ); // 2, because counter++ returns the "old" value
```

Though technically okay, such notation usually makes code less readable. One line does multiple things -- not good.

While reading code, a fast "vertical" eye-scan can easily miss something like `counter++` and it won't be obvious that the variable increased.

We advise a style of "one line -- one action":

```js run
let counter = 1;
alert( 2 * counter );
counter++;
```
````

## Bitwise operators

Bitwise operators treat arguments as 32-bit integer numbers and work on the level of their binary representation.

These operators are not JavaScript-specific. They are supported in most programming languages.

The list of operators:

- AND ( `&` )
- OR ( `|` )
- XOR ( `^` )
- NOT ( `~` )
- LEFT SHIFT ( `<<` )
- RIGHT SHIFT ( `>>` )
- ZERO-FILL RIGHT SHIFT ( `>>>` )

These operators are used very rarely, when we need to fiddle with numbers on the very lowest (bitwise) level. We won't need these operators any time soon, as web development has little use of them, but in some special areas, such as cryptography, they are useful. You can read the [Bitwise Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#Bitwise) chapter on MDN when a need arises.

## Comma

The comma operator `,` is one of the rarest and most unusual operators. Sometimes, it's used to write shorter code, so we need to know it in order to understand what's going on.

The comma operator allows us to evaluate several expressions, dividing them with a comma `,`. Each of them is evaluated but only the result of the last one is returned.

For example:

```js run
*!*
let a = (1 + 2, 3 + 4);
*/!*

alert( a ); // 7 (the result of 3 + 4)
```

Here, the first expression `1 + 2` is evaluated and its result is thrown away. Then, `3 + 4` is evaluated and returned as the result.

```smart header="Comma has a very low precedence"
Please note that the comma operator has very low precedence, lower than `=`, so parentheses are important in the example above.

Without them: `a = 1 + 2, 3 + 4` evaluates `+` first, summing the numbers into `a = 3, 7`, then the assignment operator `=` assigns `a = 3`, and the rest is ignored. It's like `(a = 1 + 2), 3 + 4`.
```

Why do we need an operator that throws away everything except the last expression?

Sometimes, people use it in more complex constructs to put several actions in one line.

For example:

```js
// three operations in one line
for (*!*a = 1, b = 3, c = a * b*/!*; a < 10; a++) {
 ...
}
```

Such tricks are used in many JavaScript frameworks. That's why we're mentioning them. But usually they don't improve code readability so we should think well before using them.
