# Ներածություն

Եկեք տեսնենք, թե ինչ հատկություններ ունի JavaScript-ը, ինչի կարող ենք հասնել նրանով, և ուրիշ ինչ տեխնոլոգիաներ են դրա հետ լավ աշխատում։

## Ի՞նչ է JavaScript-ը (ՋավաՍքրիփթ)

*JavaScript-ը* սկզբից ստեղծվել է, որպեսզի *«կյանք տա կայքերին»*։

Այս լեզվում ծրագրերը կոչվում են *script-ներ* (սքրիփթ). Նրանք կարող են գրվել ուղղակիորեն կայքի HTML-ի (Էյչ-Թի-Էմ-Էլ) մեջ և աշխատել ավտոմատ կերպով, երբ էջը բեռնվի։

Script-ների ներկայացվում և աշխատում են ինչպես հասարակ տեքստ։ Նրանք կարիք չունեն հատուկ նախապատրաստության աշխատելուց առաջ։

Այս առումով JavaScript-ը շատ է տարբերվում մեկ այլ լեզվից, որը կոչվում է [Java](https://en.wikipedia.org/wiki/Java_(programming_language)):

```smart header="Ինչու՞ <u>Java</u>Script"
Երբ JavaScript ստեղծվել էր, այն սկզբում ուրիշ անուն ուներ՝ «LiveScript» (ԼայվՍքրիփթ)։ Սակայն Java-ն շատ տարածված էր այդ ժամանակ, և որոշվեց, որ լեզվի տարածմանը կօգնի ներկայացնել նոր լեզուն ինչպես Java-ի «կրտսեր եղբայր»։

Բայց երբ այն զարգացավ, JavaScript-ը դարձավ լիովին անկախ լեզու՝ իր հատկանշական մասերով, որոնք անվանվեցին [ECMAScript](http://en.wikipedia.org/wiki/ECMAScript) (ԷՔՄԱՍքրիփթ), և հիմա այն ընդհանրապես ոչ մի կապ չունի Java-ի հետ։
```

Այսօր, JavaScript-ը կարող է աշխատել ոչ միայն browser-ներում (բրաուզեր), այլ նաև server-ներում (սերվեր), կամ ցանկացած սարքերում, որոնք ունեն մի հատուկ ծրագիր, որը կոչվում է [JavaScript engine](https://en.wikipedia.org/wiki/JavaScript_engine) (ՋավաՍքրիթփ էնջըն).

Browser-ն ունի իր մեջ ներառված engine, որը նաև անվանում են «JavaScript virtual machine» (ՋավաՍքրիփթ վըրչուըլ մըշին)։ 

Տարբեր engin-ներ ունեն տարբեր «կեղծանուններ»՝

- [V8](https://hy.wikipedia.org/wiki/V8_(JavaScript_%D5%B7%D5%A1%D6%80%D5%AA%D5%AB%D5%B9)) -- Chrome-ում, Opera-ում և Edge-ում։
- [SpiderMonkey](https://en.wikipedia.org/wiki/SpiderMonkey) -- Firefox-ում։
- ...Կան այլ կեղծանուններ, ինչպես «Chakra» IE-ի համար, «JavaScriptCore», «Nitro» և «SquirrelFish»՝ Safari-ի համար, և այլն։

Նշված տերմինները պետք է հիշել, քանի որ նրանք շատ են օգտագործվում համացանցի հոդվածներում։ Մենք նույնպես կօգտագործենք։ Օրինակ, եթե նշված է, որ «Ա հատկությունը օգտագործվում է V8-ում», ապա այն հավանաբար կաշխատի Chrome-ում, Opera-ում և Edge-ում։

```smart header="Ինչպե՞ս են աշխատում engine-ները"

Engine-ները բարդ են, բայց հիմունքները այդքան էլ դժվար չէ հասկանալ։

<<<<<<< HEAD
1. Engine-ը (ներառվածը, եթե browser-ի մասին է խոսքը) կարդում է (parse) script-ը։
2. Ապա այն փոխում է (compile) script-ը մեքենայական կոդի։
3. Վերջապես մեքենան աշխատեցնում է կոդը, բավականին արագ։
=======
1. The engine (embedded if it's a browser) reads ("parses") the script.
2. Then it converts ("compiles") the script to machine code.
3. And then the machine code runs, pretty fast.
>>>>>>> ff4ef57c8c2fd20f4a6aa9032ad37ddac93aa3c4

Engine-ը բարեփոխումներ (optimization) է անում ամեն քայլին։ Այն նույնիսկ հետևում է պատրաստ script-ի աշխատանքի ընթացքին, վերլուծում տվյալների հոսքը և կրկին բարեփոխումներ կատարում այդ գիտելիքների օգնությամբ։ Երբ դա արված է, script-ը շատ արագ է աշխատում։
```

## Ի՞նչ է կարող browser-ի միջի JavaScript-ը անել

<<<<<<< HEAD
Ժամանակակից JavaScript-ը «ապահով» ծրագրավորման լեզու է։ Այն չի տրամադրում low-level հասանելիություն հիշողությանը կան CPU-ին, քանի որ սկզբնապես ստեղծված է եղել browser-ների համար, որոնք դրա կարիքը չունեն
=======
Modern JavaScript is a "safe" programming language. It does not provide low-level access to memory or the CPU, because it was initially created for browsers which do not require it.
>>>>>>> ff4ef57c8c2fd20f4a6aa9032ad37ddac93aa3c4

JavaScript-ի հնարավորությունները մեծ մասով կախված են միջավայրից, որում այն աշխատում է։ Օրինակ՝ [Node.js](https://wikipedia.org/wiki/Node.js)-ը ունի ֆունկցիաներ, որոնք թույլատրում են JavaScript-ին կարդալ կամ գրել որևէ ֆայլի մեջ, կատարել ցանցային հարցումներ և այլն։

Browser-ի միջի JavaScript-ը կարող է անել ամեն ինչ կապված կայքերի կառավարման հետ և օգտագործողի և server-ի կապի հետ։ver.

Օրինակ՝ browser-ի միջի JavaScript-ը կարող է՝to:

- Ավելացնել նոր HTML էջ, փոխել ներկա պարունակությունը, փոխել ոճը։
- Պատասխանել օգտագործողի գործողություններին, աշխատել մկնիկի սեղման, շարժման ժամանակ։
- Ուղարկել հարցումներ համացանցով server-ների, ներբեռնել և վերբեռնել ֆայլեր (այսպես կոչված [AJAX](https://en.wikipedia.org/wiki/Ajax_(programming)) և [COMET](https://en.wikipedia.org/wiki/Comet_(programming)) տեխնոլոգիաներ)։
- Ստանալ և փոխել cookie-ներ, հարցեր տալ հաճախորդին, ցույց տալ նամակներ։
- Հիշել օգտատերի տվյալները («local storage»).

## Ի՞նչ չի կարող JavaScript-ը անել

<<<<<<< HEAD
JavaScript-ի հնարավորությունները browser-ում սահմանափակ են ապահովության նկատառումներով։ Նպատակն է կանխել չար կայքերի հասանելիությունը օգտագործողի անձնական տվյալներին։
=======
JavaScript's abilities in the browser are limited to protect the user's safety. The aim is to prevent an evil webpage from accessing private information or harming the user's data.
>>>>>>> ff4ef57c8c2fd20f4a6aa9032ad37ddac93aa3c4

Այսպիսի սահմանափակումների օրինակներ են՝

- JavaScript-ը էջում չի կարող կարդալ գամ գրել որևը կոշտ սկավառակը ֆայլի մեջ, պատճենել դրանք կամ աշխատեցնել ծրագրեր։ Այն չունի ուղիղ հասանելիություն օպերացիոն համակարգի ֆունկցիաներին։

    Ժամանակակից browser-ները թույլ են տալիս աշխատել ֆայլերի հետ, բայց հասանելիությունը տրամադրվում է միայն որոշակի դեպքերում, օրինակ՝ երբ օգտագործողը «նետում» է ֆայլերը պատուհանի մեջ կամ ընտրում `<input>` tag-ի միջոցով։

<<<<<<< HEAD
    Գոյություն ունեն մեթոդներ տեսախցիկի կամ խոսափողի հասանելիություն տրամադրելու, բայց նրանք պահանջում են օգտագործողի կողմից կատարված կամավոր գործողություն, որպեսզի էջը գաղտնիաբար չօգտագործի տեսախցիկը և տվյալներ ուղարկի [NSA](https://en.wikipedia.org/wiki/National_Security_Agency)-ին։
- Տարբեր պատուհաններ հիմնականում չգիտեն իրար մասին։ Որոշ դեպքերում, սակայն, գիտեն, օրինակ՝ երբ մի էջը օգտագործում է JavaScript, որ բացի մյուսը։ Սակայն նույնիսկ այս դեպքում, մի էջի JavaScript-ը չի կարող կառավարել մյուսը, եթե նրանք տարբեր աղբյուրներից են։ 

    Սա կոչվում է «Նույն աղբյուրի կանոն»։ Երկու էջերն էլ պետք է պայմանավորվեն տվյալների փոխանակման համար և պարունակեն հատուկ JavaScript կոդ, որը կառավարում է դա։ Մենք կխոսենք դրա մասին դասընթացի մեջ։

    Այս սահմանափակումը, նույնպես, օգտագործողի ապահովության համար է։ `http://anysite.com`-ից էջը, որը օգտագործողը բացել է, չպետք է հասանելիություն ունենա ուրիշ պատուհանի `http://gmail.com`-ին ու գողանա տվյալներ։
- JavaScript-ը կարող է հեշտորեն կապվել ցանցով server-ի հետ, որտեղից որ կայքը գալիս է։ Բայց նրա հնարավորությունը, տվյալներ ստանալ այլ աղբյուրներից, սահմանափակ է։ Չնայած, որ հնարավոր է, սակայն այն պահանջում է հատուկ համաձայնություն server-ից։

![](limitations.svg)

Այսպիսի սահմանափակումներ չկան, երբ JavaScript-ը օգտագործվում է browser-ից դուրս, օրինակ՝ server-ներում։ Ժամանակակից browser-ները նույնպես ունեն plug-in-ներ, որոնք կարող են հարցնել հավելյալ  թույլտվություններ։
=======
    There are ways to interact with the camera/microphone and other devices, but they require a user's explicit permission. So a JavaScript-enabled page may not sneakily enable a web-camera, observe the surroundings and send the information to the [NSA](https://en.wikipedia.org/wiki/National_Security_Agency).
- Different tabs/windows generally do not know about each other. Sometimes they do, for example when one window uses JavaScript to open the other one. But even in this case, JavaScript from one page may not access the other page if they come from different sites (from a different domain, protocol or port).

    This is called the "Same Origin Policy". To work around that, *both pages* must agree for data exchange and must contain special JavaScript code that handles it. We'll cover that in the tutorial.

    This limitation is, again, for the user's safety. A page from `http://anysite.com` which a user has opened must not be able to access another browser tab with the URL `http://gmail.com`, for example, and steal information from there.
- JavaScript can easily communicate over the net to the server where the current page came from. But its ability to receive data from other sites/domains is crippled. Though possible, it requires explicit agreement (expressed in HTTP headers) from the remote side. Once again, that's a safety limitation.

![](limitations.svg)

Such limitations do not exist if JavaScript is used outside of the browser, for example on a server. Modern browsers also allow plugins/extensions which may ask for extended permissions.
>>>>>>> ff4ef57c8c2fd20f4a6aa9032ad37ddac93aa3c4

## Ի՞նչն է դարձնում JavaScript-ը յուրօրինակ

Կան գոնե *երեք* լավ բաներ JavaScript-ի մասին՝

```compare
+ HTML/CSS-ի հետ ներառում։
+ Հասարակ բաները արվում են հասարակ կերպով։
+ Բոլոր մեծ browser-ները աշխատում են JavaScript—ի հետ։
```
JavaScript-ը միակ borwser-ային տեխնոլոգիան է, որը ներառում է այս 3 կետերը։

Ահա, թե ինչն է սարքում դրան այսքան տարբերվող։ Ահա, թե ինչու է ամենատարածված գործիքը browser-ային ինտերֆեյսեր սարքելու համար։

<<<<<<< HEAD
Այսպիսով, JavaScript-ը թույլ է տալիս ստեղծել server-ներ, mobile ծրագրեր և այլն։
=======
That said, JavaScript can be used to create servers, mobile applications, etc.
>>>>>>> ff4ef57c8c2fd20f4a6aa9032ad37ddac93aa3c4

## Լեզուներ՝ JavaScript-ի «վրա»

JavaScript-ի գրելաձևը բոլորին չի բավարարում։ Տարբեր մարդիկ ցանկանում են տարբեր հատկություններ։

Դա սպասելի է, քանի որ ծրագրերն ու պահանջները տարբեր են բոլորի մոտ։

<<<<<<< HEAD
Վերջերս բազում նոր լեզուներ են առաջացել, որոնք *transpile* են լինում (փոխվում) JavaScript-ի մինչև աշխատելը։
=======
So, recently a plethora of new languages appeared, which are *transpiled* (converted) to JavaScript before they run in the browser.
>>>>>>> ff4ef57c8c2fd20f4a6aa9032ad37ddac93aa3c4

Ժամանակակից գործիքները դարձնում են փոփոխվելը շատ արագ և թափանցիկ, թույլատրելով ծրագրավորողներին աշխատել այլ լեզվով, և ավտո-փոխակերպում են այն JavaScript-ի աննկատ կերպով։

Այսպիսի լեզուների օրինակներ են՝

<<<<<<< HEAD
- [CoffeeScript](http://coffeescript.org/)-ը ունի կարճ գրելաձև, թույլ է տալիս ծրագրավորողին գրել ավելի մաքուր և ճշգրիտ կոդ։ Հիմնականում Ruby-ի ծրագրավորողներն են հավանում այն։
- [TypeScript](http://www.typescriptlang.org/)-ը կենտրոնացած է խիստ տիպերի ներմուծման վրա, հեշտացնելով դժվար համակարգերի ծրագրավորումն ու հետագա ապահովումը։ Այն ստեղծվել է Microsoft-ի կողմից։
- [Flow](http://flow.org/)-ը նույնպես ավելացնում է տվյալների տիպեր, սակայն այլ կերպ է աշխատում։ Ստեղծված է Facebook-ի կողմից։
- [Dart](https://www.dartlang.org/)-ը առանձին լեզու է, որը ունի իր սեփական engine-ը և աշխատում է ոչ-browser-ային միջավայրներում, ինչպես mobile ծրագրերում, սակայն կարող է թարգմանվել JavaScript-ի։ Ստեղծվել է Google-ի կողմից։
- [Brython](https://brython.info/) թարգմանում է Python-ը JavaScript-ի։
- [Kotlin](https://kotlinlang.org/docs/reference/js-overview.html) ժամանակակից, հակիրճ և ապահով ծրագրավորման լեզու է, կա հնարավորություն կոդը թարգմանելու նաև browser-ների or Node-ի համար։

Կան ուրիշներ։ Իհարկե, եթե նույնիսկ օգտագործենք թարգմանված լեզուները, պետք է իմանանք JavaScript, որպեսզի հասկանանք՝ ինչ ենք անում։
=======
- [CoffeeScript](https://coffeescript.org/) is "syntactic sugar" for JavaScript. It introduces shorter syntax, allowing us to write clearer and more precise code. Usually, Ruby devs like it.
- [TypeScript](https://www.typescriptlang.org/) is concentrated on adding "strict data typing" to simplify the development and support of complex systems. It is developed by Microsoft.
- [Flow](https://flow.org/) also adds data typing, but in a different way. Developed by Facebook.
- [Dart](https://www.dartlang.org/) is a standalone language that has its own engine that runs in non-browser environments (like mobile apps), but also can be transpiled to JavaScript. Developed by Google.
- [Brython](https://brython.info/) is a Python transpiler to JavaScript that enables the writing of applications in pure Python without JavaScript.
- [Kotlin](https://kotlinlang.org/docs/reference/js-overview.html) is a modern, concise and safe programming language that can target the browser or Node.

There are more. Of course, even if we use one of these transpiled languages, we should also know JavaScript to really understand what we're doing.
>>>>>>> ff4ef57c8c2fd20f4a6aa9032ad37ddac93aa3c4

## Ամփոփում

- JavaScript-ը սկզբում ստեղծվել է միայն browser-ների համար, սակայն այն հիմա օգտագործվում է շատ այլ միջավայրներում նույնպես։
- Այսօր JavaScript-ը ունի իր ուրույն տեղը որպես ամենաընդունված browser-ի լեզու, HTML/CSS-ի հետ լրիվ ներառմամբ։ 
- Կան շատ լեզուներ, որոնք «թարգմանվում» են JavaScript-ի և տրամադրում որոշ հատկություններ։ Խորհուրդ է տրվում աչքի անցկացնել դրանք, գոնե մակերեսային, JavaScript-ում խորանալուց հետո։
