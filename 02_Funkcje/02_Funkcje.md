#### Lekcja 2
# Funkcje

</br>

*(od teraz celowo rowniez zmienne i nazwy funkcji beda w jezyku angielskim)*

### Zanim zaczniemy (lub w trakcie powtorki)
Od dzis postaramy sie nie tylko pracowac w konsoli ale tez w klasycznym edytorze kodu (IDE).<br>
Pobierz (i zainstaluj) darmowe IDE - `VS Code` - ze strony Microsoftu dla twojego systemu operacyjnego (wspiera Windowsa, macOS i wiekszosc dystrybucji Linuxa):
https://code.visualstudio.com/download

### Powtorka - lekcja 1

1. Czym sa zmienne?
2. Jakie znasz typy prymitywne? Wymien ich angielskie nazwy.
3. Czym sa obiekty? Z czego sie skladaja?
4. Jak ustawisz, a nastepnie wypiszesz ceche "gatunek" obiektu reprezentujacego domowego pupila `let myPet = {}`? 
5. Czego uzyjesz do przechowania wielu wartosci? Z czego sklada sie ta konstrukcja programistyczna?


### Funkcje

Funkcje realizuja jedna ze skladowych programu, o ktorej mowilismy w lekcji 0 - **operacje**.<br>
Funkcje moga byc `globalne` (tzn. nie przynaleza do zadnego obiektu) lub `obiektu` (sa czescia danego obiektu).<br>
W kontekscie obiektow, czasem mowi sie, ze skoro pola reprezentuja cechy obiektu, to funkcje (jesli sa jego czescia) reprezentuja jego zachowanie.

Posluzmy sie przykladem obiektu `Ksiazka` z Lekcji 1...
```javascript
let book = {};
book.title = 'Harry Potter and Philosophers Stone';
book.pagesCount = 340;
book.wasRead = true;
```
...i dodajmy do niej mozliwosc oceniania podobna do serwisu Reddit czy Wykop (`+` jako lubie, `-` jako nie lubie).<br>
Za kazdym razem, gdy ktos ocenia ksiazke, zaktualizujemy obecny wynik ksiazki i go wypiszemy.<br>
Zacznijmy od dodania pola, ktore bedzie reprezentowac obecny wynik:
```javascript
book.currentScore = 0; //Zaczynamy od zera - nikt jeszcze nie ocenil
```

Dodajmy teraz mozliwosc glosowania na dana ksiazke w formie funkcji:
```javascript
book.like = function() {
    this.currentScore = this.currentScore + 1; //Lubie: +1 do wyniku
    console.log('Obecny wynik to: ' + this.currentScore); //stringi (czyli teksty) sklejamy znakiem dodawania
}

book.dislike = function() {
    this.currentScore = this.currentScore - 1; //Nie lubie: -1 do wyniku
    console.log('Obecny wynik to: ' + this.currentScore);
}
```

> **Zwroc uwage na slowo kluczowe `this`**, ktore uzylismy. Jest ono niczym innym jak wskazaniem "na siebie samego" wewnatrz danego obiektu.<br>
> Dla wyzej wspomnianego obiektu trzymanego w zmiennej `book` slowo kluczowe `this` uzyte "wewnatrz tego obiektu" oznacza po prostu obiekt `book`.

Skladnia funkcji to: 
- deklaracja, ze to funkcja poprzez slowo kluczowe `function`, 
- nawiasy "okragle" tzn. `(argument1, argument2, ...)`, ktore mowia "co wchodzi do funkcji" (w naszym przypadku nic, dlatego `()`) 
- oraz kodu, ktory wykona sie po wywolaniu (uzyciu) funkcji w ramach klamr `{}`. W ramach klamr moze (ale nie musi) znajdowac sie slowo kluczowe `return`, ktore pozwala nam zwrocic wynik z funkcji. Wywolanie `return` konczy dzialanie funkcji.<br>

W powyzszym przykladzie obiektowi `book` przypisalismy funkcje do polubienia pod nazwa `like` i funkcje do nielubienia jako `dislike`.
W jezyku JavaScript funkcje obiektu definiujemy w ten sam sposob, co przypisanie wartosci do pola tego obiektu.

Sprobujmy teraz uzyc naszej funkcji i zaczac glosowac na nasza ksiazke:
```javascript
book.like();
book.dislike();
book.dislike();
book.dislike();
```

Wynik powinien wyniesc -2.

