
```js run
function ask(question, yes, no) {
  if (confirm(question)) yes();
  else no();
}

ask(
  "Դուք համաձա՞յն եք:",
*!*
  () => alert("Դուք համաձայնեցիք:"),
  () => alert("Դուք չեղարկեցիք կատարումը:")
*/!*
);
```

Հակիրճ և պարզ տեսք ունի, այդպես չէ՞:
