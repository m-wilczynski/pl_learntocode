#### Lekcja 1
# Building blocks (czyli z czego sie sklada kod?)

</br>

*(celowo wszystkie wazne nazwy maja w nawiasie tlumaczenia, by latwiej bylo ich potem szukac w Internecie)*

### Zalozenia

W ramach lekcji 0 powiedzielismy sobie, ze program/oprogramowanie opiera sie o:
1. uzytkownika oprogramowania (jego oczywiscie nie bedziemy oprogramowywac :) )
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

Zauwaz, ze nie uzylismy bezposrednio wartosci "4" a jedynie nazwe zmiennej, do ktorej przypisalismy ta wartosc.<br>
Dzieki temu, jesli wartosc zmiennej `mojaZmienna` gdzies w programie sie zmieni, nasze wypisanie (ale tez inne uzycia tej zmiennej) "zobacza" ta nowa wartosc.<br>
Sprobujmy!

```javascript
console.log(mojaZmienna); //wypisze 4
mojaZmienna = 5;
console.log(mojaZmienna); //wypisze 5
```

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

### Typy prymitywne

Przy okazji tworzenia nowego obiektu (klamry: `{}`) poznalismy tez sposob korzystania z podstawowych typow prymitywnych:
- tekstu (ang. string), ktory opisujemy w pojedynczym lub podwojnym cudzyslowiu `'to jest moj tekst'`
- liczb calkowitych (ang. integer/int), np. `340`
- wartosci logicznych (ang. boolean/bool): `true` lub `false`
- liczb zmiennoprzecinkowych (ang. float, double i decimal*), np. `7.9`

### Cwiczenie 1.1

Wybierz z twojego otoczenia trzy przedmioty i zaprogramuj je jako obiekty w konsoli.<br>
Kazdy obiekt powinien miec conajmniej trzy pola: tekstowe, liczbowe i logiczne.<br>
Po utworzeniu wszystkich trzech obiektow wypisz pole przechowujace wartosc tekstowa kazdego z nich.<br>

### Tablice

Tablica jest konstruktem (a wlasciwie, to tez obiektem!), ktory pozwala w prosty sposob przechowywac wiecej niz jeden element.<br>
Dlugosc tablicy, tj. ile mozna w niej "zmiescic" elementow jest stala. Dlugosc tablicy mozemy zawsze sprawdzic korzystajac z wbudowanego pola **length**, np. `mojaTablica.length` zwroci dlugosc tablicy mojaTablica.<br>
Elementy tablicy maja konkretne "umiejscowienie", tzn. jesli zalozymy, ze tablica ma rozmiar/dlugosc 4, to elementy beda w niej umiejscowione w konkretnych "slotach", ktory nazywami **indeksami**.<br>
Indeksy zaczynaja sie zawsze od zera (!). Np. dla tablicy owocow `owoce` o rozmiarze 3, pierwszy element bedzie mial indeks zero, a dostep do niego odbywal sie bedzie tak:
```javascript
owoce[0] = 'Jablko'; //ustaw "Jablko" jako pierwszy element tablicy "owoce"
owoce[1] = 'Gruszka'; //drugi element
```
Uzywajac bardziej obrazowej formy, tablice mozemy opisac tak:
<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/6330789/137792165-c4066b37-0f99-463a-902a-1453dafe05de.png" />
</p>


Zalozmy, ze chcemy opisac biblioteczke z ksiazkami. Zaczelibysmy pewnie tak jak wczesniej z ksiazka, tworzac obiekt:
```javascript
let biblioteczka = {}; //tworzymy obiekt
biblioteczka.material = 'drewno'; //dodamy informacje, z czego jest zbudowana
```
Teraz pewnie chcielibysmy dodac pole 'ksiazki'. Zeby umiescic w tym polu wiecej niz jedna pozycje musimy uzyc jak wyzej tablicy (nawiasy kwadratowe: `[]`).<br>
Ustawmy pole `ksiazki` obiektu `biblioteczka` od razu uzupelniajac je ksiazkami:
```javascript
biblioteczka.ksiazki = [
  'Harry Potter',
  'Przygody z Owca',
  'Beksinski, vol. 2',
  'Sapiens'
];
```

A co jesli zapomnimy dodac cos do naszej biblioteczki albo pojawi sie nowa ksiazka? <br>
Skoro tablica ma stala dlugosc, nie mozemy po prostu uzyc kolejnego indeksu! <br>
Zamiast tego uzyjemy wbudowanej funkcji `push()`:
```javascript
biblioteczka.ksiazki.push('Skazani na Shawshank');
```

Fukcja `push()` jest wbudowana funkcja obiektu `Array` reprezentujacego tablice w jezyku JavaScript. <br>
Oczywiscie nie sposob zapamietac jak wszystko zrobic w danym jezyku, dlatego warto po prostu "googlowac" korzystajac z wczesniej wspomnianej strony Mozilla Developer Network (aka "MDN").<br>
Oto moj wynik szukajac po slowach kluczowych zwiazanych z w/w zagadnieniem:

<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/6330789/137793349-efbc1699-ec9c-4b70-9a26-a1d09db9104e.png" />
</p>

<br>

### Zadanie 2.2

Skoro juz wiesz jak opisywac obiekty wokol siebie, wybierz inna rzecz (ktora zawiera wiele podobnych rzeczy w sobie) z otaczajacej Cie rzeczywistosci i opisz go w sposob podobny do tego, jak opisalismy biblioteczke.

##### Bonus
Sprobuj "wygooglowac" jak wypisac wszystkie elementy z twojego nowoutworzonego obiektu.
