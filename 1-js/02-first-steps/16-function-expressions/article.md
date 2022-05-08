# Function Expression

Ֆունկցիան JavaScript-ում «լեզվի կախարդական կառուցվածք» չէ, բայց արժեքի հատուկ տեսակ է:

Այն շարահյուսությունը, որ մինչ այս օգտագործել ենք, կոչվում է *Function Declaration* (Ֆունկցիայի Հայտարարություն):

```js
function sayHi() {
  alert( "Ողջույն" );
}
```

Կա նաև այլ շարահյուսություն, որը կոչվում է *Function Expression* (Ֆունկցիայի Արտահայտություն):

Դա մեզ թույլ է տալիս ստեղծել նոր ֆունկցիա ցանկացած արտահայտության մեջտեղում:

Օրինակ.

```js
let sayHi = function() {
  alert( "Ողջույն" );
};
```

Այստեղ մենք կարող ենք տեսնել, որ `sayHi` փոփոխականը ստանում է արժեք՝ նոր ֆունկցիա, որը ստեղծվել է այսպես՝ `function() { alert("Ողջույն"); }`:

Քանի որ ֆունկցիայի ստեղծումը տեղի է ունենում վերագրման արտահայտության համատեքստում (`=` նշանի աջ կողմում), ապա սա *Function Expression* է:

Նկատի ունեցեք, որ `function` հիմնաբառից հետո չկա անվանում: Անվան բացթողումը թույլատրելի է Ֆունկցիայի Արտահայտությունների համար:

Այստեղ մենք անմիջապես վերագրում ենք այն փոփոխականին, ուստի այս կոդի նմուշների իմաստը նույնն է. «ստեղծել ֆունկցիա և տեղադրել այն `sayHi` փոփոխականում»:

Ավելի առաջադեմ իրավիճակներում, որոնց մենք հետո կհանդիպենք, ֆունկցիան կարող է ստեղծվել և անմիջապես կանչվել կամ պլանավորվել ավելի ուշ կատարման համար, ոչ մի տեղ չպահվել, այդպիսով մնալով անանուն:

## Ֆունկցիան արժեք է

Եկեք կրկնենք. անկախ նրանից, թե ինչպես է ստեղծվում ֆունկցիան, այն արժեք է: Վերոնշյալ երկու օրինակներն էլ պահում են ֆունկցիան `sayHi` փոփոխականում:

Մենք կարող ենք նույնիսկ տպել այդ արժեքը՝ օգտագործելով `alert`.

```js run
function sayHi() {
  alert( "Ողջույն" );
}

*!*
alert( sayHi ); // ցուցադրում է ֆունկցիայի կոդը
*/!*
```

Նկատի ունեցեք, որ վերջին տողը չի կատարում ֆունկցիան, որովհետև `sayHi`-ից հետո չկան փակագծեր: Կան ծրագրավորման լեզուներ, որտեղ ֆունկցիայի անվան ցանկացած հիշատակում հանգեցնում է դրա կատարմանը, բայց JavaScript-ը այդպիսին չէ։

JavaScript-ում ֆունկցիան արժեք է, այնպես որ մենք կարող ենք դրան վերաբերվել որպես արժեքի: Վերոնշյալ կոդը ցույց է տալիս իր տողային ներկայացումը, որը սկզբնական կոդը է:

Անշուշտ, ֆունկցիան հատուկ արժեք է, այն իմաստով, որ մենք կարող ենք այն կանչել որպես `sayHi()`:

Բայց դա դեռևս արժեք է: Այսպիսով, մենք կարող ենք աշխատել դրա հետ, ինչպես այլ տեսակի արժեքների հետ:

Մենք կարող ենք պատճենել ֆունկցիան մեկ այլ փոփոխականում.

```js run no-beautify
function sayHi() {     // (1) ստեղծել
  alert( "Ողջույն" );
}

let func = sayHi;      // (2) պատճենել

func(); // Ողջույն     // (3) կատարել կրկնօրինակը (սա աշխատում է)
sayHi(); // Ողջույն    //     սա նույնպես դեռ աշխատում է (ինչու ոչ)
```

Ահա մանրամասն, թե ինչ է տեղի ունենում վերևում.

1. Ֆունկցիայի Հայտարարությունը `(1)` ստեղծում է ֆունկցիա և տեղադրում այն `sayHi` փոփոխականում:
2. Տող `(2)`-ը պատճենում է այն `func` փոփոխականում: Կրկին նկատի ունեցեք. `sayHi`-ից հետո չկան փակագծեր: Եթե լինեին, ապա `func = sayHi()` կվերագրեր `sayHi()`-ի *կանչվելու արդյունքը* `func`-ին, այլ ոչ թե հենց `sayHi` *ֆունկցիան*:
3. Այժմ երկու եղանակով էլ ֆունկցիան կարող է կանչվել՝ `sayHi()` և `func()`:

Մենք `sayHi` հայտարարելու համար կարող էինք նաև օգտագործել Ֆունկցիայի Արտահայտություն՝ առաջին տողում.

