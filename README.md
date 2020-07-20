## Olini instrukcja do karty produktu nowego szablonu.

Z wyjątkiem karty produktu oraz dropdown menu większości zmian dokonujemy za pomocą opcji Personalizuj dostępnej w zakładce Wygląd Sklepu.
Wszystkie treści przedstawione w poniższej instrukcji są treściami przykładowymi.

Dwa widoki karty produktu:
    W związku z tym, że karta produktu na froncie sklepu wymaga zmian w produkcie w panelu sklepu, wdrożylismy dwa jej widoki. Pierwszy widok jest widokiem domyślnym dla nowych szablonów i wyświetla się domyślnie dla każdego produktu.
    Drugi widok uruchamia się w momencie, gdy do produktu dodany jest którykolwiek z tagów opisanych poniżej.
    
Aby karta produktu NIE ULEGLA ZMIANOM w aktywnym szablonie, należy:
* Przed przystąpieniem do pracy nad produktem dodać do niego tag "new"
* Przekopiować zawartość pola "krótki opis produktu" na samą górę opisu produktu
* Po treści krótkiego opisu wstawić słowo klucz ``_divide``
* po treści opisu głównego dla STAREGO szablonu wstawić słowo klucz ``_separator``
* Treści zgodne z instrukcją poniżej wypełniać po kluczu ``_separator``

    
    
### OPIS PRODUKTU

