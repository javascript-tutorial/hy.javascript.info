# Ներածություն

Եկեք տեսնենք, թե ինչ հատկություններ ունի ՋավաՍքրիփթը, ինչի կարող ենք հասնել նրանով, և ուրիշ ինչ տեխնոլոգիաներ են դրա հետ լավ աշխատում։

## Ի՞նչ է ՋավաՍքրիփթը

*ՋավաՍքրիփթը* սկզբից ստեղծվել է, որպեսզի *«կյանք տա կայքերին»*։

Այս լեզվում ծրագրերը կոչվում են *սքրիփթներ*. Նրանք կարող են գրվել ուղղակիորեն կայքի HTML-ի մեջ և աշխատել ավտոմատ կերպով, երբ էջը բեռնվի։

Սքրիփթները ներկայացվում և աշխատում են ինչպես հասարակ տեքստ։ Նրանք կարիք չունեն հատուկ նախապատրաստության աշխատելուց առաջ։

Այս առումով ՋավաՍքրիփթը շատ է տարբերվում մեկ այլ լեզվից, որը կոչվում է [Java](https://en.wikipedia.org/wiki/Java_(programming_language)):

```smart header="Ինչու՞ <u>Ջավա</u>Սքրիփթ"
Երբ ՋավաՍքրիփթը ստեղծվել էր, այն սկզբում ուրիշ անուն ուներ՝ «ԼայվՍքրիփթ» (LiveScript)։ Սակայն Ջավան շատ տարածված էր այդ ժամանակ, և որոշվեց, որ լեզվի տարածմանը կօգնի ներկայացնել նոր լեզուն ինչպես Ջավայի «կրտսեր եղբայր»։

Բայց երբ այն զարգացավ, ՋավաՍքրիփթը դարձավ լիովին անկախ լեզու՝ իր հատկանշական մասերով, որոնք անվանվեցին [ECMAScript](http://en.wikipedia.org/wiki/ECMAScript), և հիմա այն ընդհանրապես ոչ մի կապ չունի Ջավայի հետ։
```

Այսօր, ՋավաՍքրիփթը կարող է աշխատել ոչ միայն բրաուզերներում, այլ նաև սերվերներում, կամ ցանկացած այլ սարքերում, որոնք ունեն մի հատուկ ծրագիր, որը կոչվում է [JavaScript engine](https://en.wikipedia.org/wiki/JavaScript_engine).

Բրաուզերն ունի իր մեջ ներառված engine, որը նաև անվանում են «JavaScript virtual machine»։ 

Տարբեր engin-ներ ունեն տարբեր «կեղծանուններ»՝

- [V8](https://en.wikipedia.org/wiki/V8_(JavaScript_engine)) -- Chrome-ում և Opera-ում։
- [SpiderMonkey](https://en.wikipedia.org/wiki/SpiderMonkey) -- Firefox-ում։
- ...Կան այլ կեղծանուններ, ինչպես «Trident» և «Chakra», IE-ի տարբերակների համար, «ChakraCore»-ը Microsoft Edge-ի համար, «Nitro» և  «SquirrelFish»՝ Safari-ի, և այլն։

Նշված տերմինները պետք է հիշել, քանի որ նրանք շատ են օգտագործվում համացանցի հոդվածներում։ Մենք նույնպես կօգտագործենք։ Օրինակ, եթե նշված է, որ «Ա հատկությունը օգտագործվում է V8-ում», ապա այն հավանաբար կաշխատի Chrome-ում և Opera-ում։

```smart header="Ինչպե՞ս են աշխատում engine-ները"

Engine-ները բարդ են, բայց հիմունքները այդքան էլ դժվար չէ հասկանալ։

1. Engine-ը (ներառվածը, եթե browser-ի մասին է խոսքը) կարդում է (parse) սքրիփթը։
2. Ապա այն փոխում է (compiles) սքրիփթը մեքենայական կոդի։
3. Վերջապես մեքենան աշխատեցնում է կոդը, բավականին արագ։

Engine-ը բարեփոխումներ (optimization) է անում ամեն քայլին։ Այն նույնիսկ հետևում է պատրաստ սքրիփթի աշխատանքի ընթացքին, վերլուծում տվյալների հոսքը և կրկին բարեփոխումներ կատարում այդ գիտելիքների օգնությամբ։ Երբ դա արված է, սքրիփթը շատ արագ է աշխատում։
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

- JavaScript-ը էջում չի կարող կարդալ գամ գրել որևը կոշտ սկավառակը ֆայլի մեջ, պատճենել դրանք կամ աշխատեցնել ծրագրեր։ Այն չունի ուղիղ հասանելիություն օպերացիոն համակարգի ֆունկցիաներին։

    Ժամանակակից browser-ները թույլ են տալիս աշխատել ֆայլերի հետ, բայց հասանելիությունը տրամադրվում է միայն որոշակի դեպքերում, օրինակ՝ երբ օգտագործողը «նետում» է ֆայլերը պատուհանի մեջ կամ ընտրում `<input>` tag-ի միջոցով։

    Գոյություն ունեն մեթոդներ տեսախցիկի կամ խոսափողի հասանելիություն տրամադրելու, բայց նրանք պահանջում են օգտագործողի կողմից կատարված կամավոր գործողություն, որպեսզի էջը գաղտիաբար չօգտագործի տեսախցիկը և տվյալներ ուղարկի [NSA](https://en.wikipedia.org/wiki/National_Security_Agency)-ին։
- Տարբեր պատուհաններ հիմնականում չգիտեն իրար մասին։ Որոշ դեպքերում, սակայն, գիտեն, օրինակ՝ երբ մի էջը օգտագործում է JavaScript, որ բացի մյուսը։ Սակայն նույնիսկ այս դեպքում, մի էջի JavaScript-ը չի կարող կառավարել մյուսը, եթե նրանք տարբեր աղբյուրներից են։ 

    Սա կոչվում է «Նույն աղբյուրի կանոն»։ Երկու էջերն էլ պետք է պայմանավորվեն տվյալների փոխանակման համար և պարունակեն հատուկ JavaScript կոդ, որը կառավարում է դա։ Մենք կխոսենք դրա մասին դասընթացի մեջ։

    Այս սահմանափակումը, նույնպես, օգտագործողի ապահովության համար է։ `http://anysite.com`-ից էջը, որը օգտագործողը բացել է, չպետք է հասանելիություն ունենա ուրիշ պատուհանի `http://gmail.com`-ին ու գողանա տվյալներ։
- JavaScript-ը կարող է հեշտորեն կապվել ցանցով server-ի հետ, որտեղից որ կայքը գալիս է։ Բայց նրա հնարավորությունը, տվյալներ ստանալ այլ աղբյուրներից, սահմանափակ է։ Չնայած, որ հնարավոր է, սակայն այն պահանջում է հատուկ համաձայնություն server-ից։

![](limitations.svg)

Such limits do not exist if JavaScript is used outside of the browser, for example on a server. Modern browsers also allow plugin/extensions which may ask for extended permissions.

## What makes JavaScript unique?

There are at least *three* great things about JavaScript:

```compare
+ Full integration with HTML/CSS.
+ Simple things are done simply.
+ Support by all major browsers and enabled by default.
```
JavaScript is the only browser technology that combines these three things.

That's what makes JavaScript unique. That's why it's the most widespread tool for creating browser interfaces.

That said, JavaScript also allows to create servers, mobile applications, etc.

## Languages "over" JavaScript

The syntax of JavaScript does not suit everyone's needs. Different people want different features.

That's to be expected, because projects and requirements are different for everyone.

So recently a plethora of new languages appeared, which are *transpiled* (converted) to JavaScript before they run in the browser.

Modern tools make the transpilation very fast and transparent, actually allowing developers to code in another language and auto-converting it "under the hood".

Examples of such languages:

- [CoffeeScript](http://coffeescript.org/) is a "syntactic sugar" for JavaScript. It introduces shorter syntax, allowing us to write clearer and more precise code. Usually, Ruby devs like it.
- [TypeScript](http://www.typescriptlang.org/) is concentrated on adding "strict data typing" to simplify the development and support of complex systems. It is developed by Microsoft.
- [Flow](http://flow.org/) also adds data typing, but in a different way. Developed by Facebook.
- [Dart](https://www.dartlang.org/) is a standalone language that has its own engine that runs in non-browser environments (like mobile apps), but also can be transpiled to JavaScript. Developed by Google.

There are more. Of course, even if we use one of transpiled languages, we should also know JavaScript to really understand what we're doing.

## Summary

- JavaScript was initially created as a browser-only language, but is now used in many other environments as well.
- Today, JavaScript has a unique position as the most widely-adopted browser language with full integration with HTML/CSS.
- There are many languages that get "transpiled" to JavaScript and provide certain features. It is recommended to take a look at them, at least briefly, after mastering JavaScript.
