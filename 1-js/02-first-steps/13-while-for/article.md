# Ցիկլեր․ while և for

Հաճախ մենք կարիք ենք ունենում կրկնել ինչ֊որ գործողությունների հետթականություն։

Օրինակ․ տպել իրար հետևից ցուցակի մեջ գտնվող ապրանքները, կամ ուղղակի աշխակատցնել նույն կոդը 1֊ից 10 բոլոր թվերի համար։

*Ցիկլերը* նույն կոդը մի քանի անգամ կրկնելու հնարավորություն են տալիս։

## "while" ցիկլը

`while` ցիկլը ունի հետևյալ գրելաձևը․

```js
while (condition) {
  // կոդը
  // որին նաև ասում են "ցիկլի մարմին" ("loop body")
}
```

Քանի դեռ `condition`֊ը (պայմանը) ճշմարիտ է, `կոդը` ցիկլի մարմնի ներսում կկատարվի։

Օրինակի համար, ներքևի ցիկլը կարտածի `i`, քանի դեռ `i < 3`․

```js run
let i = 0;
while (i < 3) { // ցույց կտա 0, հետո 1, հետո 2
  alert( i );
  i++;
}
```

Ցիկլի մարմնի մի կատարումը անվանում են *իտերացիա* (*an iteration*): Ցիկլը վերևի օրինակում կատարում է երեք իտերացիա։

Եթե չլիներ `i++` գործողությունը վերևի օրինակում, ապա ցիկլը կկրկնվեր (տեսականորեն) անվերջ։ Պրակտիկայում, դիտարկիչը (browser) կտրամադրի տարբեր գործիքներ, որոնց միջոցով կկարողանանք կանգնեցնել այդպիսի ցիկլկերը, և սերվերում (server-side) կիրառվող JavaScript֊ում կարող ենք սպանել (kill) այդ պրոցեսը։

Կամայական արտահայտություն կամ փոփոխական կարող է լինել ցիկլի պայման։ Պայմանը հաշվվում և ձևափոխվում է տրամաբանական տիպի `while`֊ի կողմից։

Օրինակի համար, `while (i != 0)` արտահայտության կարճ գրելաձևը կլինի `while (i)`:

```js run
let i = 3;
*!*
while (i) { // երբ i֊ն դառնա 0, պայմանը կդառնա սխալական, և ցիկլը կանգ կառնի
*/!*
  alert( i );
  i--;
}
```

````smart header="Ձևավոր փակագծերը պարտադիր չեն մեկ տողանի մարմնի համար"
Եթե ցիկլի մարմինը ունի ընդամենը մեկ արտահայտություն (statement), ապա կարող ենք բաց թողնել ձևավոր փակագծերը `{…}`․

```js run
let i = 3;
*!*
while (i) alert(i--);
*/!*
```
````

## "do..while" ցիկլը

Պայմանի ստուգումը կարելի է տեղափոխել ցիկլի մարմնի *ներքևը* օգտագործելով `do..while` գերլաձևը․

```js
do {
  // ցիկլի մարմին
} while (condition);
```

Ցիկլը սկզբում կաշխատացնի մարմնը, ապա կստուգի պայմանը, և քանի դեռ այն ճշմարիտ է, այն կաշխատացնի մարմինը նորից ու նորից։

Օրինակ․

```js run
let i = 0;
do {
  alert( i );
  i++;
} while (i < 3);
```

Այս գրելաձևը պետք է օգտագործվի միայն այն դեպքում, երբ ցանկանում եք, որ ցիկլի մարմինը աշխատի **առնվազն մեկ անգամ** անկախ պայմանի ճշմարիտ կամ սխալական լինելու փաստից։ Սովորաբար մյուս տեսքը ավելի նախընտրելի է․ `while(…) {…}`։

## "for" ցիկլը

`for` ցիլկը ավելի կոմպլեքս է, բայց այն ամենից շատ կիրառվող ցիկլն է։

Այն ունի հետևյալ տեսքը․

```js
for (begin; condition; step) {
  // ... ցիկլի մարմին ...
}
```

Եկեք ուսումնասիրենք այդ մասեիը օրինակի վրա։ Ներքևի ցիկլը կատարում է `alert(i)` հրամանը `i`֊ն `0`֊ից մինչև `3`֊ը ոչ ներառյալ:

```js run
for (let i = 0; i < 3; i++) { // ցույց կտա 0, հետո 1, հետո 2
  alert(i);
}
```

Դիտարկենք `for`֊ը մաս֊առ֊մաս․

| մաս  |          |                                                                            |
|-------|----------|----------------------------------------------------------------------------|
| սկիզբ | `i = 0`    | Կատարվում է, երբ մտնում ենք ցիկլ։                                      |
| պայման | `i < 3`| Ստուգվում է ցիկլի ամեն իտերացիայից առաջ։ Եթե այն սխալ է, ապա ցիկլը կանգնեցվում է։              |
| մարմին | `alert(i)`| Աշխատում է այնքան ժամանակ, քանի դեռ պայմանը ճշմարիտ է։                         |
| քայլ| `i++`      | Կատարվում է մարմնի կատարումից հետո, ամեն իտերացիայից ժամանակ։ |

Ընդհանուր դեպքում ալգորիթմը աշխատում է հետևյալ կերպ․

```
Աշխատացնել *սկիզբ*
→ (եթե *պայման* → կատարել *մարմին* և աշխատացնել *քայլ*)
→ (եթե *պայման* → կատարել *մարմին* և աշխատացնել *քայլ*)
→ (եթե *պայման* → կատարել *մարմին* և աշխատացնել *քայլ*)
→ ...
```

Այսինքն, `սկիզբ`֊ը կատարվում է մեկ անգամ, և հետո սկսվում են իտերացիաները․ ամեն `պայման`֊ի ստուգումից հետո, `մարմին`֊ը և `քայլ`֊ը կատարվում են։

Եթե ցիկլերի թեման նոր է ձեր համար, ապա օգտակար կլինի հետ գնալ օրինակներին և քայլ֊առ֊քայլ գրառել դրանց կատարման ընթացքները թղթի վրա։

Ահա թե ինչ է տեղի ունենում կոնկրետ մեր օրինակի դեպքում․

```js
// for (let i = 0; i < 3; i++) alert(i)

// աշխատացնել սկիզբը
let i = 0
// եթե պայման → կատարել մարմինը և աշխատացնել քայլը
if (i < 3) { alert(i); i++ }
// եթե պայման → կատարել մարմինը և աշխատացնել քայլը
if (i < 3) { alert(i); i++ }
// եթե պայման → կատարել մարմինը և աշխատացնել քայլը
if (i < 3) { alert(i); i++ }
// ...ավարտ, քանի որ i == 3
```

````smart header="Փոփոխականի ներկառուցված հայտարարում"
Here, the "counter" variable `i` is declared right in the loop. This is called an "inline" variable declaration. Such variables are visible only inside the loop.

```js run
for (*!*let*/!* i = 0; i < 3; i++) {
  alert(i); // 0, 1, 2
}
alert(i); // error, no such variable
```

Instead of defining a variable, we could use an existing one:

```js run
let i = 0;

for (i = 0; i < 3; i++) { // use an existing variable
  alert(i); // 0, 1, 2
}

alert(i); // 3, visible, because declared outside of the loop
```

````


### Skipping parts

Any part of `for` can be skipped.

For example, we can omit `begin` if we don't need to do anything at the loop start.

Like here:

```js run
let i = 0; // we have i already declared and assigned

for (; i < 3; i++) { // no need for "begin"
  alert( i ); // 0, 1, 2
}
```

We can also remove the `step` part:

```js run
let i = 0;

for (; i < 3;) {
  alert( i++ );
}
```

This makes the loop identical to `while (i < 3)`.

We can actually remove everything, creating an infinite loop:

```js
for (;;) {
  // repeats without limits
}
```

Please note that the two `for` semicolons `;` must be present. Otherwise, there would be a syntax error.

## Breaking the loop

Normally, a loop exits when its condition becomes falsy.

But we can force the exit at any time using the special `break` directive.

For example, the loop below asks the user for a series of numbers, "breaking" when no number is entered:

```js run
let sum = 0;

while (true) {

  let value = +prompt("Enter a number", '');

*!*
  if (!value) break; // (*)
*/!*

  sum += value;

}
alert( 'Sum: ' + sum );
```

The `break` directive is activated at the line `(*)` if the user enters an empty line or cancels the input. It stops the loop immediately, passing control to the first line after the loop. Namely, `alert`.

The combination "infinite loop + `break` as needed" is great for situations when a loop's condition must be checked not in the beginning or end of the loop, but in the middle or even in several places of its body.