```js
let sayHi = function() { // (1) ստեղծել
  alert( "Ողջույն" );
};

let func = sayHi;
// ...
```

Ամեն ինչ նույն կերպ կաշխատի:


````smart header="Ինչո՞ւ է վերջում կետ-ստորակետ:"
Կարող եք զարմանալ, թե ինչու Ֆունկցիայի Արտահայտությունը վերջում ունի կետ-ստորակետ `;`, բայց Ֆունկցիայի Հայտարարությունը չունի.

```js
function sayHi() {
  // ...
}

let sayHi = function() {
  // ...
}*!*;*/!*
```

Պատասխանը պարզ է. Ֆունկցիայի Արտահայտությունը ստեղծվել է այստեղ որպես `function(…) {…}` վերագրման հայտարարության ներսում. `let sayHi = …;` (statement): Կետ-ստորակետը `;` խորհուրդ է տրվում հայտարարության վերջում, դա ֆունկցիայի շարահյուսության մաս չէ:

Կետ-ստորակետը կարող է լինել ավելի պարզ վերագրման դեպքում, ինչպիսին է `let sayHi = 5;`, այն առկա է նաև ֆունկցիա վերագրելու դեպքում:
````

## Հետկանչ ֆունկցիաներ

Դիտարկենք ֆունկցիաները որպես արժեքներ փոխանցելու և ֆունկցիաների արտահայտություններ օգտագործելու ավելի շատ օրինակներ:

Մենք կգրենք ֆունկցիա `ask(question, yes, no)` երեք պարամետրով:

`question`
: Հարցի տեքստը

`yes`
: Կատարման համար ֆունկցիա, եթե պատասխանը «Դրական» է

`no`
: Կատարման համար ֆունկցիա, եթե պատասխանը «Բացասական» է

Ֆունկցիան պետք է հարցնի `question` և, կախված օգտատիրոջ պատասխանից, կանչի `yes()` կամ `no()`.

```js run
*!*
function ask(question, yes, no) {
  if (confirm(question)) yes()
  else no();
}
*/!*

function showOk() {
  alert( "Դուք համաձայնեցիք:" );
}

function showCancel() {
  alert( "Դուք չեղարկեցիք կատարումը։" );
}

// օգտագործումը. showOk և showCancel ֆունկցիաները փոխանցվում են ask ֆունկցիային որպես արգումենտներ
ask("Դուք համաձա՞յն եք:", showOk, showCancel);
```

Գործնականում նման ֆունկցիաները բավականին օգտակար են: Հիմնական տարբերությունը «իրական կյանքով» `ask`-ի և վերոնշյալ օրինակի միջև այն է, որ «իրական կյանքով» ֆունկցիաները օգտագործում են ավելի բարդ ուղիներ օգտատիրոջ հետ փոխազդելու համար, քան պարզ `confirm`-ը: Բրաուզերում նման ֆունկցիաները սովորաբար նկարում են գեղեցիկ տեսք ունեցող հարցերի պատուհան: Բայց դա այլ պատմություն է:

**`ask` ֆունկցիայի `showOk` և `showCancel` արգումենտները կոչվում են *callback functions* (հետկանչ ֆունկցիաներ) կամ պարզապես *callbacks* (հետկանչեր):**

Գաղափարն այն է, որ մենք փոխանցում ենք ֆունկցիա և ակնկալում, որ այն հետագայում «հետ կկանչվի» անհրաժեշտության դեպքում: Մեր պարագայում `showOk`-ը դառնում է հետկանչ «դրական» պատասխանի համար, իսկ `showCancel`-ը՝ «բացասական» պատասխանի համար:

Մենք կարող ենք օգտագործել Ֆունկցիայի Արտահայտություն՝ նույն ֆունկցիան շատ ավելի հակիրճ գրելու համար.

```js run no-beautify
function ask(question, yes, no) {
  if (confirm(question)) yes()
  else no();
}

*!*
ask(
  "Դուք համաձա՞յն եք:",
  function() { alert("Դուք համաձայնեցիք:"); },
  function() { alert("Դուք չեղարկեցիք կատարումը։"); }
);
*/!*
```

Այստեղ ֆունկցիաները ճշգրիտ են հայտարարված `ask(...)` կանչի ներսում: Նրանք չունեն անվանում, ուստի կոչվում են *anonymous* (անանուն): Նման ֆունկցիաները հասանելի չեն `ask`-ից դուրս (քանի որ դրանք վերագրված չեն փոփոխականներին), բայց դա հենց այն է, ինչ մենք ուզում ենք այստեղ:

Շատ բնական է, որ նմանատիպ կոդ է հայտնվում մեր սքրիփթներում, այն JavaScript-ի ոգով է:

```smart header="Ֆունկցիան արժեք է, որը ներկայացնում է «գործողություն»"
Սովորական արժեքները, ինչպիսիք են տողերը կամ թվերը, ներկայացնում են *տվյալներ*:

Ֆունկցիան կարող է ընկալվել որպես *գործողություն*։

Մենք կարող ենք այն փոխանցել փոփոխականների միջև և գործարկել, երբ կցանկանանք:
```


