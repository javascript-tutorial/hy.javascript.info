Պատճառը այն է որ մուտքագրված թվերը վերդարձվում են որպես տող։

Այսպիսով փոփոխականները ունեն `"1"` և `"2"` արժեքները։

```js run
let a = "1"; // prompt("First number?", 1);
let b = "2"; // prompt("Second number?", 2);

alert(a + b); // 12
```

Այն, ինչ մենք պետք է անենք, տողերը թվեր փոխարկելն է `+`-ից առաջ։ Օրինակ՝ կիրառելով `Number()` կամ դնելով դիմացից `+`։

Օրինակ՝ `prompt`-ից անմիջապես առաջ:

```js run
let a = +prompt("First number?", 1);
let b = +prompt("Second number?", 2);

alert(a + b); // 3
```

Կամ `alert`-ի մեջ:

```js run
let a = prompt("First number?", 1);
let b = prompt("Second number?", 2);

alert(+a + +b); // 3
```

Կիրառվել են և ունար և բինար `+`վերջին կոդւոմ։ Հիանալի տեսք ունի, այդպես չէ՞
