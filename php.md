# PHP - ważne notatki
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
