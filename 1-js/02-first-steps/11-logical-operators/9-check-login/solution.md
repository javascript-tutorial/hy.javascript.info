

```js run demo
let userName = prompt("Ո՞վ է", '');

if (userName === 'Ադմին') {

  let pass = prompt('Գաղտնաբառը՞', '');

  if (pass === 'Գլխավոր') {
    alert( 'Բարի գալուստ' );
  } else if (pass === '' || pass === null) {
    alert( 'Չեղարկված է' );
  } else {
    alert( 'Սխալ գաղտնաբառ' );
  }

} else if (userName === '' || userName === null) {
  alert( 'Չեղարկված է' );
} else {
  alert( "Չեմ ճանաչում քեզ" );
}
```

Ուշադրություն դարձրեք ուղղահայաց խորություններին(indents) `if` բլոկների ներսում։ Դրանք պարտադիր չեն, բայց դարձնում են ծրագիրը ավելի ընոեռնելի։
