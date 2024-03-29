Այս առաջադրանքը ցուց է տալիս, թե ինչպես նախածանցի/վերջածանցի կիրառումը կարող է բերել տարբեր արդյունքների, երբ դրանք օգտագործվում են համեմատության մեջ։

1. **1֊ից մինչև 4**

    ```js run
    let i = 0;
    while (++i < 5) alert( i );
    ```

    Առաջին արժեքը `i = 1`, քանի որ `++i`֊ն սկզբում աճեցնում է `i`֊ի արժեքը, և հետո նոր վերադարձնում ստացված նոր աժեքը։ Այսպիսով առաջին համեմատությունը կլինի `1 < 5` և `alert`֊ը ցույց կտա `1`։

    Ապա կհաջորդի `2, 3, 4…` -- արժեքները կցուցադրվեն մեկը մյուսի հետևից։ Համեմատումը միշտ օգտագործում է ավելացված արժեքը, քանի որ `++`֊ը գրված է փոփոխականից առաջ։

    Եվ վերջապես `i = 4` ավելացվում է դառնալով `5`, `while(5 < 5)` համեմատումը կլինի սխալ, և ցիկլը կավարտվի։ Այսպիսով `5`֊ը չի երևա էկրանին։
2. **1֊ից մինչև 5**

    ```js run
    let i = 0;
    while (i++ < 5) alert( i );
    ```

    Առաջին արժեքը կրկին `i = 1` է։ `i++`֊ը աճեցնում է `i`֊ն, և ապա վերադարձնում *հին* արժեքը, այսպիսով `i++ < 5` համեմատության մեջ `i = 0` (ի տարբերություն `++i < 5`֊ի)։

    Բայց `alert`֊ի կանչը առանձին է։ Այն առանձին հատված է, որը կատարվում է փոփոխականի աճից և համեմատումից հետո։ Այսպիսով այն ստանում է ընթացիկ `i = 1`։

    Ապա հետևում են `2, 3, 4…`։

    Կանգ առնենք `i = 4` դեպքի վրա։ `++i`֊ն կաճեցներ `i`֊ն և կօգտագործեր `5` արժեքը համեմատման համար։ Բայց այստեղ օգտագործվում է `i++`, որը աճեցնում է `i`֊ն՝ դանձնելով `5`, և վերադարձնում հին արժեքը։ Հետևաբար համեմատումը կլինի `while(4 < 5)` -- որն էլ ճիշտ է, և `alert`֊ը ցույց կտա `5` արժեքը։

    `i = 5` արժեքի դեպքում հաջորդ քայլում կունենանք `while(5 < 5)`, որն էլ սխալ է։