## Continue to the next iteration [#continue]

The `continue` directive is a "lighter version" of `break`. It doesn't stop the whole loop. Instead, it stops the current iteration and forces the loop to start a new one (if the condition allows).

We can use it if we're done with the current iteration and would like to move on to the next one.

The loop below uses `continue` to output only odd values:

```js run no-beautify
for (let i = 0; i < 10; i++) {

  // if true, skip the remaining part of the body
  *!*if (i % 2 == 0) continue;*/!*

  alert(i); // 1, then 3, 5, 7, 9
}
```

For even values of `i`, the `continue` directive stops executing the body and passes control to the next iteration of `for` (with the next number). So the `alert` is only called for odd values.

````smart header="The `continue` directive helps decrease nesting"
A loop that shows odd values could look like this:

```js run
for (let i = 0; i < 10; i++) {

  if (i % 2) {
    alert( i );
  }

}
```

From a technical point of view, this is identical to the example above. Surely, we can just wrap the code in an `if` block instead of using `continue`.

But as a side-effect, this created one more level of nesting (the `alert` call inside the curly braces). If the code inside of `if` is longer than a few lines, that may decrease the overall readability.
````

````warn header="No `break/continue` to the right side of '?'"
Please note that syntax constructs that are not expressions cannot be used with the ternary operator `?`. In particular, directives such as `break/continue` aren't allowed there.

For example, if we take this code:

```js
if (i > 5) {
  alert(i);
} else {
  continue;
}
```

...and rewrite it using a question mark:


```js no-beautify
(i > 5) ? alert(i) : *!*continue*/!*; // continue isn't allowed here
```

...it stops working: there's a syntax error.

This is just another reason not to use the question mark operator `?` instead of `if`.
````

## Labels for break/continue

Sometimes we need to break out from multiple nested loops at once.

For example, in the code below we loop over `i` and `j`, prompting for the coordinates `(i, j)` from `(0,0)` to `(2,2)`:

```js run no-beautify
for (let i = 0; i < 3; i++) {

  for (let j = 0; j < 3; j++) {

    let input = prompt(`Value at coords (${i},${j})`, '');

    // what if we want to exit from here to Done (below)?
  }
}

alert('Done!');
```

We need a way to stop the process if the user cancels the input.

The ordinary `break` after `input` would only break the inner loop. That's not sufficient -- labels, come to the rescue!

A *label* is an identifier with a colon before a loop:
```js
labelName: for (...) {
  ...
}
```

The `break <labelName>` statement in the loop below breaks out to the label:

```js run no-beautify
*!*outer:*/!* for (let i = 0; i < 3; i++) {

  for (let j = 0; j < 3; j++) {

    let input = prompt(`Value at coords (${i},${j})`, '');

    // if an empty string or canceled, then break out of both loops
    if (!input) *!*break outer*/!*; // (*)

    // do something with the value...
  }
}
alert('Done!');
```

In the code above, `break outer` looks upwards for the label named `outer` and breaks out of that loop.

So the control goes straight from `(*)` to `alert('Done!')`.

We can also move the label onto a separate line:

```js no-beautify
outer:
for (let i = 0; i < 3; i++) { ... }
```

The `continue` directive can also be used with a label. In this case, code execution jumps to the next iteration of the labeled loop.

````warn header="Labels do not allow to \"jump\" anywhere"
Labels do not allow us to jump into an arbitrary place in the code.

For example, it is impossible to do this:
```js
break label; // jump to the label below (doesn't work)

label: for (...)
```

A `break` directive must be inside a code block. Technically, any labelled code block will do, e.g.:
```js
label: {
  // ...
  break label; // works
  // ...
}
```

...Although, 99.9% of the time `break` is used inside loops, as we've seen in the examples above.

A `continue` is only possible from inside a loop.
````

## Summary

We covered 3 types of loops:

- `while` -- The condition is checked before each iteration.
- `do..while` -- The condition is checked after each iteration.
- `for (;;)` -- The condition is checked before each iteration, additional settings available.

To make an "infinite" loop, usually the `while(true)` construct is used. Such a loop, just like any other, can be stopped with the `break` directive.

If we don't want to do anything in the current iteration and would like to forward to the next one, we can use the `continue` directive.

`break/continue` support labels before the loop. A label is the only way for `break/continue` to escape a nested loop to go to an outer one.
