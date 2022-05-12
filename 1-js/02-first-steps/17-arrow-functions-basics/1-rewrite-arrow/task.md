
# Դարձնել սլաքով ֆունկցիաներ

Ստորև կոդում սովորական ֆունկցիաները (Function Expressions) փոխարինել՝ դարձնելով սլաքով ֆունկցիաներ․

```js run
function ask(question, yes, no) {
  if (confirm(question)) yes();
  else no();
}

ask(
  "Դուք համաձա՞յն եք:",
  function() { alert("Դուք համաձայնեցիք:"); },
  function() { alert("Դուք չեղարկեցիք կատարումը:"); }
);
```
