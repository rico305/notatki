# PHP - ważne notatki
## Spis treści
1. [echo() vs print() vs print_r()](#echo()-vs-print()-vs-print_r())
2. [Cudzysłów, a apostrof](#Cudzysłów-a-apostrof)
3. [Tablice](#Tablice)
4. [Operatory](#operatory)
5. [Instrukcje warunkowe](#instrukcje-warunkowe)

## echo() vs print() vs print_r()

echo | print() | print_r()
:-----:|:------:|:-----:
Wyświetla wiele wartości | Wyświetla tylko jedną wartość | Wyświetla zawartość np. całej tablicy czy obiektu
Zwraca void | Zwraca true | Jeśli drugi argument zostanie ustawiony na true, zwraca to co powinno wypisać do zmeinnej
<br>

### Wyświetlanie kilku wartości przy użyciu echo:
```php
echo $var1, $var2, $var3;
```


## Cudzysłów, a apostrof
Ciągi tekstowe zapisane w cudzysłowach są interpretowane, w apostrofach nie. 
Dzięki temu w apostrofach możemy używać np. zmiennych.
```php
$ile = 5;
$a = "Ala ma $ile kotów.";
$b = 'Ala ma $ile kotów.';

echo $a; //Wypisuje: Ala ma 5 kotów.
echo $b; //Wypisuje: Ala ma $ile kotów.
```

Zapisywanie znaków cudzysłowu, apostrofu lub ukośnika w ciągu tekstowym:
```php
$a = "Spytał się: \"Dokąd idziesz?\".";
$b = 'Spytał się: \"Dokąd idziesz?\".';
$c = 'Spytał się: "Dokąd idziesz?".';

echo $a; //Wypisuje: Spytał się: "Dokąd idziesz?".
echo $b; //Wypisuje: Spytał się: \"Dokąd idziesz?\".
echo $c; //Wypisuje: Spytał się: "Dokąd idziesz?".
```

W cudzysłowiach możemy używać znaków specjalnych takich jak:
znak | znaczenie
:---:|:---:
\n | Nowa linia
\t | Tabulator
\\\ | Backslash

## Tablice
Różne, równoważne sposoby definiowania tablic:
```php
$brands = array('BMW', 'Maserati', 'Bugatti');
$brands = ['BMW', 'Maserati', 'Bugatti'];

$brands = [];
$brands[] = 'BMW';
$brands[] = 'Maserati';
$brands[] = 'Bugatti';
```

### Tablice asocjacyjne
Tablice asocjacyjne, to takie, w każdy element tablicy ma odpowiadający sobie indywidualny klucz.

Definiowanie tablicy asocjacyjnej i jej elementów:
```php
$book = [
    'id' => 1,
    'title' => 'Pan Tadeusz'
];
$book['author'] = 'Adam Mickiewicz';

echo $book['title']; //Wypisuje: Pan Tadeusz

print_r($book); // Wypisuje: array( [id] => 1 [title] => Pan Tadeusz [author] => Adam Mickiewicz)
```

## Operatory
Operator | Znaczenie
:--:|:-:
+|Dodawanie
-|Odjmowanie
*|Mnożenie
/|Dzielenie
**|Potęgowanie
%|Modulo (reszta z dzielenia)
++|Inkrementacja (zwiększenie o 1)
--|Dekrementacja (zmniejszenie o 1)

## Instrukcje warunkowe

### Sposób 1:
```php
if ( warunek ) {
    ...
}
elseif {
    ...
}
```
### Sposób 2 (zastosowanie instrukcji `end`):
```php
if ( warunek ) :
    ...
elseif : 
    ...
endif;
```

Sposób drugi (z zastsowoanie instrukcji 'end') możemy stosować również z innymi instrukcjami sterującymi jak np `while (endwhile)`, `for (endfor)` itd.

### Sposób 3:
```php
$var = ( warunek ) ? $valueWhenTrue : $valueWhenFalse;
```
Jeśli warunek jest prawdziwy, do zmiennej `$var` przypisana zostaje wartość zmiennej `$valueWhenTrue`, w przeciwnym wypadku `$valueWhenFalse`;

### Inna wersja:
```php
$var = $value ?? $default;
```
Jeśli jest zdefioniowana zmienna `$value`, to do zmiennej `$var` zostanie przypisana jej wartość, jeśli nie, przypisana zostanie wartość zmiennej `$default`;

Jest to analogiczny zapis do tego:
```php 
if(isset($value))
{
    $var = $value;
} else 
{
    $var = $default;
}
```
oraz tego:
```php
$var = isset($value) ? $value : $default;
```