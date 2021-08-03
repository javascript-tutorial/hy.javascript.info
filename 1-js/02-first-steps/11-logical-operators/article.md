# Տրամաբանական օպերատորներ (Logical operators)

JavaScript-ում կան չորս տրամաբանական օպերատորներ՝ `||` (ԿԱՄ), `&&` (ԵՎ), `!` (ՈՉ), `??` (Null-ի հետ համակցման). Այստեղ մենք կծանոթանանք առաջին երեքին։ `??` օպերատորին կարող եք ծանոթանալ հաջորդ հոդվածում։

Չնայած նրանք անվանվում են "տրամաբանական", նրանք կարող են կիրառվել կամայական(տարբերվող տրամաբանական տիպից) տիպի վրա։ Նրանց արդյունքը նույպես կարող է լինել կամայական տիպի։

Եկեք դիտարկենք ավելի մանրամասն։

## || (ԿԱՄ)

"ԿԱՄ" օպերատորը ներկայացվում է երկու ուղղահայաց գիծ նշանների միջոցով։

```js
result = a || b
```

Կլասիկ ծրագրավորման մեջ տրամաբանական ԿԱՄ օպերատորը կիրառվում է միայն տրամաբանական արժեքների վրա։ Եթե նրա արգումենտներից մեկը ճշմարի `true` է, ապա այն վերադարձնում է `true`, հակառակ դեպքում՝ `false`։

JavaScript֊ում այս օպերատորը ավելի ճկուն և հզոր է։ Բայց սկզում եկեք տեսնենք, թե ինչ է կատարվում տրամաբանական տիպերի հետ։

Կան չորս տրամաբանական կոմբինայիաներ․

```js run
alert(true || true) // true
alert(false || true) // true
alert(true || false) // true
alert(false || false) // false
```

Ինչպես տեսնում ենք արդյունքը միշտ ճիշտ(`true`) է, բացի այն դեպքից, երբ երկու օպերանդներն էլ սխալ(`false`) են։

If an operand is not a boolean, it's converted to a boolean for the evaluation.

Օրինակ `1`֊ը մշակվում է որպես `true`, `0`֊ն՝ `false`․

```js run
if (1 || 0) {
  // աշխատում է ինչպես if( true || false )
  alert('Ճշմարիտ է!')
}
```

Շատ հաճախ ԿԱՄ `||` օպերատորը օգտագործվում է `if` պայմանի օպերատորի հետ՝ ստուգելու համար արդյոք ճիշտ(`true`) է տրված պայմաններից _գոնե մեկը_։

Օրինակ․

```js run
let hour = 9;

*!*
if (hour < 10 || hour > 18) {
*/!*
  alert('Գրասենյակը փակ է։');
}
```

Մենք կարող ենք ստուգել ավելի շատ պայմաններ․

```js run
let hour = 12
let isWeekend = true

if (hour < 10 || hour > 18 || isWeekend) {
  alert('Գրասենյակը փակ է։') // քանի որ շաբաթ կամ կիրակի է (weekend)
}
```

## ԿԱՄ "||"֊ը գտնում է առաջին ճշմարիտ արժեքը [#or-finds-the-first-truthy-value]

Վերոնշյալ տրամաբանությունը ստանդարտ է ԿԱՄ֊ի համար։ Հիմա եկեք դիտարկենք JavaScript֊ի "հավելյալ" հատկությունները։

Ընդլայնված ալգորիթմը աշխատում է հետևյալ կերպ։

Տրված են մի քանի ԿԱՄ֊ով կապված արժեքներ․

```js
result = value1 || value2 || value3
```

ԿԱՄ `||` օպերատորը կատարում է հետևյալ քայլերը․

- Հաշվում է օպերանդների արժեքները ձախից աջ։
- Ամեն օպերանդի արժեք փոխակերպում է տրամաբանական տիպի։ Եթե արդյունքը `true` է այն կանգ է առնում և վերադարձնում այդ օպերանդի օրիգինալ արժեքը։
- Եթե բոլոր օպերանդները հաշվվում են, և բոլորի արժեքը `false` է լինում, ապա վերադարձնում է վերջին օպերանդի արժեքը։

Արժեքը վերադարձվում է իր օրիգինալ վիճակում, առանց փոխարկման(conversion)։

Այլ կերպ ասած, ԿԱՄ `||`֊երից կազմված շղթան վերադարձնում է առաջին ճշմարիտ արժեքը, կամ վերջինը, եթե չկան ճշմարիտ արժեքներ։

Օրինակ․

```js run
alert(1 || 0) // 1 (1֊ը ճշմարիտ է)

alert(null || 1) // 1 (1֊ը առաջին ճշմարիտ արժեքն է)
alert(null || 0 || 1) // 1 (առաջին ճշմարիտ արժեքը)

alert(undefined || null || 0) // 0 (քանի որ բոլորը սխալական(falsy) են, վերադարձնում է վերջինը)
```

Սա հնարավորություն է տալիս կիրառել օպերատորը "մաքուր, ստանդարտ, միայն տրամաբանական ԿԱՄ"֊ի շրջանակներից դուրս։

