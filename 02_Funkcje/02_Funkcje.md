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
2. Czym sa obiekty? Z czego sie skladaja?
3. Jak ustawisz, a nastepnie wypiszesz ceche "gatunek" obiektu reprezentujacego domowego pupila `let myPet = {}`? 
4. Czego uzyjesz do przechowania wielu wartosci? Z czego sklada sie ta konstrukcja programistyczna?


### Funkcje

...

### Instrukcje warunkowe

...

### Zmieniamy srodowisko na VS Code

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

### Zadanie 2.2

Przenies to, co przecwiczylismy na poczatku tej lekcji w ramach sekcji *Funkcje* i *Instrukcje warunkowe* i przetestuj wciaz czy dziala.

### HTML i struktura dokumentu strony internetowej

...

### Laczymy operacje (funkcje w JavaScript) z widokiem (dokument w HTML)

...
