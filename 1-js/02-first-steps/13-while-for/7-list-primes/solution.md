There are many algorithms for this task.

Let's use a nested loop:

```js
For each i in the interval {
  check if i has a divisor from 1..i
  if yes => the value is not a prime
  if no => the value is a prime, show it
}
```

The code using a label:

```js run
let n = 10;

nextPrime:
for (let i = 2; i <= n; i++) { // ամեն i֊ի համար...

  for (let j = 2; j < i; j++) { // փնտրում է բաժանարար..
    if (i % j == 0) continue nextPrime; // պարզ չէ, անցնում է հաջորդ i֊ին
  }

  alert( i ); // պարզ թիվ
}
```

Այս օրինակում կան շատ տեղեր, որ կարելի է ավելի օպտիմալ գրել։ Օրինակ մենք կարող ենք փնտրել բաժանարարները `2`֊ից մինչև արմատ `i`֊ն։ Մեծ ինտերվալների դեպքում մենք պետք է լավացնենք (այսինքն փոքրացնենք) փնտրման սահմանները, ավելի արդյունավետ ծրագիր ստանալու համար։ Դրա համար պետք է ծանոթ լինենք խորացված մաթեմատիկայի տարրերին և կոմպլեքս ալգորիթմներին, ինչպիսիք են [Քառակուսային մաղ (Quadratic sieve)](https://en.wikipedia.org/wiki/Quadratic_sieve), [Ընդհանուր թվերի դաշտային մաղ (General number field sieve)](https://en.wikipedia.org/wiki/General_number_field_sieve) և այլն։
