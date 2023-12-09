# Uzgadnianie puli kluczy dla nowych kont incognito z punktu widzenia użytkownika

Procedura rozpoczyna się od zgłoszenia się do jednego z serwerów do wzięcia udziału w procedurze na zadany okres oraz w zadanym obszarze, oraz oczekiwanie na rozpoczęciu procedury przez serwer.

```
# Opcjonalne
Serwer otrzyma możliwość przekazania oczekujących użytkowników do innych serwerów
```

Użytkownik otrzymuje od serwera listę kont uczestniczącej w procedurze. Jest to przede wszystkim `userID` oraz klucz publiczny konta. Użytkownik wykonuje zapytanie o klucze publiczne dla podanych `userID` do innego źródła w celu zapobieżeniu atakowi `man in the middle` w wykonaniu serwera.

Użytkownik generuje nową parę kluczy dla nowego konta. Klucz zostanie rozesłany do losowych adresatów i zaszyfrowany ich kluczem publicznym w liczbie uczestników procedury. Każdy pakiet zostanie również zapakowany w pakiet adresowany również do losowego uczestnika procedury i szyfrowany. Ostatnia taka integracja obejmuje adresowanie do każdego uczestnika procedury. Unikamy sytuacji gdzie otrzymany pakiet zostanie zaadresowany do tego samego uczestnika. Jest to mechanizm zaczerpnięty z sieci TOR. Ostatecznie w tym kroku użytkownik wysyła do serwera pakiety adresowane po jednym dla każdego pozostałego uczestnika.

```
Trzeba tutaj ustalić optymalną ilość warstw w pakietach, intuicyjnie strzelając na początek będzie to 5.
```

Następnie nastąpi kilka tur otrzymania pakietu wiadomości. Użytkownik odszyfrowuje je swoim kluczem prywatnym i zawartość odsyła serwerowi. Zawartość nie jest tutaj istotna z punktu widzenia użytkowania.

Po wszystkich turach serwer prześle gotową zawartość komendy tworzącej nowe konta w systemie. Użytkownik weryfikuje czy jego klucz znajduje się w puli a następnie sporządza sygnaturę - podpis i przesyła ją serwerowi. 