Treść w sekcjach 1, 3 i 5 edytujemy za pomocą edycji opisu produktu. Opis podzielony jest za pomocą klucza ``_divide`` - czyli tam, gdzie kończy się treść danej sekcji opisu a zaczyna następna wstawiamy słowo klucz ``_divide``, przykładowo:
![](https://i.imgur.com/U8sMBI6.png)



Dodatkowo, aby pojawiła się sekcja 3 i/lub 5, konieczne jest aby produkt posiadał odpowiedni tag:
``desc-1`` dla sekcji 3 i  ``desc-2``.  Sekcja pierwsza będzie widoczna zawsze, ale miejsmy na uwadze że w niej zawieramy informacje o sugerowanej pojemności produktu, więc powinnam zawierac jeden klucz ``_divide``

W sekcjach 3 i 5 mamy zdjęcia oraz jedno video.
Aby zdjęcie wyświetlało się w odpowiedniej sekcji, to musi być ono:
* dodane do karty produktu
* posiadać odpowiedni alt
    * alt jest zależny od sekcji, w której zdjęcie ma się wyświetlać i powinien wyglądać następująco:
        * ``desc_1_1`` dla zdjęcia przy sekcji 3
        * ``desc_2_1`` dla  pierwszego zdjęcia przy sekcji 5
        * ``desc_2_2`` dla drugiego zdjęcia przy sekcji 5
        

Aby w sekcji 3 wyświetlało się video, produkt również musi posiadać odpowiedni tag. Tag dot. video powinien wyglądać następująco: ``video_1_bX4Pf_5fpiA`` Gdzie ``video_1_`` jest częścią stałą dla każdego produktu, a pozostała część to fragment linku do video, czyli mając link https://www.youtube.com/watch?v=bX4Pf_5fpiA&t=8s
wycinamy ``bX4Pf_5fpiA`` i doklejamy na koncu taga.

### SEKCJA 2
Aby sekcja była widoczna, konieczne jest dodanie do produktu tagu ``props`` oraz stworzenie odpowiedniej strony własnej w panelu sklepu. Strona musi nazywać się ``nazwa_produktu_props`` czyli przykładowo, dla produktu Olej lniany, stronę nazywamy ``olej_lniany_props``. Ważnym jest by w nazwie strony był dokładny tytuł produktu napisany małymi literami, ze spacjami zamienionymi na znak ``_``

Po utworzeniu strony, cokolwiek tam zostanie wpisane wyświetli się na karcie produktu. Aby jednak zachować układ zgodny z projektem, wypełniona musi zostać poniższa templatka:
```html
<div class="columns custom-props-inner-wrapper">
    <div class="column is-3-desktop is-3-tablet is-12-mobile">
        <div class="custom-props-element">
            <p class="custom-prop-value">83,93g</p>
            <p class="custom-prop-description">kwasy tłuszczowe nienasycone</p>
        </div>
    </div>
    <div class="column is-3-desktop is-3-tablet is-12-mobile">
        <div class="custom-props-element">
            <p class="custom-prop-value">52,92g</p>
            <p class="custom-prop-description">kwasy tłuszczowe wielonasycone</p>
        </div>
    </div>
    <div class="column is-3-desktop is-3-tablet is-12-mobile">
        <div class="custom-props-element">
            <p class="custom-prop-value"><em class="ol-icon-thermometer"></em></p>
            <p class="custom-prop-description">do spożywania na zimno</p>
        </div>
    </div>
</div>
<div class="columns">
<div class="column is-12 props-baseline">
wszystkie dane na 100 g
</div>
</div>
```
Gdzie edytujemy tylko tekst pomiędzy znacznikami, a znaczniki powinny zostać nienaruszone. Wypełniony kod wklejamy w zawartość strony własnej, używając edytora HTML stron własnych, dostępnego po kliknięciu następującego przycisku:
![](https://i.imgur.com/dfIC1Rx.png)

W przypadku tej templatki edytujemy tylko poniższe bloki:
```html
            <p class="custom-prop-value">83,93g</p>
            <p class="custom-prop-description">kwasy tłuszczowe nienasycone</p>
```
Czyli podmieniamy tekst pomiędzy znacznikami oznaczonymi klasą ``"custom-prop-value"`` lub ``"custom-prop-description"``
            

### SEKCJA 3
Poruszona w pierwszej części intrukcji (OPIS PRODUKTU)
### SEKCJA 4
Analogicznie, jak w przypadku Sekcji 2, i w tym przypadku musimy:
* dodać do produktu odpowiedni tag ``ingredients`` 
* stworzyć stronę o nazwie ``nazwa_produktu_ingredients`` 
* edytować templatkę i wkleić kod w kod strony własnej.

```html
<div class="columns custom-ingredients-content">
    <div class="column is-12 ingredients-header">
    <h3>Składniki</h3>
    <p>100% olej z nasion czarnuszki siewnej tłoczony na zimno</p>
    </div>
    <div class="columns">
        <div class="column is-12">
            <h3>Warto wiedzieć</h3>
        </div>
    <div class="column is-6">
    
    <div class="ingredients-list-element">
<figure><img src="https://cdn.shoplo.com/5432/s/54/assets/polska-icon-01.svg?6292" data-image="y5mfn2mawc3e"></figure>
        <div class="ingredients-content-wrapper">
            <span class="ing-header">
            Kraj pochodzenia:
            </span>
            <span class="ing-content">
            Polska
            </span>
        </div>
    </div>
    
    <div class="ingredients-list-element">
        <div class="ingredients-icon ol-icon-for-whom"></div>
        <div class="ingredients-content-wrapper">
            <span class="ing-header">
            Dla kogo:
            </span>
            <span class="ing-content">
            Nie jest polecany dla kobiet w ciąży oraz dzieci poniżej pierwszego roku życia.
            </span>
        </div>
    </div>
    
    <div class="ingredients-list-element">
        <div class="ingredients-icon ol-icon-taste"></div>
        <div class="ingredients-content-wrapper">
            <span class="ing-header">
        Kolor i smak:
            </span>
            <span class="ing-content">
                W zależności od partii ziaren olej może różnić się kolorem, smakiem i mętnością. Olej z czarnuszki ma barwę od czarnego, ciemnozielonego, po zupełnie jasny czy słomkowy. Mimo tych różnic nie różni się właściwościami. Olej z czarnuszki ma korzenny, wyrazisty smak.
            </span>
        </div>
    </div>
    
    <div class="ingredients-list-element">
        <figure><img src="https://cdn.shoplo.com/5432/s/54/assets/peanut.svg?8051" data-image="6n6vwvsixdeb"></figure>
        <div class="ingredients-content-wrapper">
            <span class="ing-header">
            Informacja dla alergików:
            </span>
            <span class="ing-content">
                Może zawierać gorczycę oraz gluten.
            </span>
        </div>
    </div>
    </div>
    <div class="column is-6">
    
    <div class="ingredients-list-element">
        <div class="ingredients-icon ol-icon-clock"></div>
        <div class="ingredients-content-wrapper">
            <span class="ing-header">
                Termin przydatności do spożycia:
            </span>
                <span class="ing-content">
                Termin przydatności do spożycia to 3 miesiące od daty wytłoczenia, niezależnie od daty otwarcia. Data znajduje się na tylnej etykiecie. Oleje w naszej rodzinnej olejarni Olini tłoczymy małymi partiami, na świeżo oznacza to, że olej z czarnuszki nie stoi na półce. Ten, który do Was wyślemy będzie miał maksymalnie 2-5 dni.
            </span>
        </div>
    </div>
    
    <div class="ingredients-list-element">
        <div class="ingredients-icon ol-icon-fridge"></div>
        <div class="ingredients-content-wrapper">
            <span class="ing-header">
            Przechowywanie:
        </span>
                <span class="ing-content">
                Olej z czarnuszki trzeba przechowywać w lodówce (w temperaturze około 4-10 stopni) przed jak i po otwarciu. </span>
        </div>
    </div>
    
    <div class="ingredients-list-element">
                <figure><img src="https://cdn.shoplo.com/5432/s/54/assets/residue.svg?8051" data-image="9w6crhxav7zw"></figure>

        <div class="ingredients-content-wrapper">
            <span class="ing-header">
            Osad:
        </span>
                <span class="ing-content">
                Jeżeli olej dłuższy czas stoi bez ruchu, to osad może osiąść na dnie butelki. Sedymentacja osadu w oleju z czarnuszki jest procesem naturalnym. Przed użyciem można wstrząsnąć delikatnie butelką, aby wzbudzić osad.
            
            </span>
        </div>
    </div>
    
    </div>
    </div>
    <div class="column is-12 nutri-values-table">
        <h3>Wartości odżywcze</h3>
        <div class="columns nutri-values">
            <div class="column is-4-desktop is-6-tablet is-12-mobile nutri-content">
    <div class="nutri-vals-header">
        <span class="nutri-right">Wartość odżywcza</span><span class="nutri-left">w 100 g</span>
    </div>

    <div class="nutri-vals-row">
        <span class="nutri-right">Wartość energetyczna</span><span class="nutri-left">3700 kJ  / 900 kcal</span>
    </div>
    <div class="nutri-vals-row">
        <span class="nutri-right">tłuszcz</span><span class="nutri-left">100 g</span>
    </div>
    <div class="nutri-vals-row">
        <span class="nutri-right">w tym</span><span class="nutri-left"></span>
    </div>
    <div class="nutri-vals-row">
        <span class="nutri-right">kwasy tłuszczowe nasycone</span><span class="nutri-left">16,07 g</span>
    </div>
    <div class="nutri-vals-row">
        <span class="nutri-right">kwasy tłuszczowe jednonasycone</span><span class="nutri-left">24,41 g</span>
    </div>
    <div class="nutri-vals-row">
        <span class="nutri-right">kwasy tłuszczowe wielonasycone</span><span class="nutri-left">59,52 g</span>
    </div>
    <div class="nutri-vals-row">
        <span class="nutri-right">węglowodany</span><span class="nutri-left">0 g</span>
    </div>
    <div class="nutri-vals-row">
        <span class="nutri-right">w tym cukry</span><span class="nutri-left">0 g</span>
    </div>
    <div class="nutri-vals-row">
        <span class="nutri-right">białko</span><span class="nutri-left">0 g</span>
    </div>
    <div class="nutri-vals-row">
        <span class="nutri-right">sól</span><span class="nutri-left">0 g</span>
    </div>
</div>

        </div>
<div id="nutriTrigger">
<span class="show">Pokaż tabelę wartości odżywczych</span>
<span class="hide">Ukryj tabelę wartości odżywczych</span>
</div>
    </div>
    </div>
```    

Analogicznie jak w przypadku poprzedniej strony, edytujemy jedynie tekst pomiędzy znacznikami a następnie wklejamy za pomocą edytora HTML stron własnych w kod strony własnej.

#### Nagłówek sekcji
```html
<h3>Składniki</h3>
<p>100% olej z nasion czarnuszki siewnej tłoczony na zimno</p>
```
W znacnziku ``h3``powinien znaleźć się tytuł główny sekcji, w znaczniku ``p`` umieszczamy podtytuł.
##### Sekcja "warto wiedzieć"
Analogicznie jak wyżej, tytuł sekcji umieszczamy pomiędzy znacznikami ``h3``:
```html
<h3>Warto wiedzieć</h3>
```
Kolejne elementy sekcji są blokami:
```html
<div class="ingredients-list-element">
    <figure><img src="https://cdn.shoplo.com/5432/s/54/assets/polska-icon-01.svg?6292" data-image="y5mfn2mawc3e"></figure>
    <div class="ingredients-content-wrapper">
        <span class="ing-header">
            Kraj pochodzenia:
        </span>
        <span class="ing-content">
            Polska
        </span>
    </div>
</div>
```
Podmieniamy tekst w znaczniku o klasie ``"ing-header"`` - tu umieszczamy "nagłówek elementu", oraz podmieniamy tekst w znaczniku o klasie ``"ing-content"`` - tu umieszczamy "treść elementu"

Powtarzamy dla każdego kolejnego elementu.

#### Tabela rozmiarów
Tabela rozmiarów również skłąda się z powtarzalnych bloków, w których wypełniamy odpowiednie wartości:
```html
    <div class="nutri-vals-row">
        <span class="nutri-right">Wartość energetyczna</span><span class="nutri-left">3700 kJ  / 900 kcal</span>
    </div>
```

W znacznikach oznaczonych klasą ``"nutri-right"`` umieszczamy to co ma się znaleźć w prawej kolumnie, natomiast w znacznikach oznaczonych klasą ``"nutri-left"`` to co ma się znaleźć w lewej kolumnie.
Wiersz można powtórzyć dowolną ilość razy.

### SEKCJA 5
Poruszona w pierwszej części instrukcji (OPIS PRODUKTU)

### SEKCJA 6
Sekcja 6 zawiera video, aby video się wyświetlało należy dodac do produktu tag ``video_2_fragmentlinku``, przykładowo ``video_2_bX4Pf_5fpiA`` Gdzie ``video_2_`` jest częścią stałą dla każdego produktu, a pozostała część to fragment linku do video, czyli mając link https://www.youtube.com/watch?v=bX4Pf_5fpiA&t=8s
wycinamy ``bX4Pf_5fpiA`` i doklejamy na koncu taga.

### SEKCJA 7
Analogicznie jak w przypadku sekcji 4, aby sekcja była widoczna, należy:
* dodać do produktu odpowiedni tag ``why`` 
* stworzyć stronę o nazwie ``nazwa_produktu_why`` 
* edytować templatkę i wkleić kod w kod strony własnej.

```html <div class="columns why-wrapper">
<h3 class="column is-8 is-offset-2 why-header">
Dlaczego warto sięgnąć po olej z czarnuszki Olini?
</h3>
<span class="column is-8 is-offset-2">
W naszej rodzinnej olejarni tłoczymy jedynie najlepszej jakości olej z czarnuszki.
Jeszcze niedawno tłoczyliśmy go jedynie dla siebie i naszych bliskich, teraz chcemy dzielić
się tym co najlepsze z naszymi klientami:
</span>

<div class="column is-12 why-section">
	<div class="why-section-wrapper">
		<div class="why-icon ol-icon-grains" style="color: #fde5b4;"></div>
		<div class="why-texts">
			<span class="why-text-header">
				Najlepsze ziarno
			</span>
			<span class="why-text">
				Nasz olej tłoczymy ze starannie wyselekcjonowanych ziaren czarnuszki siewnej pochodzącej z Polski. Ziarna zamawiamy wyłącznie u sprawdzonych dostawców, do których mamy wieloletnie zaufanie. Wiemy, że najlepszej jakości surowiec gwarantuje otrzymanie oleju spożywczego, który będzie miał pełnię smaku.
			</span>
		</div>
	</div>


	<div class="why-section-wrapper">
		<div class="why-icon ol-icon-leaves-drop" style="color:#d3ab9e;"></div>
		<div class="why-texts">
			<span class="why-text-header">
				Odpowiedni proces produkcji
			</span>
			<span class="why-text">
				Olej z czarnuszki tłoczymy na zimno, w prasach ślimakowych, w których temperatura tłoczenia nie jest wyższa niż 35°C. Jak przy produkcji wszystkich olejów zimnotłoczonych, naszego oleju nie filtrujemy, nie rafinujemy i nie oczyszczamy, dzięki temu zachowuje on swoje wartości odżywcze oraz walory smakowe.
			</span>
		</div>
	</div>

	<div class="why-section-wrapper">
		<div class="why-icon ol-icon-hand-leaves" style="color:#c1f2df;"></div>
		<div class="why-texts">
			<span class="why-text-header">
				Bezwzględna świeżość
			</span>
			<span class="why-text">
				Olej z czarnuszki to produkt, po który chętnie i często sięgają rodzice. W związku z tym tłoczymy go niemal codziennie, na bieżąco, w porcjach odpowiadających zapotrzebowaniu. Pozwala nam to wysyłać do Was wyłącznie najświeższy olej.
			</span>
		</div>
	</div>

	<div class="why-section-wrapper">
		<div class="why-icon ol-icon-hands-heart-light" style="color:#ff9899;"></div>
		<div class="why-texts">
			<span class="why-text-header">
				Mała skala
			</span>
			<span class="why-text">
				Olejów nie tłoczymy do dużych sklepów, aptek ani zielarni, tylko do niedużego (ale wciąż powiększającego się) grona bezpośrednich klientów. Dzięki temu w pełni kontrolujemy jakość, warunki przechowywania i czas trwania transportu naszych produktów.
			</span>
		</div>
	</div>

	<div class="why-section-wrapper">
		<div class="why-icon ol-icon-parcel-hands" style="color:#ffcba5;"></div>
		<div class="why-texts">
			<span class="why-text-header">
				Bezpieczny transport
			</span>
			<span class="why-text">
				Nasze oleje wysyłamy do Was w ciemnych butelkach z grubego szkła (w trosce o wrażliwe kwasy tłuszczowe), a dodatkowo na czas transportu pakujemy je w styropianowe termosy. Zapewnia to ochronę przed światłem słonecznym i temperaturą.
			</span>
		</div>
	</div>
</div>
</div>
```
Analogicznie jak w przypadku poprzedniej strony, edytujemy jedynie tekst pomiędzy znacznikami a następnie wklejamy za pomocą edytora HTML stron własnych w kod strony własnej.

#### Naglówek sekcji
Nagłówek sekcji uzupełniamy w poniższym fragmencie kodu:
```html
<h3 class="column is-8 is-offset-2 why-header">
Dlaczego warto sięgnąć po olej z czarnuszki Olini?
</h3>
<span class="column is-8 is-offset-2">
W naszej rodzinnej olejarni tłoczymy jedynie najlepszej jakości olej z czarnuszki.
Jeszcze niedawno tłoczyliśmy go jedynie dla siebie i naszych bliskich, teraz chcemy dzielić
się tym co najlepsze z naszymi klientami:
</span>
```
#### Treść w sekcji
Sekcja, podobnie jak poprzednia, sklada się z niemal identycznych bloków:
```html
<div class="why-section-wrapper">
		<div class="why-icon ol-icon-parcel-hands" style="color:#ffcba5;"></div>
		<div class="why-texts">
			<span class="why-text-header">
				Bezpieczny transport
			</span>
			<span class="why-text">
				Nasze oleje wysyłamy do Was w ciemnych butelkach z grubego szkła (w trosce o wrażliwe kwasy tłuszczowe), a dodatkowo na czas transportu pakujemy je w styropianowe termosy. Zapewnia to ochronę przed światłem słonecznym i temperaturą.
			</span>
		</div>
</div>
```
Wypełniamy tutaj text w znaczniku o klasie ``"why-text-header"`` - nagłówek elementu sekcji oraz w znaczniku o klasie ``"why-text"`` - treść elementu sekcji.
    
### SEKCJA 8
Analogicznie jak w przypadku sekcji 4, aby sekcja była widoczna, należy:
* dodać do produktu odpowiedni tag ``experts`` 
* stworzyć stronę o nazwie ``nazwa_produktu_experts`` 
* edytować templatkę i wkleić kod w kod strony własnej.   
```html
<div class="column is-12">
	<h3 class="experts-header">
		Opinie ekspertów
	</h3>
</div>
<div class="columns experts-wrapper">
	<div class="column is-narrow-desktop is-narrow-tablet  is-12-mobile is-paddingless">
		<figure><img src="//cdn.shoplo.com/3585/files/pantabletka.png" ></figure>
	</div>
	<div class="column expert-review-wrapper">
<div class="expert-triangle"></div>
		<span class="experts-review">"Możemy powiedzieć, że czarnuszka to dosłownie bomba składników bioaktywnych. A odpowiedniej jakości olej z czarnuszki to esencja z esencji. Prozdrowotny dynamit. <br>
			O czarnuszce mówimy, że posiada właściwości immunomodulujące. Oznacza to, że wpływa na działanie układu odpornościowego. Immunomodulacja to działanie dużo bardziej subtelne niż samo „stymulowanie odporności”. Związki bioaktywne, które ukryte są w czarnuszce (głównie ten tymochinon) – z jednej strony mają zdolność do mobilizowania układu odpornościowego, czyli czasowo podnoszą ilość komórek „wojowników” układu odpornościowego, a z drugiej działają przeciwzapalnie i łagodząco w stanach, kiedy układ odpornościowy działa „za bardzo”, czyli w różnego rodzaju chorobach alergicznych (np.: alergiczny nieżyt nosa), atopowym zapaleniu skóry i reumatoidalnym zapaleniu stawów."
		</span>
		<span class="experts-author">
			Pan Tabletka, <a href="http://pantabletka.pl"> http://pantabletka.pl</a>
		</span>
	</div>
</div>
<div class="columns experts-wrapper">
	<div class="column is-narrow-desktop is-narrow-tablet  is-12-mobile is-paddingless">
		<figure><img src="https://cdn.shoplo.com/3585/files/aaaaa.png" ></figure>
	</div>
	<div class="column expert-review-wrapper">
		<span class="experts-review">"Przygotujcie się na jesień! Nasz sekretny plan odpornościowy: olej z czarnuszki Olini + miód. Zaczynamy znów go pić, by dzieci chorowały jak najmniej i łagodnie przechodziły infekcje. Czy to naprawdę działa? TAK! <br>
			Pierwszy wpis o oleju umieściłyśmy na blogu w 2016 roku, od tego czasu olej z czarnuszki od Olini jest w naszych lodówkach cały rok. Nie, nie pijemy go non stop, robimy okresowe przerwy, ale w sezonie od sierpnia do marca staramy się, by dzieci piły go regularnie."
		</span>
		<span class="experts-author">
			Alaantkoweblw, <a href="https://alaantkoweblw.pl">https://alaantkoweblw.pl</a>
		</span>
	</div>
</div>
```
Analogicznie jak w przypadku każdej innej takiej strony, edytujemy jedynie tekst pomiędzy znacznikami a następnie wklejamy za pomocą edytora HTML stron własnych w kod strony własnej. Jedyną różnicą tutaj jest to, że musimy również wkleić bezpośrednie odnośniki do zdjęć dla każdej opinii. 

Sekcja ta składa się z bloków, dla każdej opinii:

```html
<div class="columns experts-wrapper">
    <div class="column is-narrow-desktop is-narrow-tablet  is-12-mobile is-paddingless">
        <figure><img src="//cdn.shoplo.com/3585/files/pantabletka.png"></figure>
    </div>
    <div class="column expert-review-wrapper">
        <div class="expert-triangle"></div>
            <span class="experts-review">"Możemy powiedzieć, że czarnuszka to dosłownie bomba składników bioaktywnych. A odpowiedniej jakości olej z czarnuszki to esencja z esencji. Prozdrowotny dynamit. <br>
                O czarnuszce mówimy, że posiada właściwości immunomodulujące. Oznacza to, że wpływa na działanie układu odpornościowego. Immunomodulacja to działanie dużo bardziej subtelne niż samo „stymulowanie odporności”. Związki bioaktywne, które ukryte są w czarnuszce (głównie ten tymochinon) – z jednej strony mają zdolność do mobilizowania układu odpornościowego, czyli czasowo podnoszą ilość komórek „wojowników” układu odpornościowego, a z drugiej działają przeciwzapalnie i łagodząco w stanach, kiedy układ odpornościowy działa „za bardzo”, czyli w różnego rodzaju chorobach alergicznych (np.: alergiczny nieżyt nosa), atopowym zapaleniu skóry i reumatoidalnym zapaleniu stawów."
            </span>
            <span class="experts-author">
                Pan Tabletka, <a href="http://pantabletka.pl"> http://pantabletka.pl</a>
            </span>
        </div>
    </div>
```
Tu wklejamy odpowiednie:
* Link do obrazu w atrybucie src do znacznika img: ``<img src="//linkdoobrazkadlaopinii.png">`` 
* Treść opinii eksperta w znaczniku z klasa ``"experts-review"``
* W znaczniku o klasie ``"experts-author"`` wypełniamy informacje o autorze opinii, jego nazwę oraz adres url (W znaczniku A podmieniamy adres url, odpowiednio w dwóch miejscach)

### SEKCJA 9 
Analogicznie jak w przypadku sekcji 4, aby sekcja była widoczna, należy:
* dodać do produktu odpowiedni tag ``faq`` 
* stworzyć stronę o nazwie ``nazwa_produktu_faq`` 
* edytować templatkę i wkleić kod w kod strony własnej.  
```html
<div class="columns">
<div class="column is-12">
	<h3 class="faq-header">
Najczęściej zadawane pytania
	</h3>
</div>
<div class="column is-12 is-paddingless custom-faq-questions">
        <div class="custom-faq-block">
            <div class="custom-faq-header">
                <h3 class="custom-faq-question"> Czy olej z czarnuszki można pić w ciąży?</h3> 
                <div class="faq-buttons"><span class="faq-hidden faq-button">+</span><span class="faq-visible faq-button">-</span></div>
            </div>
                <div class="custom-faq-collapsabe-answer">
                    Olej z czarnuszki jest sklasyfikowany jako bezpieczny olej spożywczy, nie środek leczniczy, więc nie ma działań niepożądanych. Pojawiają się jednak również opinie, że czarnuszka nie jest zalecana w ciąży, bo może wywołać przedwczesne skurcze.
                    W dużych ilościach i jako nowość w diecie, olej z czarnuszki w ciąży może nie być najlepszym pomysłem, ale jeśli jest obecny w naszej kuchni na co dzień to w ciąży nie trzeba z niego rezygnować.
                    Ponieważ każda ciąża jest inna, najbezpieczniej będzie skonsultować się ze swoją położną lub lekarzem.
                </div>
        </div>
        <div class="custom-faq-block">
            <div class="custom-faq-header">
                <h3 class="custom-faq-question">Dlaczego olej ma zupełnie inny kolor niż poprzednio?</h3> 
                <div class="faq-buttons"><span class="faq-hidden faq-button">+</span><span class="faq-visible faq-button">-</span></div>
            </div>        
                <div class="custom-faq-collapsabe-answer">
                Olej z czarnuszki jest sklasyfikowany jako bezpieczny olej spożywczy, nie środek leczniczy, więc nie ma działań niepożądanych. Pojawiają się jednak również opinie, że czarnuszka nie jest zalecana w ciąży, bo może wywołać przedwczesne skurcze.
                W dużych ilościach i jako nowość w diecie, olej z czarnuszki w ciąży może nie być najlepszym pomysłem, ale jeśli jest obecny w naszej kuchni na co dzień to w ciąży nie trzeba z niego rezygnować.
                Ponieważ każda ciąża jest inna, najbezpieczniej będzie skonsultować się ze swoją położną lub lekarzem.
            </div>
    </div>
    <div class="custom-faq-block">
        <div class="custom-faq-header">
            <h3 class="custom-faq-question">Czy olej z czarnuszki mogę łączyć z zakwasem z buraków?</h3> 
            <div class="faq-buttons"><span class="faq-hidden faq-button">+</span><span class="faq-visible faq-button">-</span></div>
        </div>   
             <div class="custom-faq-collapsabe-answer">
            Olej z czarnuszki jest sklasyfikowany jako bezpieczny olej spożywczy, nie środek leczniczy, więc nie ma działań niepożądanych. Pojawiają się jednak również opinie, że czarnuszka nie jest zalecana w ciąży, bo może wywołać przedwczesne skurcze.
            W dużych ilościach i jako nowość w diecie, olej z czarnuszki w ciąży może nie być najlepszym pomysłem, ale jeśli jest obecny w naszej kuchni na co dzień to w ciąży nie trzeba z niego rezygnować.
            Ponieważ każda ciąża jest inna, najbezpieczniej będzie skonsultować się ze swoją położną lub lekarzem.
        </div>
</div>
<div class="custom-faq-block">
    <div class="custom-faq-header">
        <h3 class="custom-faq-question"> Czy olej z czarnuszki można pić w ciąży?</h3> 
        <div class="faq-buttons"><span class="faq-hidden faq-button">+</span><span class="faq-visible faq-button">-</span></div>
    </div>
        <div class="custom-faq-collapsabe-answer">
        Olej z czarnuszki jest sklasyfikowany jako bezpieczny olej spożywczy, nie środek leczniczy, więc nie ma działań niepożądanych. Pojawiają się jednak również opinie, że czarnuszka nie jest zalecana w ciąży, bo może wywołać przedwczesne skurcze.
        W dużych ilościach i jako nowość w diecie, olej z czarnuszki w ciąży może nie być najlepszym pomysłem, ale jeśli jest obecny w naszej kuchni na co dzień to w ciąży nie trzeba z niego rezygnować.
        Ponieważ każda ciąża jest inna, najbezpieczniej będzie skonsultować się ze swoją położną lub lekarzem.
    </div>
</div>
</div>
</div>
```

Analogicznie jak w przypadku każdej innej takiej strony, edytujemy jedynie tekst pomiędzy znacznikami a następnie wklejamy za pomocą edytora HTML stron własnych w kod strony własnej.
Podobnie jak w przypadku porpzednich sekcji są tu powtarzalne bloki, w których wypełniamy tylko treść w miejsce tej przykładowej:
```html
<div class="custom-faq-block">
    <div class="custom-faq-header">
        <h3 class="custom-faq-question"> Czy olej z czarnuszki można pić w ciąży?</h3> 
        <div class="faq-buttons"><span class="faq-hidden faq-button">+</span><span class="faq-visible faq-button">-</span></div>
    </div>
    <div class="custom-faq-collapsabe-answer">
                    Olej z czarnuszki jest sklasyfikowany jako bezpieczny olej spożywczy, nie środek leczniczy, więc nie ma działań niepożądanych. Pojawiają się jednak również opinie, że czarnuszka nie jest zalecana w ciąży, bo może wywołać przedwczesne skurcze.
                    W dużych ilościach i jako nowość w diecie, olej z czarnuszki w ciąży może nie być najlepszym pomysłem, ale jeśli jest obecny w naszej kuchni na co dzień to w ciąży nie trzeba z niego rezygnować.
                    Ponieważ każda ciąża jest inna, najbezpieczniej będzie skonsultować się ze swoją położną lub lekarzem.
    </div>
</div>
```
W blokach podmieniamy tylko treść pytania FAQ 2 znaczniku ``h3`` oraz treść odpowiedzi w znaczniku oznaczonym klasą ``"custom-faq-collapsabe-answer"``

### SEKCJA 10
Analogicznie jak w przypadku poprzednich sekcji, aby sekcja była widoczna, należy:
* dodać do produktu odpowiedni tag ``stories`` 
* stworzyć stronę o nazwie ``nazwa_produktu_stories`` 
* edytować templatkę i wkleić kod w kod strony własnej.
```html 
<h3 class="column is-12 stories-header">
Historie klientów
</h3>
<div class="columns stories">

    <div class="column is-12 story">
        <p class="story-content">
            "Uczucie odetkanego nosa, zmniejszenie obrzęku w okolicach zatok, brak wydzieliny spływającej po gardle, no cuda! A zazwyczaj w czasie pylenia brzozy był dramat. Wierzę w magiczną moc oleju, jest bardzo intensywny w smaku, czuć że robicie to dobrze. Dziękuję! Polecam dalej."
        </p>
        <span class="story-author">@mkreuje</span>
    </div>
    <div class="column is-12 story">
        <p class="story-content">
            "Chorowałam 3 miesiące (organizm osłabiony ciąża i porodem, nawracające przeziębienia, grypy, wirusy) i dopiero po piciu oleju, który podniósł  odporność przestałam chorować. Świadczy to o dobrej jakości oleju. To już dożywotnio mój olejowy sklep.”
        </p>
        <span class="story-author">@Ania Jabłońska</span>
    </div>
    <div class="column is-12 story">
        <p class="story-content">
            "Sama nie wierzyłam w działanie czarnuszki, myślałam że kolejny przereklamowany lek na wszystko. U mnie za każdym razem z wiosną przychodził koszmar związany z ciągłym swędzeniem oczu, katarem, non stop leki na alergię które praktycznie nie pomagały. Spróbowałam olej z czarnuszki nie wierząc w to, że pomoże, kiedy obudziłam się następnego dnia bez typowego swędzenia nie mogłam w to uwierzyć, myślałam że może to przypadek, odstawiłam olej, następnego dnia znowu ta alergia!!! Znowu łyżka oleju i następnego dnia brak objawów. Odstawiłam leki na alergie całkowicie."
        </p>
        <span class="story-author">@Natalya Malczyk</span>
    </div>
    <div class="column is-12 story">
        <p class="story-content">
            "Uczucie odetkanego nosa, zmniejszenie obrzęku w okolicach zatok, brak wydzieliny spływającej po gardle, no cuda! A zazwyczaj w czasie pylenia brzozy był dramat. Wierzę w magiczną moc oleju, jest bardzo intensywny w smaku, czuć że robicie to dobrze. Dziękuję! Polecam dalej."
        </p>
        <span class="story-author">@mkreuje</span>
    </div>
    <div class="column is-12 story">
        <p class="story-content">
            "Chorowałam 3 miesiące (organizm osłabiony ciąża i porodem, nawracające przeziębienia, grypy, wirusy) i dopiero po piciu oleju, który podniósł  odporność przestałam chorować. Świadczy to o dobrej jakości oleju. To już dożywotnio mój olejowy sklep.”
        </p>
        <span class="story-author">@Ania Jabłońska</span>
    </div>
    <div class="column is-12 story">
        <p class="story-content">
            "Sama nie wierzyłam w działanie czarnuszki, myślałam że kolejny przereklamowany lek na wszystko. U mnie za każdym razem z wiosną przychodził koszmar związany z ciągłym swędzeniem oczu, katarem, non stop leki na alergię które praktycznie nie pomagały. Spróbowałam olej z czarnuszki nie wierząc w to, że pomoże, kiedy obudziłam się następnego dnia bez typowego swędzenia nie mogłam w to uwierzyć, myślałam że może to przypadek, odstawiłam olej, następnego dnia znowu ta alergia!!! Znowu łyżka oleju i następnego dnia brak objawów. Odstawiłam leki na alergie całkowicie."
        </p>
        <span class="story-author">@Natalya Malczyk</span>
    </div>
    <div class="column is-12 story">
        <p class="story-content">
            "Uczucie odetkanego nosa, zmniejszenie obrzęku w okolicach zatok, brak wydzieliny spływającej po gardle, no cuda! A zazwyczaj w czasie pylenia brzozy był dramat. Wierzę w magiczną moc oleju, jest bardzo intensywny w smaku, czuć że robicie to dobrze. Dziękuję! Polecam dalej."
        </p>
        <span class="story-author">@mkreuje</span>
    </div>
    <div class="column is-12 story">
        <p class="story-content">
            "Chorowałam 3 miesiące (organizm osłabiony ciąża i porodem, nawracające przeziębienia, grypy, wirusy) i dopiero po piciu oleju, który podniósł  odporność przestałam chorować. Świadczy to o dobrej jakości oleju. To już dożywotnio mój olejowy sklep.”
        </p>
        <span class="story-author">@Ania Jabłońska</span>
    </div>
    <div class="column is-12 story">
        <p class="story-content">
            "Sama nie wierzyłam w działanie czarnuszki, myślałam że kolejny przereklamowany lek na wszystko. U mnie za każdym razem z wiosną przychodził koszmar związany z ciągłym swędzeniem oczu, katarem, non stop leki na alergię które praktycznie nie pomagały. Spróbowałam olej z czarnuszki nie wierząc w to, że pomoże, kiedy obudziłam się następnego dnia bez typowego swędzenia nie mogłam w to uwierzyć, myślałam że może to przypadek, odstawiłam olej, następnego dnia znowu ta alergia!!! Znowu łyżka oleju i następnego dnia brak objawów. Odstawiłam leki na alergie całkowicie."
        </p>
        <span class="story-author">@Natalya Malczyk</span>
    </div>
</div>
```
Analogicznie jak w przypadku każdej innej takiej strony, edytujemy jedynie tekst pomiędzy znacznikami a następnie wklejamy za pomocą edytora HTML stron własnych w kod strony własnej.

Tu również mamy powtarzalne bloki, które trzeba wypełnić odpowiednią treścią:
```html
<div class="column is-12 story">
        <p class="story-content">
            "Sama nie wierzyłam w działanie czarnuszki, myślałam że kolejny przereklamowany lek na wszystko. U mnie za każdym razem z wiosną przychodził koszmar związany z ciągłym swędzeniem oczu, katarem, non stop leki na alergię które praktycznie nie pomagały. Spróbowałam olej z czarnuszki nie wierząc w to, że pomoże, kiedy obudziłam się następnego dnia bez typowego swędzenia nie mogłam w to uwierzyć, myślałam że może to przypadek, odstawiłam olej, następnego dnia znowu ta alergia!!! Znowu łyżka oleju i następnego dnia brak objawów. Odstawiłam leki na alergie całkowicie."
        </p>
        <span class="story-author">@Natalya Malczyk</span>
    </div>
```
w znaczniku oznaczonym klasą ``"story-content"`` wpisujemy treść historii klienta, natomiast w znaczniku oznaczonym klasą ``"story-author"`` wypełniamy nazwę autora historii.


### SEKCJA 11
Sekcja ta jest galerią, aby dodać zdjęcia do tej galerii, należy:
* Dodać zdjęcia do karty produktu
* Nadać zdjęciom odpowiednie alty - ``bot-gallery``
Sterować widocznością galerii możemy za pomocą tagu ``bot-gallery`` - jeśli produkt takiego tagu nie ma, galeria się nie wyświetli. 
Ważne - aby galeria wyświetlała się dobrze, konieczne jest aby były w niej conajmniej dwa zdjęcia.


### SEKCJA 12

Sekcja ta tworzy się 'sama' - jeśli istnieje ścieżka przejścia do produktu (z kategorii/kolekcji) to tu wyświetlą się produktu z kolekcji/kategorii z której przyszliśmy.

## OVERLAY NA LIŚCIE PRODUKTÓW
Aby na liscie produktów po najechaniu pojawiała się lista, w **KRÓTKIM OPISIE PRODUKTU** należy wkleić następujący fragment kodu i wypełnić odpowiednimi informacjami:
```html
<div class="custom-product-hover">
<ul>
<li>Najczęściej wybierany przez rodziców</li>
<li>Bomba składników bioaktywnych</li>
<li>Naturalne wsparcie przy alergii</li>
</ul>
<a href="{$p->url}">zobacz</a></div>
```
Zmieniamy tylko treść w znacznikach ``li``

## DROPDOWN MENU W MENU GŁÓWNYM

Aby z elementu menu wysunęło się menu rozwijane, w panelu należy:
* Stworzyć dwie nawigacje nazwane odpowiednio:
    ``tytułmenuzkjtóregomenumasięrozwijac_1`` oraz ``tytułmenuzkjtóregomenumasięrozwijac_1``
    I umieścić w nich odpowiednie linki.
    W każdej z dwóch nawigacji ostatni link będzie wyróżniony kolorem
* Dodać do szablonu zdjęcie mające wyswietlać się w menu, zdjęcie powinno mieć odpowiednią nazwę - nazwaelementuwmenuglownymphoto i być w formacie png, przykładowo ``olejephoto.png``

Aby dodać zdjęcie do szablonu, należy:
* Przejść w panelu do zakłądki wygląd sklepu, otworzyć edytor HTML szablonu
* W menu po lewej stronie wybrać "Pozostałe pliki" i na samym dole tej sekcji pojawi się "Dodaj plik", należy dodać plik w tym miejscu. 


    


