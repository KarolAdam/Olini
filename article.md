# Artykuł

## Pierwsza sekcja z krótkim opisem
```html
<div class="article-short-info">
					Najczęstsze pytania o olej z czarnuszki
					Dlaczego mój olej z czarnuszki jest zupełnie czarny a zawsze był słomkowy. Czy osad na dnie buteleczki jest naturalny? Jaki jest termin przydatności do spożycia oleju z czarnuszki? Jak ten olej bezpiecznie przetransportować? Poznaj odpowiedzi na najczęściej pojawiające się pytania o olej z czarnuszki!
</div>
```
Podmieniamy tekst pomiędzy znacznikami.

## Druga sekcja z nazwą i zdjęciem autora
```html
<div class="article-author">
		<div class="author-inner-wrapper">
			<figure><img src="https://cdn.shoplo.com/5432/s/80/assets/author.png"></figure>
			<span class="article-author">Agnieszka Maciejowska</span>
		</div>
</div>
```
w znaczniku Img podmieniamy link do zdjęcia natomiast w znaczniku span wstawiamy imię i nazwisko autora

## Trzecia sekcja z głównym zdjęciem artykułu
```html
<div class="article-image-full">
	<figure>
		<img src="https://cdn.shoplo.com/5432/s/80/assets/Warstwa_10.png">
	</figure>
</div>
```
Podmieniamy tylko link do zdjęcia

## Czwarta sekcja - tekst główny artykułu
```html
<div class="article-text-content">
	<h3 class="article-text-header">
			Dlaczego mój olej jest ciemny/jasny?
	</h3>
	<p class="article-text">
						Olej z czarnuszki bywa bardzo różny. Potrafi być zupełnie jasny, niemal przezroczysty o słomkowym zabarwieniu, wygląda wtedy tak jak oleje do których przywykliśmy np. słonecznikowy. Bywa również bardzo ciemny, niemal czarny, nieprzezroczysty, często jest też mętny z widocznym osadem. Kolor oleju zależy od partii ziaren. Z tej samej rośliny – czarnuszki siewnej – otrzymujemy zarówno bardzo jasny jak i ciemny olej. Dodatkowo olej tłoczony na zimno, niefiltrowany i nierafinowany jak ten z Rodzinnej Olejarni Olini – jest w pełni naturalny, nieoczyszczany, przez co może być mętny, nieprzezroczysty i zawierać osad. W przypadku oleju z czarnuszki kolor osadu będzie w ciemnym kolorze takim samym jak ziarno. Zarówno jasny, jak i ciemny olej z czarnuszki jest pełnowartościowy. Każdy z tych olejów ma też swoich zwolenników, spotykamy się zarówno z osobami, które preferują olej przezroczysty, słomkowy jak i takimi którzy cenią sobie olej ciemny albo z dużą ilością osadu. Ważne jest żeby wybierać olej z czarnuszki tłoczony na zimno, nierafinowany i nieoczyszczany.
	</p>
</div>
```

W Znaczniku h3 wstawiamy nagłówek sekcji, natomiast w znaczniku p jej treść. Te elementy możemy dowolnie powielać, ale powinny znajdować się wewnatrz div'a o klasie ``article-text-content``.

## Piąta sekcja - box z tłem
```html 
<div class="background-image-box">
    <div class="background-box">
    	<h3 class="background-box-header">
    		W naszej rodzinnej olejarni oleje tłoczymy dopiero w momencie Twojego zamówienia.
    	</h3>
    	<h4 class="background-box-subheader">
    		Termiczne opakowanie i bezpieczna dostawa gwarantują najwyższą świeżość!
    	</h4>
    	<a href="https://olini.pl" class="to-store-button">PRZEJDŹ DO SKLEPU</a>
	</div>
</div>
```
Tu edytujemy teksty pomiędzy znacznikami h4, h4 i a. Pierwsze dwa są trescia sekcji, trzeci jest napisem na buttonie. W elemencie a powinnismy też podmienić link.

## Szósta sekcja - box z produktem i tekstem

```html
<div class="article-content-product-box">
	<div class="product-box">
		<figure>
		    <img src="https://cdn.shoplo.com/5432/s/80/assets/Warstwa_15.png">
		    </figure>
		<span class="product-name">
			Świeżo tłoczony
			olej z czarnuszki
		</span>
		<a href="https://olini.pl" class="to-store-button">ZOBACZ W SKLEPIE</a>
	</div>
	
	<div class="article-text-content-small">
	    <h3 class="article-text-header">
			Chcę zabrać mój olej na urlop – jak bezpiecznie go przewieźć?
		</h3>
		<p class="article-text">
			Często spotykamy się z pytaniami o bezpieczny transport oleju z czarnuszki. Niektórzy chcą zabgo ze sobą na urlop, inni pragną zawieź go do rodzinny czy bliskich mieszkających daleko. olej nie stracił swoich właściwości warto zadbać o jak najlepsze warunki jego przewożenia. Ważeby olej był w ciemnej, zakręconej buteleczce. Jeżeli będziesz potrzebować tylko jakąś niewieilość oleju, możesz ją odlać do mniejszej buteleczki. Schłodzony olej wyjmij z lodówki tuż prsamym wyjazdem. Możesz zawinąć go w folię aluminiową a następnie umieścić np. w styropianoopakowaniu w którym kurier dostarczył Twój olej z olejarni. Dobrym pomysłem będzie wykorzystateż pojemniczka termicznego albo termosu. Tak zabezpieczony olej może spokojnie podróżować prjakiś czas. Pamiętaj, że możesz też zamówić świeży olej bezpośrednio na miejsce wakacji lubTwoich bliskich, będziesz miał wtedy pewność, że olej został odpowiednio zabezpieczony na ctransportu.
		</p>
	</div>
</div>
```

Tak jak poprzednio uzupełniamy tekst pomiędzy konkretnymi znacnzikami - musimy pamiętać o linku w a i linkach do zdjęć.

## Siódma sekcja - bibliografia
```html 
<div class="article-sources">
	<h5>
		Źródła informacji:
	</h5>
	<p>(1) <a href="https://www.blogojciec.pl">https://www.blogojciec.pl</a></p>
	<p>(2) <a href="https://www.blogojciec.pl">https://www.blogojciec.pl</a></p>
	<p>(3) <a href="https://www.blogojciec.pl">https://www.blogojciec.pl</a></p>
</div>
```
Edytujemy treść linków, może być ich dowolna ilość

## ósma sekcja - o autorze
```html
<div class="author-details">
	<h5>
		Autor/ka:
	</h5>
	<div class="author-wrapper">
	<figure><img src="https://cdn.shoplo.com/5432/s/80/assets/author.png"></figure>
	<p>
		Agnieszka Maciejowska
		Od lat związana ze zdrową żywnością. W Olini.pl odpowiada za testowanie produktów
		i edukację ludzi.
	</p>
	</div>
</div>
```
Analogicznie jak w przypadku poprzednich sekcji - wypełniamy treści pomiędzy zancznikami, pamiętami o linku do zdjęcia. 


