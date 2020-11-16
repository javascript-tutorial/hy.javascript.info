# Ներածություն

<<<<<<< HEAD
Եկեք տեսնենք, թե ինչ հատկություններ ունի JavaScript-ը, ինչի կարող ենք հասնել նրանով, և ուրիշ ինչ տեխնոլոգիաներ են դրա հետ լավ աշխատում։
=======
Let's see what's so special about JavaScript, what we can achieve with it, and what other technologies play well with it.
>>>>>>> 99e59ba611ab11319ef9d0d66734b0bea2c3f058

## Ի՞նչ է JavaScript-ը (ՋավաՍքրիփթ)

<<<<<<< HEAD
*JavaScript-ը* սկզբից ստեղծվել է, որպեսզի *«կյանք տա կայքերին»*։
=======
*JavaScript* was initially created to "make web pages alive".
>>>>>>> 99e59ba611ab11319ef9d0d66734b0bea2c3f058

Այս լեզվում ծրագրերը կոչվում են *script-ներ* (սքրիփթ). Նրանք կարող են գրվել ուղղակիորեն կայքի HTML-ի (Էյչ-Թի-Էմ-Էլ) մեջ և աշխատել ավտոմատ կերպով, երբ էջը բեռնվի։

Script-ների ներկայացվում և աշխատում են ինչպես հասարակ տեքստ։ Նրանք կարիք չունեն հատուկ նախապատրաստության աշխատելուց առաջ։

