# Instrukcja tworzenia Landing Page
1. Tworzymy stronę własną w panelu shoplo, na której znajdzie się Landing Page, sprawdzamy "uchwyt" do niej w konsoli. 
2. Wchodzimy w edytor HTML szablonu i otwieramy plik ``page.tpl``, odszukujemy warunek ``{else}`` (na screenie poniżej w 423 linii kodu) 
![](https://i.imgur.com/oo530XR.png)
i przed nim wklejamy następujący fragment kodu: 
```
{else if $page->handle == 'uchwyt_strony'}
{snippet file='uchwyt_strony'}
```
3. W edytorze szablonu html, w sekcji ``Snippets`` tworzymy nowy snippet o nazwie identycznej jak uchwyt strony, przechodzimy do edycji tego snippetu.
4. Jako "szkielet" landinga wklejamy poniższy kod:
```html
<div class="container landing-page">
<div class="columns fixed-width">
	
</div>
</div>
```
5. Kolejnym krokiem jest wklejenie poniższych elementów w żądanej kolejności:
a. Nagłówek:
```html
<div class="column is-12 landing-header">
	<h1 class="has-text-weight-bold">Pyszności za 1 grosz!</h1>
    <h2>Zrób zakupy za podaną kwotę i odbierz jedną z naszych pyszności za 1 grosz. </h2>
</div>
```
b. Zdjęcie na całą szerokość:
```html
<div class="column is-12 langing-image-full is-paddingless-mobile">
	<img src="https://cdn.shoplo.com/5432/s/80/assets/landing1.png">
</div>
```
c. Kolekcja 4 produktów:
W poniższym fragmencie edytujemy **tylko** nazwę kolekcji w linii ``settings_collection`` oraz ilość produktów wyświetlanych w tym bloku w wierszu poniżej. 
```html
<div class="column  is-paddingless is-12 landing-collection">
		<h2>
			Odbierz jeden z następujących produktów za 1 grosz:
		</h2>
		{snippet
		file="landing_products_4"
		grid_class="shb-grid-col-4"
		product_col_class="column is-4-tablet is-3-desktop cart-prod"
		sidebar_col_class="column is-3-tablet"
		product_view=1
		set_image_ratio={$settings->product_image_ratio}
		settings_collection="frontpage"
		settings_frontpage_collection_products_count="8"
		product_list_show_add_to_cart = {$settings->product_list_show_add_to_cart}
		product_list_show_title = {$settings->product_list_show_title}
		product_list_title_limit = {$settings->product_list_title_limit}
		product_list_show_variants = {$settings->product_list_show_variants}
		product_list_show_variants_on_hover = {$settings->product_list_show_variants_on_hover}
		}

	</div>
```
d. Blok tesktu z tłem i dwóch produktów:
W poniższym fragmencie kodu poza odpowiednimi tekstami zmieniamy również tytuł kolekcji.
```html
<div class="column is-paddingless is-12 landing text-two-products">
		<div class="container">

			<div class="columns fixed-width">
				<div class="column is-6 is-12-mobile is-paddingless-mobile">
					<div class="textbox small-tb" style="background-color: #ffcba5;">

					<h4>
						Dla zakupów powyżej 300zł:
					</h4>
					<p>
						Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque ac finibus lectus. Curabitur sollicitudin dolor nec mauris congue dictum. Morbi eu finibus sem, eget mattis enim. Suspendisse molestie ipsum eget neque imperdiet laoreet. Nullam sollicitudin justo eget posuere sagittis.


					</p>
						

					<span>MIX-ZA-GROSZ</span>
					</div>
				</div>
				<div class="column is-6 is-12-mobile">
					{snippet
					file="landing_products_2"
					grid_class="shb-grid-col-4"
					product_col_class="column is-4-tablet is-3-desktop cart-prod"
					sidebar_col_class="column is-3-tablet"
					product_view=1
					set_image_ratio={$settings->product_image_ratio}
					settings_collection="frontpage"
					settings_frontpage_collection_products_count="2"
					product_list_show_add_to_cart = {$settings->product_list_show_add_to_cart}
					product_list_show_title = {$settings->product_list_show_title}
					product_list_title_limit = {$settings->product_list_title_limit}
					product_list_show_variants = {$settings->product_list_show_variants}
					product_list_show_variants_on_hover = {$settings->product_list_show_variants_on_hover}
					}
				</div>
			</div>
		</div>
	</div>

e. Blok tekstu z jednym produktem:
W poniższym fragmencie kodu poza odpowiednimi tekstami zmieniamy również tytuł kolekcji.
```html
<div class="column is-paddingless is-12 landing text-one-product">
			<div class="container">
				<div class="columns fixed-width">
					<div class="column is-9 landing-textbox is-paddingless-mobile">
						<div class="textbox" style="background-color: #ffcba5;">

						<h4>
							Dla zakupów powyżej 300zł:
						</h4>
						<p>
							Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque ac finibus lectus. Curabitur sollicitudin dolor nec mauris congue dictum. Morbi eu finibus sem, eget mattis enim. Suspendisse molestie ipsum eget neque imperdiet laoreet. Nullam sollicitudin justo eget posuere sagittis. Nulla lobortis non odio id aliquet. Donec fringilla dolor ex, sit amet gravida lectus ultrices eu. Maecenas ornare, lacus quis ultrices cursus, nisl leo mattis felis, non commodo metus eros et odio. Aenean consequat nec urna ut bibendum. Integer vitae metus lacus.


						</p>
							

						<span>MIX-ZA-GROSZ</span>
						</div>
					</div>
					<div class="column is-3">
						{snippet
						file="landing_products_1"
						grid_class="shb-grid-col-4"
						product_col_class="column is-4-tablet is-3-desktop cart-prod"
						sidebar_col_class="column is-3-tablet"
						product_view=1
						set_image_ratio={$settings->product_image_ratio}
						settings_collection="frontpage"
						settings_frontpage_collection_products_count="1"
						product_list_show_add_to_cart = {$settings->product_list_show_add_to_cart}
						product_list_show_title = {$settings->product_list_show_title}
						product_list_title_limit = {$settings->product_list_title_limit}
						product_list_show_variants = {$settings->product_list_show_variants}
						product_list_show_variants_on_hover = {$settings->product_list_show_variants_on_hover}
						}
					</div>
				</div>
			</div>
</div>
```
f. Blok ze zdjęciem i dwoma produktami
W poniższym kodzie edytujemy adres url zdjęcia oraz nazwę kolekcji:
```html
<div class="column is-paddingless is-12 landing photo-two-products">
		<div class="container">

			<div class="columns fixed-width">
				<div class="column is-6 is-12-mobile is-paddingless-mobile">
					<img src="https://cdn.shoplo.com/5432/s/80/assets/landing2.png">
				</div>
				<div class="column is-6 is-12-mobile">
					{snippet
					file="landing_products_2"
					grid_class="shb-grid-col-4"
					product_col_class="column is-4-tablet is-3-desktop cart-prod"
					sidebar_col_class="column is-3-tablet"
					product_view=1
					set_image_ratio={$settings->product_image_ratio}
					settings_collection="frontpage"
					settings_frontpage_collection_products_count="2"
					product_list_show_add_to_cart = {$settings->product_list_show_add_to_cart}
					product_list_show_title = {$settings->product_list_show_title}
					product_list_title_limit = {$settings->product_list_title_limit}
					product_list_show_variants = {$settings->product_list_show_variants}
					product_list_show_variants_on_hover = {$settings->product_list_show_variants_on_hover}
					}
				</div>
			</div>
		</div>
	</div>
```
g. Blok ze zdjęciem i z jednym produktem 
W poniższym kodzie edytujemy adres url zdjęcia oraz nazwę kolekcji:
```html
<div class="column is-paddingless is-12 landing photo-one-product">
		<div class="container">

			<div class="columns fixed-width">
				<div class="column is-9 is-paddingless-mobile">
					<img src="https://cdn.shoplo.com/5432/s/80/assets/landing2.png">
				</div>
				<div class="column is-3">
					{snippet
					file="landing_products_1"
					grid_class="shb-grid-col-4"
					product_col_class="column is-4-tablet is-3-desktop cart-prod"
					sidebar_col_class="column is-3-tablet"
					product_view=1
					set_image_ratio={$settings->product_image_ratio}
					settings_collection="frontpage"
					settings_frontpage_collection_products_count="1"
					product_list_show_add_to_cart = {$settings->product_list_show_add_to_cart}
					product_list_show_title = {$settings->product_list_show_title}
					product_list_title_limit = {$settings->product_list_title_limit}
					product_list_show_variants = {$settings->product_list_show_variants}
					product_list_show_variants_on_hover = {$settings->product_list_show_variants_on_hover}
					}
				</div>
			</div>
		</div>
	</div>
```
h. Blok z tekstem (Regulamin etc.)
Tu jest pełna dowolność edycji treści.
```html
		<div class="column is-12 text-box">
			<h4>
				Regulamin promocji "Pyszności za 1 grosz"
			</h4>
			<ol>
				<li>Organizatorem akcji jest Olini sp. z o.o.</li>
				<li>Czas trwania akcji od 20-02-2020 do 31-05-2020 r.</li>
				<li>Promocja polega na obniżeniu wartości wybranych produktów do 0,01 zł.</li>
				<li>Aby uzyskać rabat należy wpisać w odpowiednim polu w koszyku kod rabatowy.</li>
				<li>Kod rabatowy jest ważny do dnia 31-05-2020 r.</li>
				<li>Promocja obowiązuje na wybrane produkty opisane na stronie powyżej.</li>
				<li>Promocja obowiązuje w sklepie internetowym www.olini.pl.</li>
				<li>W przypadkach spornych interpretacja regulaminu leży po stronie Organizatora.</li>
			</ol>
		</div>
```

## Blokami można dowolnie zarządzać i manipulować kolejnością, może być więcej niż jeden blok tego samego typu, ale każdy musi mieć inną kolekcję. Każdy landing page musi mieć swój snippet. 
