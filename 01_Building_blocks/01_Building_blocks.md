#### Lekcja 1
# Building blocks (czyli z czego sie sklada kod?)

</br>

*(celowo wszystkie wazne nazwy maja w nawiasie tlumaczenia, by latwiej bylo ich potem szukac w Internecie)*

### Zalozenia

W ramach lekcji 0 powiedzielismy sobie, ze program/oprogramowanie opiera sie o:
1. uzytkownika oprogramowania
2. zdarzenia, na ktore program reaguje
3. operacje, ktore program wykonuje
4. wynik/dane, ktore program zwraca
5. poza zwracanymi danymi program moze rowniez modyfikowac juz istniejace dane

### Konstrukcje

W ramach lekcji 1 zapoznamy sie z podstawowymi elementami, z jakich sklada sie kod tworzacy oprogramowanie oraz ich skladnia w jezyku **JavaScript**.<br>
Naleza do nich:
- `obiekty` (ang. object), ktore pozwalaja opisywac otaczajaca nas rzeczywistosc
- `typy prymitywne` (ang. primitives), ktore pozwalaja nam opisywac wartosci cech obiektow (np. obiekt `Ksiazka` ma ceche `strony` o wartosci `450`)
- `tablice` (ang. array), ktore pozwalaja nam na przechowywanie wiecej niz jednej wartosci (np. obiekt `Koszyk` ma ceche `zawartosc` o wartosci `[ 'Jablko', 'Gruszka', 'Banan' ]`)
- `zmienne` (ang variable) - miejsca, w ktorych mozemy przechowywac dane i w prosty sposob uzywac ich w innych miejscach programu (np. `let stawkaVat = 0.23` pozwala nam pozniej uzywac w programie nazwy `stawkaVat` zamiast pamietac za kazdym razem ile VAT wynosi, gdy doliczamy go do ceny produktu)
- `funkcje` (ang. function) zwane w niektorych jezykach metodami; opisuja operacje (np. obiekt `Przycisk` ma operacje `kliknij`, ktora prezentuje jakis popup)
- `instrukcje warunkowe` (ang. conditional), ktore pozwalaja nam zrobic cos tylko, jesli cos innego jest prawda (np. mozesz kliknac `Wyslij` jesli wypelniono wszystkie dane)
- `petle` (ang. loop), ktore pozwalaja nam przegladac elementy wczesniej wspomnianych tablic (np. przejrzyj `Koszyk` i wypisz z `zawartosc` tylko owoce zaczynajace sie na `J`)

### Skladnia

Najwazniejsza konstrukcja jezyka programowania jest zmienna. To w niej bedziemy przechowywac obiekty, typy prymitywne czy tablice i to je bedziemy przekazywac do funkcji. To je beda sprawdzac instrukcje warunkowe i to je beda przegladac petle.<br>

Piszac program w jezyku JavaScript (jak i wielu innych jezykach) zaczynam od **deklaracji** zmiennej (uwaga, cos bede tu przechowywac), nadajac jej **nazwe** (od teraz nazywasz sie tak) i ew. **przypisujac wartosc** (zalozmy `4`).<br>
W JavaScript bedzie to wygladac mniej wiecej tak:
```javascript
let mojaZmienna = 4;
```
Zadeklarowalismy (`let`) zmienna o nazwie `mojaZmienna` przypisujac jej wartosc `4`. Kazde takie wyrazenie konczymy srednikiem (`;`) co pozwala programowi zrozumiec gdzie konczy sie nasz fragment kodu.<br>

Do kodu mozemy rowniez dodawac komentarze, ktore pozwola nam na zapamietanie, o co nam wlasciwie chodzilo:
```javascript
//Komentarz moge wstawic przed wlasciwa linia
let mojaZmienna = 4; //...albo tez na koncu linii kodu...
let innaZmienna = /* ...albo w srodku kodu */ 123;
```

Po tych dwoch przykladach pewnie juz widzisz, ze w "dziwny" sposob nazywam nasze zmienne. Jest to konwencja, ktora nazywamy `camelCase` i jest ona standardem przyjetym dla jezyka JavaScript. Oczywiscie inne jezyki moga (i czesto korzystaja) z innych konwencji nazewniczych (np. `PascalCase` lub `snake_case`).<br>
Wiecej tutaj: https://pl.wikipedia.org/wiki/CamelCase

### Komunikaty

Komunikaty sa przydatna funkcjonalnoscia, dzieki ktorej w latwy sposob mozemy cos wypisac na konsole (nasze srodowisko programistyczne).
Sprobujmy wypisac poprzednio zadeklarowana zmienna `mojaZmienna`:
```javascript
console.log(mojaZmienna); //powinno wypisac 4
```

Zauwaz, ze nie uzylismy bezposredni


### Obiekty

Obiekty wykorzystujemy do opisywania elementow otaczajacego nas swiata, ktorych nie da sie opisac (tylko pojedyncza) liczba, tekstem lub wartoscia tak/nie.<br>
Ceche obiektow nazywamy w programowaniu **polem** (ang. field) lub **wlasciwoscia** (ang. property), aczkolwiek w niektorych jezykach programowania (np. C#) sa to rozne konstrukcje programistyczne.<br>
Sposob tworzenia obiektow w jezyku JavaScript jest nieco prostszy niz w innych jezykach (o czym przekonasz sie w przyszlosci).<br>
Stworzmy obiekt `ksiazka` i nadajmy mu cechy `tytul`, `ile stron`, `czy przeczytano` i `sr. ocena w Internecie`:
```javascript
let ksiazka = {}; //stworz nowy obiekt
ksiazka.tytul = 'Harry Potter i Kamien Filozoficzny'; //ustawmy w polu 'tytul' wartosc 'Harry Potter (...)
ksiazka.ileStron = 340;
ksiazka.czyPrzeczytano = true;
ksiazka.sredniaOcena = 7.9;
```
Zauwaz, ze by dostac sie "do srodka" dowolnego obiektu uzywamy znaku kropki, po ktorym mozemy odczytac lub zmodyfikowac **pole obiektu**. Gdybysmy chcieli np. zbadac pozostale litry paliwa w obiekcie `samochod`

Przy okazji tworzenia nowego obiektu (klamry: `{}`) poznalismy tez sposob korzystania z podstawowych typow prymitywnych:
- tekstu (ang. string), ktory opisujemy w pojedynczym lub podwojnym cudzyslowiu `'to jest moj tekst'`
- liczb calkowitych (ang. integer/int), np. `340`
- wartosci logicznych (ang. boolean/bool): `true` lub `false`
- liczb zmiennoprzecinkowych (ang. float, double i decimal*), np. `7.9`

### Cwiczenie 1.1

Wybierz z twojego otoczenia trzy przedmioty i zaprogramuj je jako obiekty w konsoli.<br>
Kazdy obiekt powinien miec conajmniej trzy pola: tekstowe, liczbowe i logiczne.<br>
Po utworzeniu wszystkich trzech obiektow wypisz pole przechowujace wartosc tekstowa kazdego z nich.<br>