Այս առումով JavaScript-ը շատ է տարբերվում մեկ այլ լեզվից, որը կոչվում է [Java](https://en.wikipedia.org/wiki/Java_(programming_language)):

<<<<<<< HEAD
```smart header="Ինչու՞ <u>Java</u>Script"
Երբ JavaScript ստեղծվել էր, այն սկզբում ուրիշ անուն ուներ՝ «LiveScript» (ԼայվՍքրիփթ)։ Սակայն Java-ն շատ տարածված էր այդ ժամանակ, և որոշվեց, որ լեզվի տարածմանը կօգնի ներկայացնել նոր լեզուն ինչպես Java-ի «կրտսեր եղբայր»։
=======
```smart header="Why is it called <u>Java</u>Script?"
When JavaScript was created, it initially had another name: "LiveScript". But Java was very popular at that time, so it was decided that positioning a new language as a "younger brother" of Java would help.
>>>>>>> 99e59ba611ab11319ef9d0d66734b0bea2c3f058

Բայց երբ այն զարգացավ, JavaScript-ը դարձավ լիովին անկախ լեզու՝ իր հատկանշական մասերով, որոնք անվանվեցին [ECMAScript](http://en.wikipedia.org/wiki/ECMAScript) (ԷՔՄԱՍքրիփթ), և հիմա այն ընդհանրապես ոչ մի կապ չունի Java-ի հետ։
```

Այսօր, JavaScript-ը կարող է աշխատել ոչ միայն browser-ներում (բրաուզեր), այլ նաև server-ներում (սերվեր), կամ ցանկացած սարքերում, որոնք ունեն մի հատուկ ծրագիր, որը կոչվում է [JavaScript engine](https://en.wikipedia.org/wiki/JavaScript_engine) (ՋավաՍքրիթփ էնջըն).

Browser-ն ունի իր մեջ ներառված engine, որը նաև անվանում են «JavaScript virtual machine» (ՋավաՍքրիփթ վըրչուըլ մըշին)։ 

Տարբեր engin-ներ ունեն տարբեր «կեղծանուններ»՝

<<<<<<< HEAD
- [V8](https://en.wikipedia.org/wiki/V8_(JavaScript_engine)) -- Chrome-ում և Opera-ում։
- [SpiderMonkey](https://en.wikipedia.org/wiki/SpiderMonkey) -- Firefox-ում։
- ...Կան այլ կեղծանուններ, ինչպես «Trident» և «Chakra», IE-ի տարբերակների համար, «ChakraCore»-ը Microsoft Edge-ի համար, «Nitro» և  «SquirrelFish»՝ Safari-ի, և այլն։
=======
- [V8](https://en.wikipedia.org/wiki/V8_(JavaScript_engine)) -- in Chrome and Opera.
- [SpiderMonkey](https://en.wikipedia.org/wiki/SpiderMonkey) -- in Firefox.
- ...There are other codenames like "Chakra" for IE, "ChakraCore" for Microsoft Edge, "Nitro" and "SquirrelFish" for Safari, etc.
>>>>>>> 99e59ba611ab11319ef9d0d66734b0bea2c3f058

Նշված տերմինները պետք է հիշել, քանի որ նրանք շատ են օգտագործվում համացանցի հոդվածներում։ Մենք նույնպես կօգտագործենք։ Օրինակ, եթե նշված է, որ «Ա հատկությունը օգտագործվում է V8-ում», ապա այն հավանաբար կաշխատի Chrome-ում և Opera-ում։

```smart header="Ինչպե՞ս են աշխատում engine-ները"

Engine-ները բարդ են, բայց հիմունքները այդքան էլ դժվար չէ հասկանալ։

1. Engine-ը (ներառվածը, եթե browser-ի մասին է խոսքը) կարդում է (parse) script-ը։
2. Ապա այն փոխում է (compile) script-ը մեքենայական կոդի։
3. Վերջապես մեքենան աշխատեցնում է կոդը, բավականին արագ։

<<<<<<< HEAD
Engine-ը բարեփոխումներ (optimization) է անում ամեն քայլին։ Այն նույնիսկ հետևում է պատրաստ script-ի աշխատանքի ընթացքին, վերլուծում տվյալների հոսքը և կրկին բարեփոխումներ կատարում այդ գիտելիքների օգնությամբ։ Երբ դա արված է, script-ը շատ արագ է աշխատում։
=======
The engine applies optimizations at each step of the process. It even watches the compiled script as it runs, analyzes the data that flows through it, and further optimizes the machine code based on that knowledge.
>>>>>>> 99e59ba611ab11319ef9d0d66734b0bea2c3f058
```

## Ի՞նչ է կարող browser-ի միջի JavaScript-ը անել

Ժամանակակից JavaScript-ը «ապահով» ծրագրավորման լեզու է։ Այն չի տրամադրում low-level հասանելիություն հիշողությանը կան CPU-ին, քանի որ սկզբնապես ստեղծված է եղել browser-ների համար, որոնք դրա կարիքը չունեն

JavaScript-ի հնարավորությունները մեծ մասով կախված են միջավայրից, որում այն աշխատում է։ Օրինակ՝ [Node.js](https://wikipedia.org/wiki/Node.js)-ը ունի ֆունկցիաներ, որոնք թույլատրում են JavaScript-ին կարդալ կամ գրել որևէ ֆայլի մեջ, կատարել ցանցային հարցումներ և այլն։

Browser-ի միջի JavaScript-ը կարող է անել ամեն ինչ կապված կայքերի կառավարման հետ և օգտագործողի և server-ի կապի հետ։ver.

Օրինակ՝ browser-ի միջի JavaScript-ը կարող է՝to:

- Ավելացնել նոր HTML էջ, փոխել ներկա պարունակությունը, փոխել ոճը։
- Պատասխանել օգտագործողի գործողություններին, աշխատել մկնիկի սեղման, շարժման ժամանակ։
- Ուղարկել հարցումներ համացանցով server-ների, ներբեռնել և վերբեռնել ֆայլեր (այսպես կոչված [AJAX](https://en.wikipedia.org/wiki/Ajax_(programming)) և [COMET](https://en.wikipedia.org/wiki/Comet_(programming)) տեխնոլոգիաներ)։
- Ստանալ և փոխել cookie-ներ, հարցեր տալ հաճախորդին, ցույց տալ նամակներ։
- Հիշել օգտատերի տվյալները («local storage»).

## Ի՞նչ չի կարող JavaScript-ը անել

JavaScript-ի հնարավորությունները browser-ում սահմանափակ են ապահովության նկատառումներով։ Նպատակն է կանխել չար կայքերի հասանելիությունը օգտագործողի անձնական տվյալներին։

Այսպիսի սահմանափակումների օրինակներ են՝

<<<<<<< HEAD
- JavaScript-ը էջում չի կարող կարդալ գամ գրել որևը կոշտ սկավառակը ֆայլի մեջ, պատճենել դրանք կամ աշխատեցնել ծրագրեր։ Այն չունի ուղիղ հասանելիություն օպերացիոն համակարգի ֆունկցիաներին։
=======
- JavaScript on a webpage may not read/write arbitrary files on the hard disk, copy them or execute programs. It has no direct access to OS functions.
>>>>>>> 99e59ba611ab11319ef9d0d66734b0bea2c3f058

    Ժամանակակից browser-ները թույլ են տալիս աշխատել ֆայլերի հետ, բայց հասանելիությունը տրամադրվում է միայն որոշակի դեպքերում, օրինակ՝ երբ օգտագործողը «նետում» է ֆայլերը պատուհանի մեջ կամ ընտրում `<input>` tag-ի միջոցով։

    Գոյություն ունեն մեթոդներ տեսախցիկի կամ խոսափողի հասանելիություն տրամադրելու, բայց նրանք պահանջում են օգտագործողի կողմից կատարված կամավոր գործողություն, որպեսզի էջը գաղտիաբար չօգտագործի տեսախցիկը և տվյալներ ուղարկի [NSA](https://en.wikipedia.org/wiki/National_Security_Agency)-ին։
- Տարբեր պատուհաններ հիմնականում չգիտեն իրար մասին։ Որոշ դեպքերում, սակայն, գիտեն, օրինակ՝ երբ մի էջը օգտագործում է JavaScript, որ բացի մյուսը։ Սակայն նույնիսկ այս դեպքում, մի էջի JavaScript-ը չի կարող կառավարել մյուսը, եթե նրանք տարբեր աղբյուրներից են։ 

    Սա կոչվում է «Նույն աղբյուրի կանոն»։ Երկու էջերն էլ պետք է պայմանավորվեն տվյալների փոխանակման համար և պարունակեն հատուկ JavaScript կոդ, որը կառավարում է դա։ Մենք կխոսենք դրա մասին դասընթացի մեջ։

    Այս սահմանափակումը, նույնպես, օգտագործողի ապահովության համար է։ `http://anysite.com`-ից էջը, որը օգտագործողը բացել է, չպետք է հասանելիություն ունենա ուրիշ պատուհանի `http://gmail.com`-ին ու գողանա տվյալներ։
- JavaScript-ը կարող է հեշտորեն կապվել ցանցով server-ի հետ, որտեղից որ կայքը գալիս է։ Բայց նրա հնարավորությունը, տվյալներ ստանալ այլ աղբյուրներից, սահմանափակ է։ Չնայած, որ հնարավոր է, սակայն այն պահանջում է հատուկ համաձայնություն server-ից։

![](limitations.svg)

Այսպիսի սահմանափակումներ չկան, երբ JavaScript-ը օգտագործվում է browser-ից դուրս, օրինակ՝ server-ներում։ Ժամանակակից browser-ները նույնպես ունեն plug-in-ներ, որոնք կարող են հարցնել հավելյալ  թույլտվություններ։

## Ի՞նչն է սարքում JavaScript-ը յուրօրինակ

Կան գոնե *երեք* լավ բաներ JavaScript-ի մասին՝

```compare
+ HTML/CSS-ի հետ ներառում։
+ Հասարակ բաները արվում են հասարակ կերպով։
+ Բոլոր մեծ browser-ները աշխատում են JavaScript—ի հետ։
```
JavaScript-ը միակ borwser-ային տեխնոլոգիան է, որը ներառում է այս 3 կետերը։

Ահա, թե ինչն է սարքում դրան այսքան տարբերվող։ Ահա, թե ինչու է ամենատարածված գործիքը browser-ային ինտերֆեյսեր սարքելու համար։

Այսպիսով, JavaScript-ը թույլ է տալիս ստեղծել server-ներ, mobile ծրագրեր և այլն։

## Լեզուներ՝ JavaScript-ի «վրա»

JavaScript-ի գրելաձևը բոլորին չի բավարարում։ Տարբեր մարդիկ ցանկանում են տարբեր հատկություններ։

Դա սպասելի է, քանի որ ծրագրերն ու պահանջները տարբեր են բոլորի մոտ։

Վերջերս բազում նոր լեզուներ են առաջացել, որոնք *transpile* են լինում (փոխվում) JavaScript-ի մինչև աշխատելը։

Ժամանակակից գործիքները դարձնում են փոփոխվելը շատ արագ և թափանցիկ, թույլատրելով ծրագրավորողներին աշխատել այլ լեզվով, և ավտո-փոխակերպում են այն JavaScript-ի աննկատ կերպով։

Այսպիսի լեզուների օրինակներ են՝

<<<<<<< HEAD
- [CoffeeScript](http://coffeescript.org/)-ը ունի կարճ գրելաձև, թույլատրելով ծրագրավորողին գրելկ ավելի մաքուր և ճշգրիտ կոդ։ Հիմնականում Ruby-ի ծրագրավորողներն են հավանում այն։
- [TypeScript](http://www.typescriptlang.org/)-ը կենտրոնացած է խիստ տիպերի ներմուծման վրա, հեշտացնելով դժվար համակարգերի ծրագրավորումն ու հետագա ապահովումը։ Այն ստեղծվել է Microsoft-ի կողմից։
- [Flow](http://flow.org/)-ը նույնպես ավելացնում է տվյալների տիպեր, սակայն այլ կերպով է աշխատում։ Ստեղծված է Facebook-ի կողմից։
- [Dart](https://www.dartlang.org/)-ը առանձին լեզու է, որը ունի իր սեփական engine-ը և աշխատում է ոչ-browser-ային միջավայրներում, ինչպես mobile ծրագրերում, սակայն կարող է թարգմանվել JavaScript-ի։ Ստեղծվել է Google-ի կողմից։
=======
- [CoffeeScript](http://coffeescript.org/) is a "syntactic sugar" for JavaScript. It introduces shorter syntax, allowing us to write clearer and more precise code. Usually, Ruby devs like it.
- [TypeScript](http://www.typescriptlang.org/) is concentrated on adding "strict data typing" to simplify the development and support of complex systems. It is developed by Microsoft.
- [Flow](http://flow.org/) also adds data typing, but in a different way. Developed by Facebook.
- [Dart](https://www.dartlang.org/) is a standalone language that has its own engine that runs in non-browser environments (like mobile apps), but also can be transpiled to JavaScript. Developed by Google.
- [Brython](https://brython.info/) is a Python transpiler to JavaScript that allow to write application in pure Python without JavaScript.
>>>>>>> 99e59ba611ab11319ef9d0d66734b0bea2c3f058

Կան ուրիշներ։ Իհարկե, եթե նույնիսկ օգտագործենք թարգմանված լեզուները, պետք է իմանանք JavaScript, որպեսզի հասկանանք՝ ինչ ենք անում։

## Ամփոփում

<<<<<<< HEAD
- JavaScript-ը սկզբում ստեղծվել է միայն browser-ների համար, սակայն այն հիմա օգտագործվում է շատ այլ միջավայրներում նույնպես։
- Այսօր JavaScript-ը ունի իր ուրույն տեղը ամենաընդունված browser-ի լեզուն, HTML/CSS-ի հետ լրիվ ներառմամբ։ 
- Կան շատ լեզուներ, որոնք «թարգմանվում» են JavaScript-ի և տրամադրում որոշ հատկություններ։ Խորհուրդ է տրվում աչքի անց կացնել դրանք, գոնե մակերեսային, JavaScript-ում խորանալուց առաց։
=======
- JavaScript was initially created as a browser-only language, but it is now used in many other environments as well.
- Today, JavaScript has a unique position as the most widely-adopted browser language with full integration in HTML/CSS.
- There are many languages that get "transpiled" to JavaScript and provide certain features. It is recommended to take a look at them, at least briefly, after mastering JavaScript.
>>>>>>> 99e59ba611ab11319ef9d0d66734b0bea2c3f058
