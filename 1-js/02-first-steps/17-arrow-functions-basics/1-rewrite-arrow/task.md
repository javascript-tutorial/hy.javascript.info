
# Վերագրել սլաքով ֆունկցիաների

Ստորև կոդում սովորական ֆունկցիաները (Function Expressions) փոխարինել՝ դարձնել սլաքով ֆունկցիաներ․

```js run
function ask(question, yes, no) {
  if (confirm(question)) yes();
  else no();
}

ask(
  "Դուք համաձա՞յն եք:",
  function() { alert("Դուք համաձայնվեցիք:"); },
  function() { alert("Դուք չեղարկեցիք կատարումը:"); }
);
```
