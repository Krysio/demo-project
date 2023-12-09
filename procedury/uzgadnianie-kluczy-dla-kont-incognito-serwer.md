# Uzgadnianie puli kluczy dla nowych kont incognito z punktu widzenia serwera nadzorującego operację

Serwer zbiera połączenia z użytkownikami chcącymi utworzenia nowego anonimowego konta. W miarę możliwości z puli uczestników stara się dobrać odpowiednio liczną grupę z jak najmniejszą średnią wartością pola `level`.

Dodatkowo należy unikać dobierania kont anonimowych, które zostały utworzone w tej samej operacji.

```
Dla jawnego konta użytkownika wartość pola level wynosi 0. Natomiast wartość dla nowych kont anonimowych obliczana jest jako średnia z kont tworzących + 1 
```

Po zebraniu odpowiedniej puli użytkowników do każdego wysyłana jest lista uczestniczących w procedurze.

Serwer czeka aż otrzyma pakiety adresowane do innych użytkowników od każdego uczestnika. Pakiety są grupowane według adresata i jednorazowo wysyłane.

Po kilku turach serwer otrzymuje użytkowników listy kluczy publicznych w różnej liczbie. Odrzucając powtórzenia tworzy pulę kluczy a następnie treść komendy tworzącej nowe konta w systemie. Przesyła ją do każdego użytkownika w celu potwierdzenia poprawności oraz uzyskania sygnatury - podpisu.

Po otrzymaniu wszystkich sygnatur tworzona jest kompletna komenda i wprowadzana jest do systemu block-chain.


