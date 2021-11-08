#### Lekcja 3
# Podstawy HTML

</br>

### Powtorka - lekcja 2

1. Do czego sluza funkcje?
2. Jakie operatory dostepne sa dla liczb, jakie dla tekstu a jakie dla wyrazen logicznych (`true`/`false`)?
3. Jakiej skladni uzyjesz do zaprogramowania zdania 
> **Jezeli `wynik` wiekszy od zera wypisz 'Super!', w przeciwnym razie wypisz 'Oh nie...'**


### HTML i struktura dokumentu strony internetowej

W lekcji 2 stworzylismy plik `index.html`, bedacy (przez konwencje przyjeta w Internecie) plikiem definiujacym strone startowa kazdej witryny internetowej.
Witryna (`web site`) moze skladac sie z wielu stron (`web page`). Np. witryna https://onet.pl zawiera wiele stron, reprezentujacych codziennie wydawane artykuly. Potocznie o calej witrynie mowi sie (troche mylnie) jako o stronie internetowej, dlatego tez czasem dla faktycznych stron (w ramach tej "strony internetowej") uzywa sie pojecia "podstrony".

##### Skladnia jezyka HTML

Jezyk HTML (ktory nie jest wlasciwie jezykiem programowania a jedynie jezykiem znacznikow) opisujacy dokument strony internetowej sklada sie z tzw. **tagow** (_pl. znacznikow_), ktorych nazwy umieszczamy w nawiasach trojkatnych: `<mojTag>`. Kazdy tag raz otwarty musi byc tez zamkniety takim samym tagiem poprzedzonym slashem (`/`). Dla przykladu wczesniej wspomniany "wymyslony" tag `<mojTag>` domkniemy tagiem `</mojTag>`.

Kazdy tag moze rowniez zawierac atrybuty, ktore moga go opisywac, np. nazwe, wartosc, identyfikator czy nawet elementy stylu takie jak kolor czcionki, tla etc.
Atrybut nastepuje zawsze jako czesc tagu jako `nazwaAtrybutu="wartosc atrybutu"`, np. atrybut `id` o wartosci `"moj-przycisk"` tagu reprezentujacego przycisk `<button>` zapiszemy tak:
```html
<button id="moj-przycisk"></button>
```
Tagi moga rowniez zawierac w sobie inne tagi lub tekst. Np. najczesciej uzywany w HTML tag `<div>` - oznaczajacy po prostu element/sekcje strony - zazwyczaj zawiera w sobie inne tagi. 
Dla przykladu - ponizszy przyklad definiuje sekcje wewnatrz tagu `<div>`, w ktorej znajduja sie dwa przyciski, kazdy zawierajacy inny tekst:
```html
<div>
  <button>Pierwszy przycisk</button>
  <button>Drugi przycisk</button>
</div>
```

##### Dokument HTML

Powtorzmy kroki z lekcji drugiej w nowym folderze, ktory nazwiemy `lekcja3`.
Ponownie stworzymy w nim plik `index.html`, ktory wypelnimy ponizszym kodem i zapiszemy poprzez _File->Save_ albo skrot `Ctrl+S`:
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

Przyjrzyjmy sie teraz dokladnie dokumentowi, ktory stworzylismy.

Sklada sie on zawsze z przynajmniej 4 czesci:
- naglowka `<!DOCTYPE html>`, ktory jest deklaracja typu dokumentu jako HTML
- tagu `<html>`, w ktorym beda znajdowac sie wszystkie pozostale tagi
- tagu `<head>` (**wewnatrz** tagu `<html>`), ktory definiuje importowane do dokumentu strony elementy takie jak kod JavaScript (patrz plik `site.js`, ktory w lekcji 2 stworzylismy) czy arkusze styli (definiujace jak wyglada strona) i inne, mniej lub bardziej przydatne rzeczy
- tagu `<body>` (**wewnatrz** tagu `<html>`), ktory definiuje wlasciwa strukture strone, czyli jaki element, w ktorym miejscu ma sie znajdowac

W naszym przypadku w tagu `<head>` zaimportowalismy nasz plik `site.js` z kodem JavaScript poprzez tag `<script>` z atrybutem `src`  (skrot od "source" - zrodlo) wskazujacym na lokalizacje pliku:
```html
<script src="site.js"></script>
```
oraz dodalismy drugi tag, w ktorym mozemy bezposrednio pisac kod JavaScript, jesli nie chcemy pisac go w oddzielnym pliku:
```html
<script>
  //Tu bedziemy miec dostep do wszystkiego, co znajduje sie w w/w site.js
</script>
```

W tagu `<body>` dodalismy dwa tagi:
- `<h2>` ktory reprezentuje 2gi najwiekszy typ naglowka (h = header) na stronie; `<h1>` oznaczalby najwiekszy naglowek na stronie, `<h3>` 3ci najwiekszy itd. az do `<h6>`
- `<div>`, ktory reprezentuje sekcje strony, w ramach ktorej po prostu umiescilismy tekst

### Zadanie 3.1

We wczesniej utworzonej stronie `lekcja3/index.html` sprobujmy stworzyc kopie artykulu dot. witryny/serwisu internetowego z Wikipedii.
> :warning: **Jesli masz watpliwosci "w co wsadzic tekst lub jakis element", zawsze zaczynaj od `<div>`**

Zeby stworzyc w/w artykul:
- dodajmy naglowek o wielkosci 2 z tytulem "Serwis internetowy"
- dodajmy sekcje opis serwisu internetowego:
> Serwis internetowy, witryna internetowa (ang. website) – grupa powiązanych ze sobą, w celu zwiększenia funkcjonalności, stron internetowych i innych dokumentów udostępnianych w internecie z jednego adresu domenowego za pośrednictwem usługi WWW[1]. Serwisy internetowe, poza treścią statyczną, często mają sekcję wiadomości oraz oferują możliwość logowania się i zapamiętywania preferencji odbiorców w celu dostosowania treści do indywidualnych upodobań. W serwisie mogą występować obiekty interaktywne, na przykład formularze, aplikacje. 
Serwisy mogą być tematyczne, a więc poświęcone jednej dziedzinie lub kwestii, albo ogólne. 
- dodajmy kolejna sekcje, w ktorej bedzie znajdowac sie naglowek o wielkosci 4 z tytulem "Wybrane rodzaje serwisów internetowych" oraz wymienione rodzaje witryn:
> - portal internetowy – jest zwykle wielotematyczny, oferuje dostęp do różnorodnych informacji
> - wortal (portal wertykalny) – portal wyspecjalizowany, publikujący informacje z jednej dziedziny (muzyki, filmu, motoryzacji, programów komputerowych)
> - bankowość elektroniczna – dostęp do rachunku bankowego za pomocą komputera podłączonego do internetu
    
    
Wynikowa strona bedzie wygladac +/- tak:
</br>
![image](https://user-images.githubusercontent.com/6330789/140816902-456338a9-8d93-4139-b6c5-d334a09c6b25.png)
    
 > :warning: Pamietaj by zapisac dokument uzywajac `Ctrl+S`
    
</br>
</br>
    
### Laczymy operacje (funkcje w JavaScript) z widokiem (dokument w HTML)

...
