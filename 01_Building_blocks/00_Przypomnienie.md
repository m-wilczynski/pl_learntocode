#### Lekcja 0
# Przypomnienie z lekcji-wstepu

</br>

*(celowo wszystkie wazne nazwy maja w nawiasie tlumaczenia, by latwiej bylo ich potem szukac w Internecie)*

### Zalozenia

*(W telegraficznym skrocie)* **Oprogramowanie/aplikacja/system komputerowy/appka** to **kod (doslownie tekst napisany przez programiste)**, ktory mozna **wykonac**/uzyc na swoim komputerze. Oczywiscie oprogramowanie dzialajace na iPhonie (niemal zawsze) nie bedzie dzialac na laptopie z Windowsem ze wzg. na kompatybilnosc - ale o tym innym razem.

Glownym celem oprogramowania (czyli tego, co tworzymy poprzez programowanie) jest automatyzacja (lub cyfryzacja):
- czegos co albo istnieje juz w otaczajacym nas swiecie 
- albo czegos, co w inny niz dotychczas sposob rozwiazuje jakis istniejacy problem.

Wlasciwie kazde oprogramowanie bedzie mialo:
- `aktorow` (uzytkownikow, inne oprogramowanie/aplikacje)
- `zdarzenia`, na jakie reaguje (klikniecie w przycisk, komenda glosowa, dotyk ale tez uplyw czasu lub komunikaty/wiadomosci z innych programow)
- `operacje`, ktore wykonuje w odpowiedzi na zdarzenia; np. w odpowiedzi na klikniecie w obraz artykulu na stronie Onet.pl (zdarzenie) przegladarka przeniesie nas na strone artykulu (operacja)
- `wynik` operacji, ktory otrzymamy w odpowiedzi na zdarzenie (zazwyczaj beda to jakies `dane` ale moze byc to tez tylko status w postaci jakiegos kodu, np. "OK")

Przyklad - zalozmy, ze korzystamy ze strony MultiKino i szukamy filmu:
<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/6330789/137776442-87ec77b4-8262-4c8e-8709-6f9832759bd7.png" />
</p>

### Jezyk

Do komunikacji z komputerem i opisywaniem tego, co ma robic (czyt. do programowania) uzywamy jezykow programowania. </br>
Dla nauki absolutnych podstaw wybralem jezyk programowania **JavaScript**. </br>
Niegdys sluzyl jedynie do dodawania sniegu na stronach internetowych - dzis jest jednym z najpopularniejszych jezykow programowania zarowno dla hobbystow jak i profesjonalistow. </br>
Materialow dotyczacych tego jezyka jest mnostwo w Internecie, a jednym z najlepszych (i przetlumaczonym na jezyk polski) jest strona **Mozilla Developer Network**:
https://developer.mozilla.org/pl/docs/Web/JavaScript

### Srodowisko programistyczne

Kod *(ang. code)* to fragment tekstu napisanym uzywajac skladni *(ang. syntax)* danego jezyka programowania *(ang. programming language)*.</br>
Kod zazwyczaj piszemy w jakims srodowisku programistycznym zwanym **IDE** *(ang. Integrated Development Environment)*.</br>
Dlaczego uzywamy IDE? Ano dlatego, by pracowac szybciej (dzieki podpowiedziom), popelniac mniej bledow (bledy sa podkreslane) i zeby ogolnie bylo nam wygodniej (mnostwo wtyczek, kolorowanie skladni, autozapis, wlasne preferencje etc.).<br>

Na potrzeby pierwszych lekcji bedziemy korzystac z wbudowanej konsoli w kazda przegladarke, ktora nazywa sie **Developer Tools** (lub DevTools).<br>
By uruchomic DevTools uzyj na dowolnej otwartej stronie (polecam na start google.pl) klawisza `F12`. Powinno otworzyc sie nowe okno.<br>
Przyklad okna DevTools dla przegladarki Chrome:<br>
<p align="center">
<img src="https://user-images.githubusercontent.com/6330789/137780562-9483d0eb-dc97-4a55-b0a5-f62fc6b57eee.png" />
</p>

Przechodzimy do zakladki **Konsola** (ang. Console) znajdujacej sie na gornej belce nowootwartego okna: ![image](https://user-images.githubusercontent.com/6330789/137781103-45050f37-3491-44eb-994c-503d97a8313d.png) gdzie bedziemy od teraz pracowac.