## Function Expression vs Function Declaration

Let's formulate the key differences between Function Declarations and Expressions.

First, the syntax: how to differentiate between them in the code.

- *Function Declaration:* a function, declared as a separate statement, in the main code flow.

    ```js
    // Function Declaration
    function sum(a, b) {
      return a + b;
    }
    ```
- *Function Expression:* a function, created inside an expression or inside another syntax construct. Here, the function is created at the right side of the "assignment expression" `=`:

    ```js
    // Function Expression
    let sum = function(a, b) {
      return a + b;
    };
    ```

The more subtle difference is *when* a function is created by the JavaScript engine.

**A Function Expression is created when the execution reaches it and is usable only from that moment.**

Once the execution flow passes to the right side of the assignment `let sum = function…` -- here we go, the function is created and can be used (assigned, called, etc. ) from now on.

Function Declarations are different.

**A Function Declaration can be called earlier than it is defined.**

For example, a global Function Declaration is visible in the whole script, no matter where it is.

That's due to internal algorithms. When JavaScript prepares to run the script, it first looks for global Function Declarations in it and creates the functions. We can think of it as an "initialization stage".

And after all Function Declarations are processed, the code is executed. So it has access to these functions.

For example, this works:

```js run refresh untrusted
*!*
sayHi("John"); // Hello, John
*/!*

function sayHi(name) {
  alert( `Hello, ${name}` );
}
```

The Function Declaration `sayHi` is created when JavaScript is preparing to start the script and is visible everywhere in it.

...If it were a Function Expression, then it wouldn't work:

```js run refresh untrusted
*!*
sayHi("John"); // error!
*/!*

let sayHi = function(name) {  // (*) no magic any more
  alert( `Hello, ${name}` );
};
```

Function Expressions are created when the execution reaches them. That would happen only in the line `(*)`. Too late.

Another special feature of Function Declarations is their block scope.

**In strict mode, when a Function Declaration is within a code block, it's visible everywhere inside that block. But not outside of it.**

For instance, let's imagine that we need to declare a function `welcome()` depending on the `age` variable that we get during runtime. And then we plan to use it some time later.

If we use Function Declaration, it won't work as intended:

```js run
let age = prompt("What is your age?", 18);

// conditionally declare a function
if (age < 18) {

  function welcome() {
    alert("Hello!");
  }

} else {

  function welcome() {
    alert("Greetings!");
  }

}

// ...use it later
*!*
welcome(); // Error: welcome is not defined
*/!*
```

That's because a Function Declaration is only visible inside the code block in which it resides.

Here's another example:

```js run
let age = 16; // take 16 as an example

if (age < 18) {
*!*
  welcome();               // \   (runs)
*/!*
                           //  |
  function welcome() {     //  |  
    alert("Hello!");       //  |  Function Declaration is available
  }                        //  |  everywhere in the block where it's declared
                           //  |
*!*
  welcome();               // /   (runs)
*/!*

} else {

  function welcome() {    
    alert("Greetings!");
  }
}

// Here we're out of curly braces,
// so we can not see Function Declarations made inside of them.

*!*
welcome(); // Error: welcome is not defined
*/!*
```

What can we do to make `welcome` visible outside of `if`?

The correct approach would be to use a Function Expression and assign `welcome` to the variable that is declared outside of `if` and has the proper visibility.

This code works as intended:

```js run
let age = prompt("What is your age?", 18);

let welcome;

if (age < 18) {

  welcome = function() {
    alert("Hello!");
  };

} else {

  welcome = function() {
    alert("Greetings!");
  };

}

*!*
welcome(); // ok now
*/!*
```

Or we could simplify it even further using a question mark operator `?`:

```js run
let age = prompt("What is your age?", 18);

let welcome = (age < 18) ?
  function() { alert("Hello!"); } :
  function() { alert("Greetings!"); };

*!*
welcome(); // ok now
*/!*
```


```smart header="When to choose Function Declaration versus Function Expression?"
As a rule of thumb, when we need to declare a function, the first to consider is Function Declaration syntax. It gives more freedom in how to organize our code, because we can call such functions before they are declared.

That's also better for readability, as it's easier to look up `function f(…) {…}` in the code than `let f = function(…) {…};`. Function Declarations are more "eye-catching".

...But if a Function Declaration does not suit us for some reason, or we need a conditional declaration (we've just seen an example), then Function Expression should be used.
```

## Summary

- Functions are values. They can be assigned, copied or declared in any place of the code.
- If the function is declared as a separate statement in the main code flow, that's called a "Function Declaration".
- If the function is created as a part of an expression, it's called a "Function Expression".
- Function Declarations are processed before the code block is executed. They are visible everywhere in the block.
- Function Expressions are created when the execution flow reaches them.

In most cases when we need to declare a function, a Function Declaration is preferable, because it is visible prior to the declaration itself. That gives us more flexibility in code organization, and is usually more readable.

So we should use a Function Expression only when a Function Declaration is not fit for the task. We've seen a couple of examples of that in this chapter, and will see more in the future.
