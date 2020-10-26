# PHP - ważne notatki
## echo() vs print() vs print_r()
echo | print() | print_r()
----- |:------:|-----:
Wyświetla wiele wartości | Wyświetla tylko jedną wartość | Wyświetla zawartość np. całej tablicy czy obiektu
Zwraca void | Zwraca true | Jeśli drugi argument zostanie ustawiony na true, zwraca to co powinno wypisać do zmeinnej:
`echo` - wyświetla wiele warotści np:<br>
```php 
echo $var1, $var2, $var3;
```