1. **Առաջին ճշմարիտ արժեքի ստացումը փոփոխականների կամ արտահայտությունների ցուցակից։**

   Օրինակի, ունենք `firstName`, `lastName` և `nickName` փոփոխականները, բոլորը ըստ ցանկության կարող են ստանալ սխալական կամ `undefined` արժեքներ։

   Եկեք օգտագործենք ԿԱՄ `||`֊ը ընտրելու համար մեկը որը ունի արժեք(ճշմարիտ) և ցույց տանք այն (կամ `"Anonymous"` եթե այդպիսի արժեք չի գտնվել):

   ```js run
   let firstName = "";
   let lastName = "";
   let nickName = "SuperCoder";

   *!*
   alert( firstName || lastName || nickName || "Anonymous"); // SuperCoder
   */!*
   ```

   Եթե բոլոր փոփոխականները լինեին սխալական, ապա կտեսնեինք `"Anonymous"`։

2. **Կրճատ հաշվարկ (Short-circuit evaluation)։**

   ԿԱՄ `||`֊ի մեկ այլ հատկությունը այսպես կոչված "կրճատ հաշվարկ"֊ի հատկությունն է։

   Դա նշանակում է, որ `||`֊ը կատարում է իր արգումենտների հաշվարկը և փոխակերպումը տրամաբանական տիպի մինչև առաջին ճշմարիտ արժեքին հանդիպելը, ապա այդ արժեքը միանգամից վերադարձվում է, առանց նույնիսկ հաջորդ արգումենտներին նայելու։

   Այս հատկության կարևորությունն ակնհայտ է դառնում, եթե օպերանդը պարզապես արժեք չէ, այլ ինչ֊որ արտահայտություն՝ կողմնակի ազդեցությամբ, օրինակ փոփոխականի վերագրում կամ ֆունկցիայի կանչ։

   Ներքևի օրինակում միայն երկրորդ նամակը կերևա էկրանին․

   ```js run no-beautify
   *!*true*/!* || alert("չի երևա");
   *!*false*/!* || alert("կերևա");
   ```

   Առաջին տողում ԿԱՄ `||` օպերատորը անմիջապես դադարեցնում է հաշվարկը հենց հանդիպում է `true` արժեքին, այդ պատճառով `alert`֊ը չի կանչվում։

   Հաճախ ծրագրավորողները օգտագործում են այս հատկությունը այն դեպքում, երբ անհրաժեշտ է կատարել հրամանները(execute commands) այն և միայն այն դեպքում, երբ ձախ կողմի գրված պայմանը սխալական է։

## && (AND)

The AND operator is represented with two ampersands `&&`:

```js
result = a && b
```

In classical programming, AND returns `true` if both operands are truthy and `false` otherwise:

```js run
alert(true && true) // true
alert(false && true) // false
alert(true && false) // false
alert(false && false) // false
```

An example with `if`:

```js run
let hour = 12
let minute = 30

if (hour == 12 && minute == 30) {
  alert('The time is 12:30')
}
```

Just as with OR, any value is allowed as an operand of AND:

```js run
if (1 && 0) {
  // evaluated as true && false
  alert("won't work, because the result is falsy")
}
```

## AND "&&" finds the first falsy value

Given multiple AND'ed values:

```js
result = value1 && value2 && value3
```

The AND `&&` operator does the following:

- Evaluates operands from left to right.
- For each operand, converts it to a boolean. If the result is `false`, stops and returns the original value of that operand.
- If all operands have been evaluated (i.e. all were truthy), returns the last operand.

In other words, AND returns the first falsy value or the last value if none were found.

The rules above are similar to OR. The difference is that AND returns the first _falsy_ value while OR returns the first _truthy_ one.

Examples:

```js run
// if the first operand is truthy,
// AND returns the second operand:
alert(1 && 0) // 0
alert(1 && 5) // 5

// if the first operand is falsy,
// AND returns it. The second operand is ignored
alert(null && 5) // null
alert(0 && 'no matter what') // 0
```

We can also pass several values in a row. See how the first falsy one is returned:

```js run
alert(1 && 2 && null && 3) // null
```

When all values are truthy, the last value is returned:

```js run
alert(1 && 2 && 3) // 3, the last one
```

````smart header="Precedence of AND `&&`is higher than OR`||`" The precedence of AND `&&`operator is higher than OR`||`.

So the code `a && b || c && d` is essentially the same as if the `&&` expressions were in parentheses: `(a && b) || (c && d)`.

`````

````warn header="Don't replace `if` with `||` or `&&`"
Sometimes, people use the AND `&&` operator as a "shorter way to write `if`".

For instance:

```js run
let x = 1;

(x > 0) && alert( 'Greater than zero!' );
```

The action in the right part of `&&` would execute only if the evaluation reaches it. That is, only if `(x > 0)` is true.

So we basically have an analogue for:

```js run
let x = 1;

if (x > 0) alert( 'Greater than zero!' );
```

Although, the variant with `&&` appears shorter, `if` is more obvious and tends to be a little bit more readable. So we recommend using every construct for its purpose: use `if` if we want `if` and use `&&` if we want AND.
`````

## ! (NOT)

The boolean NOT operator is represented with an exclamation sign `!`.

The syntax is pretty simple:

```js
result = !value
```

The operator accepts a single argument and does the following:

1. Converts the operand to boolean type: `true/false`.
2. Returns the inverse value.

For instance:

```js run
alert(!true) // false
alert(!0) // true
```

A double NOT `!!` is sometimes used for converting a value to boolean type:

```js run
alert(!!'non-empty string') // true
alert(!!null) // false
```

That is, the first NOT converts the value to boolean and returns the inverse, and the second NOT inverses it again. In the end, we have a plain value-to-boolean conversion.

There's a little more verbose way to do the same thing -- a built-in `Boolean` function:

```js run
alert(Boolean('non-empty string')) // true
alert(Boolean(null)) // false
```

The precedence of NOT `!` is the highest of all logical operators, so it always executes first, before `&&` or `||`.
