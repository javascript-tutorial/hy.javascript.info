importance: 4

---

# Մեծատառ հաստատուններ

Դիտարկենք ստորև բերված կոդը՝

```js
const birthday = '18.04.1982';

const age = someCode(birthday);
```

<<<<<<< HEAD
Այստեղ ունենք `birthday` հաստատունը, որն ամսաթիվ է պարունակում, իսկ `age`-ը հաշվարկվում է `birthday`-ից ինչ-որ ֆուկցիայի միջոցով (մանրամասները նշված չեն հակիրճության համար):
=======
Here we have a constant `birthday` for the date, and also the `age` constant.

The `age` is calculated from `birthday` using `someCode()`, which means a function call that we didn't explain yet (we will soon!), but the details don't matter here, the point is that `age` is calculated somehow based on the `birthday`.
>>>>>>> 5dff42ba283bce883428c383c080fa9392b71df8

Ճիշտ կլինե՞ր մեծատառերով գրել `birthday`-ը: Իսկ `age`-ը՞: Կամ գուցե երկու՞սն էլ:

```js
<<<<<<< HEAD
const BIRTHDAY = '18.04.1982'; // սա՞ գրել մեծատառերով

const AGE = someCode(BIRTHDAY); // թե՞ age-ը
=======
const BIRTHDAY = '18.04.1982'; // make birthday uppercase?

const AGE = someCode(BIRTHDAY); // make age uppercase?
>>>>>>> 5dff42ba283bce883428c383c080fa9392b71df8
```