Przecwiczmy jeszcze wspomiane slowo kluczowe `return`:
```javascript
let taxes = {};
taxes.getVat = function() { return 0.23; }

//Przypiszmy teraz wynik funkcji getVat do zmiennej
let vat = taxes.getVat();
console.log(vat); //0.23
```

### Reuzywalnosc funkcji

Powiedzielismy, ze funkcje tworzymy, by realizowac operacje lub zachowanie obiektu.<br>
Jest jednak jeszcze jeden, rownie wazny powod: **reuzywalnosc**.<br>
Funkcje, ktora do tej pory uzywalismy byly proste ale wyobraz sobie, ze piszesz funkcjonalnosc sortowania ksiazek alfabetycznie wewnatrz biblioteczki.<br>
Raz napisana funkcja sortowania pozwoli nam utrzymac porzadek alfabetyczny bez koniecznosci pisania kodu sortowania za kazdym dodaniem ksiazki.

Gdy juz mamy funkcje `sortAlphabetically`, wystarczy nam uzycie jej gdy tylko tego potrzebujemy:
```javascript
let bookshelf = {};
bookshelf.books = [];
bookshelf.sortAlphabetically = function() { /* tu bylaby nasza implementacja sortowania */ };
let newBook = { title: 'Harry Potter' };
bookshelf.books.push(newBook);
bookshelf.sortAlphabetically(); //Przywroc porzadek alfabetyczny
let anotherNewBook = { title: 'Przygoda z owca' };
bookshelf.books.push(anotherNewBook);
bookshelf.sortAlphabetically(); //Przywroc porzadek alfabetyczny
```

Sama **reuzywalnosc pozwala nam tez na standaryzacje podejscia do roznych rzeczy** w ramach danego obiektu.<br>
Np. zauwaz, ze dla przykladu ksiazki, ktory rozszerzylismy o mozliwosc glosowania/oceniania mamy dwie, takie same linie wewnatrz funkcji `like` i `dislike`:
```javascript
    console.log('Obecny wynik to: ' + this.currentScore);
```
Gdy zdecydujemy, ze chcemy zmienic sposob wypisywania obecnego wyniku ksiazki, musielibysmy za kazdym razem modyfikowac obie te funkcje. <br>
Co gorsza, gdybysmy chcieli robic to tez w ramach innej, nowej funkcji, musielibysmy znow przekopiowac ta linijke i pamietac, by ja aktualizowac gdy cos sie zmieni.

Zamiast tego mozemy ustandaryzowac wypisywanie obecnego wyniku w ramach oddzielnej funkcji i po prostu z niej korzystac:
```javascript
//Nowa funkcja dla wypisywania wyniku:
book.printScore = function() {
    console.log('Obecny wynik to: ' + this.currentScore);
}

book.like = function() {
    this.currentScore = this.currentScore + 1; //Lubie: +1 do wyniku
    this.printScore(); //uzywamy nowej funkcji
}

book.dislike = function() {
    this.currentScore = this.currentScore - 1; //Nie lubie: -1 do wyniku
    this.printScore(); //uzywamy nowej funkcji
}
```
Zauwaz, ze niewazne ile funkcji nie korzystalo by z funkcji `printScore` (niewazne czy "wewnatrz" czy "z zewnatrz" obiektu) ich wypisywany komunikat bedzie spojny i ten sam.

> Dobra praktyka i nawykiem jest wylapywanie sytuacji jak powyzsza i **wydzielanie** wspoldzielonych funkcjonalnosci, tak by mozna je bylo reuzyc.

### Zmieniamy srodowisko na VS Code

*(UWAGA! Ten podrozdzial to wlasciwie INSTRUKCJA. Nie probuj niczego z tego wkurwac - sama bieglosc przyjdzie z czasem wraz z korzystaniem z narzedzia)*

Zacznijmy od stworzenia folderu, w ktorym bedziemy pracowac. Nazwijmy go `lekcja2`.

Teraz otworzmy nasze nowopobrane i zainstalowane IDE - VS Code:<br>
![image](https://user-images.githubusercontent.com/6330789/138522920-ec1918be-ce85-460e-85cf-d4688f72d4d7.png)


Nastepnie otworzmy ten folder w zainstalowanym na poczatku lekcji VS Code:<br>
![image](https://user-images.githubusercontent.com/6330789/138522010-35766b10-392b-4422-9e67-a4c2a0699809.png)

Po lewej strony powinnismy widziec teraz zawartosc (obecnie pustego) folderu `lekcja2`:<br>
![image](https://user-images.githubusercontent.com/6330789/138523180-8be95f77-5265-40ed-bb0e-d196b607010f.png)


Dodajmy (prawym na w/w pustej liscie -> *New file*) dwa pliki:
- `index.html` - reprezentujacym dokument naszej testowej strony internetowej (o tym za chwile troche wiecej); plik nie nazwalismy bez powodu w ten sposob - przyjelo sie tak nazywac kazda strone startowa serwisu w Internecie  
- `site.js` - reprezentujacym kod naszej strony (od teraz bedziemy programowac tutaj)

Mamy teraz otwarty kazdy z w/w plikow jako tab (zakladke) w edytorze:<br>
![image](https://user-images.githubusercontent.com/6330789/138523529-9e83dd54-07c0-40bf-bf59-38268c541a5c.png)

Do pliku `index.html` wklejmy n/w zawartosc:
```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">

        <script src="site.js"></script>
        <script>
            //Tu bedziemy miec dostep do wszystkiego, co znajduje sie w w/w site.js
        </script>
    </head>
    <body>
        <h2>Zaladowano dokument!</h2>
        <div>Teraz wszystko, co dodasz w site.js po odswiezeniu bedzie widoczne w konsoli DevTools.</div>
    </body>
</html>
```

Do pliku `site.js` wklejmy n/w zawartosc:
```javascript
function test() {
    console.log('Hello World!');
}
```

Teraz otworz plik `index.html` w przegladarce (dwuklik na tym pliku w folderze `lekcja2` powinien wystarczyc).<br>
Nowootwarta strona powinna wygladac +/- tak:<br>
![image](https://user-images.githubusercontent.com/6330789/138524140-edd7f9a5-67d5-46e1-863e-04deb937f0e3.png)

Otworz teraz DevTools (F12) i sprobuj uzyc testowej funkcji `test()`, ktora zdefiniowalismy w pliku `site.js`. Powinnismy zobaczyc wypisane *Hello World!*.

### Zadanie 2.1

Przenies to, co przecwiczylismy na poczatku tej lekcji w ramach sekcji *Funkcje* i *Instrukcje warunkowe* i przetestuj wciaz czy dziala.

### Operatory, wyrazenia logiczne i logika Boole'a

W lekcji pierwszej powiedzielismy sobie o 4 typach prymitywnych (czasem nazywanymi tez "typami prostymi"). Pominmy na razie liczby zmiennoprzecinkowe.<br>
Najbardziej naturalnym typem kojarzacym sie nam z funkcjami jest oczywiscie *liczba calkowita* - `int`. Dostepne operatory na liczbach calkowitych to m.in. `+`, `-`, `*` i `/`, sluzace do podstawowych operacji arytmetycznych.<br>
W przykladzie z glosowaniem uzylismy operatora `+` do zwiekszania wyniku o 1.<br>
W/w operatory beda zwracac inne liczby (calkowite lub zmiennoprzecinkowy) - tak jak w klasycznej arytmetyce.<br>
Na liczbach calkowitych mozemy rowniez uzywac **operatorow porownania - wiekszy od `>` i mniejszy od `<`**. Ich wynikiem bedzie wartosc logiczna: `true` albo `false`:
```javascript
let example1 = 2 > 3; //false
let example2 = 3 > 1; //true
```

Na liczbach, jak i na kazdym innym typie prostym mozemy uzyc rowniez **operatora porownania `==`**, ktory oznacza "czy rowna sie?".<br>
Intencjonalnie nie uzywamy pojedynczego znaku rownosci (`=`), poniewaz w wiekszosci jezykow programowania oznacza on **przypisanie**.<br>
Przyklad:
```javascript
let example3 = 3 == 3; //true
```

W programowaniu pozostale typy proste tez posiadaja swoje operatory (poza "rowna sie"), tak bysmy w podobny (do operacji arytmetycznych) sposob operowac na nich.<br>
Chwile wczesniej przy wypisywaniu tekstu "skleilismy" dwa teksty (`string`) ze soba uzywajac operatora `+`:
```javascript
let myText = 'Hello`; //stworz zmienna myText
myText = myText ` World!`;//Ustaw zmiennej myText nowa wartosc: stara wartosc myText plus doklejone ` World!`
```

Na wartosciach logicznych rowniez mozemy wykonywac operacje, niestety uzywane operatory nieco roznia sie od tych znanych z arytmetyki.<br>
Arytmetyke na wartosciach logicznych nazywamy *logika Boole'a* (od nazwiska angielskiego matematyka).<br>
Podstawowe operatory, ktore Ci sie najczesciej przydadza to:
- `&&` oznaczajacy "oraz"
- `||` oznaczajacy "lub"
- `!` oznaczajacy negacje

Przyklad dwoch pierwszych operatorow:
```javascript
let canRideOnLand = true; //czy moze jezdzic po ladzie?
let canRideOnWater = false; //czy moze plywac po wodzie?
//Jest amfibia jesli jezdzi po ladzie i plywa po wodzie
let isAmphibous = canRideOnLand && canRideOnWater; //false
canRideOnWater = true; //jednak uznalismy, ze tez umie plywac
isAmphibous = canRideOnLand && canRideOnWater; //true
```
Przyklad negacji:
```javascript
let isRed = true; //jest czerwony
let isNotRed = !isRed; //nieprawda ze "jest czerwony"
```

> Wszystkie operatory (ale tez funkcje), ktore zwracaja wartosc logiczna (`true` lub `false`) nazywamy **wyrazeniami logicznymi**.

### Instrukcje warunkowe

Funkcje (niewazne czy wydaja Ci sie teraz skomplikowane czy nie) same w sobie nie pozwalaja na zbyt wiele bez inny konstruktow, dostepnych w programowaniu.<br>
Jednym z najwazniejszych takich konstruktow jest **instrukcja warunkowa**, ktora mozemy uzywac jedynie wewnatrz funkcji (lub w szczegolnym przypadku w ramach deklaracji zmiennej).<br>
Jej dzialanie jest dosc intuicyjne: `jezeli (warunek) to X, w przeciwnym wypadku Y`. W miejscu `(warunek)` zawsze musi znajdowac sie albo zmienna typu `bool`/`boolean` (nazwa rozni sie zaleznie od jezyka) lub wyrazenie logiczne (tzn. takie, z ktorego wynikac moga tylko dwa wyniki: tak (`true`) lub nie (`false`)).

Wykorzystajmy ponownie przyklad z ksiazka i - podmieniajac funkcje `book.printScore` - dodajmy do naszego wypisywania:
- `'Niezle!'` - jesli wynik jest dodatni
- `'Oh nie...'` - jesli wynik jest ujemny

Oto jak to zrobic:
```javascript
//Zmieniona funkcja wypisywania
book.printScore = function() {
    //Jezeli (if) obecny wynik > 0
    if (this.currentScore > 0) {
        console.log('Hurra! Obecny wynik to: ' + this.currentScore);
    }
    //W przeciwnym razie (else)
    else {
        console.log('Oh nie... Obecny wynik to: ' + this.currentScore);
    }
}
```

Instrukcje warunkowa zawsze zaczynamy od "jezeli(mojWarunek)" - `if(mojWarunek)`.<br>
Nastepnie to, co ma sie wykonac jezeli mojWarunek jest spelniony wpisujemy w klamrach `{}`.<br>
Nastepnie mozemy dodac inny warunek "lub jezeli(mojInnyWarunek)" - `else if(mojInnyWarunek) { ... }`. Takich "lub jezeli" mozemy dodac ile chcemy.<br>
Instrukcje warunkowa mozemy (ale nie musimy) zakonczyc warunkiem "a w przeciwnym razie" - `else { ... }`.<br>

### Zadanie 2.2

Mamy jeden, nieobsluzony przypadek w naszej funkcji `printScore`, a jest nim zero. Dodaj obsluge tego warunku przy uzyciu `else if` dopisujac na poczatku komunikatu `No coz. `.

### Zadanie 2.3 (homework)

Dokoncz funkcje `getZodiacSign(birthdate)` przyjmujaca jeden parametr (date urodzenia) i zwracajacy nazwe znaku zodiaku.

```javascript
let horoscope = {};
horoscope.getZodiacSign = function(birthDate) {
    let day = birthDate.getDate(); //pobierz dzien miesiaca z birthDate
    let month = birthDate.getMonth() + 1; //pobierz numer miesiaca z birthDate (niestety w JavaScript zaczyna sie od "0", wiec musimy dodac 1)
    
    let zodiacSign = '';
    
    //Tutaj twoja czesc odpowiedzialna za przypisanie do zodiacSign wlasciwego znaku zodiaku w zaleznosci od otrzymanej daty urodzenia
    
    return zodiacSign;
}

```
Wiecej o samym wbudowanym obiekcie `Date` reprezentujacym date w jezyku Javascript znajdziesz w MDN: https://developer.mozilla.org/pl/docs/Web/JavaScript/Reference/Global_Objects/Date
